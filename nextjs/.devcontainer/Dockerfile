FROM node:20-alpine AS base

RUN set -eux; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make


# for dev
FROM base AS dev

RUN set -eux; \
    apk add --no-cache openssh-client-default
