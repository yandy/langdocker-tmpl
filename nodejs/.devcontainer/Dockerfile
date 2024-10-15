FROM node:20-alpine

RUN set -eux; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git; \
    npm config set registry https://registry.npmmirror.com
