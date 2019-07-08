# ekwing/node

## Build
```bash
docker build \
  --tag=ekwing/node:12.2.0 \
  --build-arg ALPINE_VERSION=3.9 \
  --build-arg NODE_VERSION=12.2.0 \
  --build-arg YARN_VERSION=1.16.0 \
  --compress \
  .
```
