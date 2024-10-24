FROM node:20-alpine

RUN set -eux; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make

RUN set -eux; \
    apk add --no-cache openssh-client-default
