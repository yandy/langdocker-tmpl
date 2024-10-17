# build stage
FROM maven:3-eclipse-temurin-21-alpine AS build

COPY docker/settings.xml /root/.m2/settings.xml

COPY . /app

WORKDIR /app

RUN --mount=type=cache,target=/root/.m2/repository set -eux; mvn package -Dmaven.test.skip=true

# package stage
FROM eclipse-temurin:21-jre-alpine

COPY --chmod=755 docker/entrypoint.sh /entrypoint.sh
COPY --from=build /app/target/app.jar /opt/app.jar

ENTRYPOINT [ "/entrypoint.sh" ]
CMD [ "/opt/app.jar" ]
