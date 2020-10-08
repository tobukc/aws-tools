# aws-tools

A docker image for AWS tools:

- aws-cli
- aws-sam-cli

### Usage

**aws-cli**

```
docker run --rm -it \
  -v "$HOME/.aws":/home/aws/.aws \
  -v "$PWD":/aws \
  phelucko/aws-tools aws [arguments]
```

**aws-sam-cli**

```
docker run --rm -it \
  --network="host" \
  -v "$HOME/.aws":/home/aws/.aws \
  -v "$PWD":/aws \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -e DOCKER_HOST_GID=$(getent group docker | cut -d: -f3) \
  phelucko/aws-tools sam [arguments]
```
