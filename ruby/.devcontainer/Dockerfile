FROM ruby:3-alpine

RUN set -eux; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make; \
    gem sources --remove https://rubygems.org/ ; \
    gem sources -a https://mirrors.aliyun.com/rubygems/ ; \
    bundle config set path .bundle

