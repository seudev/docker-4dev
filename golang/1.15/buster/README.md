# Golang 4dev

[![golang-4dev](http://dockeri.co/image/seudev/golang-4dev)](https://hub.docker.com/r/seudev/golang-4dev)

## What is it?

A Docker image for developers that use Golang

# Resources

This image has the below resources:

* ssh
* git
* [gopls](https://github.com/golang/tools/tree/master/gopls)
* [delve](https://github.com/go-delve/delve)
* [cobra](https://github.com/spf13/cobra)
* [go-bindata](https://github.com/go-bindata/go-bindata)
* Shell Scripts
  * [add-ssh-key](https://github.com/seudev/env-config/tree/v1.2.0#add-ssh-key)
  * [set-git-config](https://github.com/seudev/env-config/tree/v1.2.0#set-git-config)
  * [get-git-target-branch](https://github.com/seudev/env-config/tree/v1.2.0#get-git-target-branch)
  * [update-build-branch](https://github.com/seudev/env-config/tree/v1.2.0#update-build-branch)
  * [hash-dir](https://github.com/seudev/env-config/tree/v1.2.0#hash-dir)

## Using Golang 4dev

```sh
docker run -ti --rm -v `pwd`:/usr/src/app seudev/golang-4dev:1.15-buster
```

### Using to commit with local config

```sh
docker run -ti --rm -e GIT_USER_NAME="$(git config --get user.name)" -e GIT_USER_EMAIL="$(git config --get user.email)" -v `pwd`:/usr/src/app seudev/golang-4dev:1.15-buster
```

Execute in the container:

```sh
set-git-config
```

### Building this image:

```sh
docker build -t seudev/golang-4dev:1.15-buster .
```

## Licensing

**seudev/docker-4dev** is provided and distributed under the [Apache Software License 2.0](http://www.apache.org/licenses/LICENSE-2.0).

Refer to *LICENSE* for more information.
