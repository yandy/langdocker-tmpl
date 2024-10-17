# maven docker env template

## dev

use [sdkman](https://sdkman.io/)

usage

```sh
sdk list java  # 列出java版本
sdk install java 21.0.4-tem  # 安装特定java版本
sdk uninstall java 21.0.4-tem  # 卸载特定java本本
sdk use java 21.0.4-tem  # 启用特定java版本
sdk install maven # 安装最新的 maven
sdk env init  # 生成 .sdkmanrc 文件，用于切换环境(启用的版本等)
sdk env # 根据 .sdkmanrc 切换环境

sdk config # 打开配置文件，修改 sdkman_auto_env=true，自动 sdk env
```


## deploy

```
docker build -t image:tag .
docker run -p xxx:80 image:tag
```
