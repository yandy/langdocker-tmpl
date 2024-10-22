FROM node:20-alpine

RUN set -eux; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make

COPY --chmod=755 devinit /devinit

RUN set -eux; \
    apk add --no-cache openssh-client-default
