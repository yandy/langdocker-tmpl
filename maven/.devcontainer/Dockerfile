FROM maven:3-eclipse-temurin-21-alpine AS build

RUN set -eux; \
    addgroup -g 1000 java; \
    adduser -u 1000 -G java -s /bin/sh -D java \
    ; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make

RUN --mount=type=cache,target=/root/.m2/repository set -eux; mvn package -Dmaven.test.skip=true

RUN set -eux; \
    apk add --no-cache openssh-client-default
