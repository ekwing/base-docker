# ekwing/node

## Build
```bash
docker build \
  --tag=ekwing/node:12.2.0 \
  --build-arg ARG_ALPINE_VERSION=3.9 \
  --build-arg ARG_NODE_VERSION=12.2.0 \
  --build-arg ARG_YARN_VERSION=1.16.0 \
  --compress \
  .
```
