# Docker build

## Multi-platform Docker builds

Use the below commands to build the images for multiple platforms (i.e. `amd64` and `arm64`).  This requires the use of [BuildKit](https://docs.docker.com/build/buildkit/).

Create a custom builder: 

```sh
docker run --rm --privileged multiarch/qemu-user-static --reset -p yes
docker buildx create --name multiarch --driver docker-container --use
docker buildx inspect --bootstrap
```

Build images:

```sh
docker buildx build  -f client/Dockerfile --platform linux/arm64,linux/amd64 \
  --tag <repo>/dcrdex  \
  --output "type=registry" .
```

