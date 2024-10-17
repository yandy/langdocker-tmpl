# nodejs docker env template

## dev

use vscode dev container extention

open in vscode, invoke 'rebuild and reopen in container'

## deploy

```
docker build -t image:tag .
docker run -p xxx:80 image:tag
```
