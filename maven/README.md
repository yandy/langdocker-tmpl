# maven docker env template

## dev

use vscode dev container extention

open in vscode, invoke 'rebuild and reopen in container'

open integrated terminal and run commands (eg. `mvn package`)


## deploy

```
docker build -t image:tag .
docker run image:tag
```
