# ekwing/node

## Build
```bash
docker build \
  --tag=ekwing/node:12.2.0 \
  --add-host=npm.ekwing.com:172.20.0.1 \
  --build-arg NODE_VERSION=12.2.0 \
  --build-arg YARN_VERSION=1.16.0 \
  --compress \
  .
```
