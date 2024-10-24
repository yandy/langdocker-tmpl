FROM maven:3-eclipse-temurin-21-alpine AS base

RUN set -eux; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make


# for dev
FROM base AS dev

RUN set -eux; \
    addgroup -g 1000 java; \
    adduser -u 1000 -G java -s /bin/sh -D java \
    ; \
    apk add --no-cache openssh-client-default
