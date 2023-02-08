## Publishing the docker image

The `dcrdex` image can be built and published to Docker Hub using the following steps.  This requires the use of [BuildKit](https://docs.docker.com/build/buildkit/), which is part of recent docker releases.

1. Log in to Docker Hub using the credentials that has write access to https://hub.docker.com/u/decred

```bash
docker login
```

2. Build the image

```bash
git clone https://github.com/decred/dcrdex
cd dcrdex
git checkout release-v0.5
docker buildx create --use
docker buildx build -f client/Dockerfile \
  --platform linux/arm64,linux/amd64 \
  --tag decred/dcrdex:v0.5.8 \
  --output "type=registry"  .
```

This is a multi-platform (targeting `amd64` and `arm64`) build which takes longer, this is normal.  
If there are no error messages, at the end of the build the image will be published to Docker.

3. Verify that the image has been published on https://hub.docker.com/r/decred/dcrdex/tags.  There should be 2 digest lines; these indicate that both target platforms have been built and are included in the published image.
