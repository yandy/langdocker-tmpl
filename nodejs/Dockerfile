# build stage
FROM node:20-alpine as buildor

COPY . /app

WORKDIR /app

RUN set -eux; \
    sed -i "s@dl-cdn.alpinelinux.org@mirrors.aliyun.com@g" /etc/apk/repositories; \
    apk add --no-cache curl git; \
    npm config set registry https://registry.npmmirror.com; \
    npm install; npm run build

# production stage
FROM nginx:1.26-alpine
# 将项目根目录下dist文件夹（构建之后才会生成）下的所有文件复制到镜像/usr/share/nginx/html/目录下
COPY --from=buildor /app/dist /usr/share/nginx/html
