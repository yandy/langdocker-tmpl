FROM ruby:3-alpine

RUN set -eux; \
    addgroup -g 1000 ruby; \
    adduser -u 1000 -G ruby -s /bin/sh -D ruby \
    ; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make

COPY --chmod=755 devinit /devinit
