FROM ruby:3-alpine

RUN set -eux; \
    addgroup -g 1000 ruby; \
    adduser -u 1000 -G ruby -s /bin/sh -D ruby \
    ; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make

COPY . /app

WORKDIR /app

RUN set -eux; \
    gem sources --remove https://rubygems.org/ ; \
    gem sources -a https://mirrors.aliyun.com/rubygems/ ; \
    bundle config set mirror.http://rubygems.org https://mirrors.aliyun.com/rubygems/ ; \
    bundle config set path .bundle ; \
    bundle install
