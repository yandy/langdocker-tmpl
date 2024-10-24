FROM node:20-alpine as base

# build stage
FROM base as builder

RUN set -eux; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git g++ gcc make

COPY . /app

WORKDIR /app

RUN --mount=type=cache,target=/app/node_modules set -eux; \
    npm config set registry https://registry.npmmirror.com; \
    npm install; npm run build

# statc serve stage
FROM base AS runner
WORKDIR /app

COPY --from=builder /app/public ./public

COPY --from=builder /app/.next/standalone ./
COPY --from=builder /app/.next/static ./.next/static

CMD ["node", "server.js"]
