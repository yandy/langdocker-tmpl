# nextjs docker env template

## dev

use vscode dev container extention

open in vscode, invoke 'rebuild and reopen in container'

invoke: `npm run dev`

## deploy

**normal deploy**
```sh
docker build -t image:tag .
docker run -p xxx:3000 image:tag
```

**static deploy**
```sh
docker build -f Dockerfile.static -t image:tag .
docker run -p xxx:80 image:tag
```
