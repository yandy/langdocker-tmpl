FROM maven:3-eclipse-temurin-21-alpine AS base

RUN set -eux; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make


# build stage
FROM base AS build

COPY docker/settings.xml /root/.m2/settings.xml

COPY . /app

WORKDIR /app

RUN --mount=type=cache,target=/usr/share/maven/ref/repository set -eux; \
    sed -i "s@{{local_repo_path}}@/usr/share/maven/ref/repository@g" /root/.m2/settings.xml; \
    mvn package -Dmaven.test.skip=true


# package stage
FROM eclipse-temurin:21-jre-alpine

COPY --chmod=755 docker/entrypoint.sh /entrypoint.sh
COPY --from=build /app/target/app.jar /opt/app.jar

ENTRYPOINT [ "/entrypoint.sh" ]
CMD [ "/opt/app.jar" ]
