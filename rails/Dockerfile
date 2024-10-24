FROM ruby:3-alpine AS base

RUN set -eux; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make


# for deploy
FROM base AS runner

WORKDIR /app

COPY Gemfile Gemfile.lock ./
COPY --chmod=755 docker/config-deploy /docker-config

RUN --mount=type=cache,target=/root/.bundle/cache set -eux; \
    /docker-config ; \
    bundle install

COPY . /app
