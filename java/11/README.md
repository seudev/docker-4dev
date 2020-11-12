# Java 4dev

[![java-4dev](http://dockeri.co/image/seudev/java-4dev)](https://hub.docker.com/r/seudev/java-4dev)

## What is it?

A Docker image for developers that use Java

# Resources

This image has the below resources:

* ssh
* git
* vim
* Shell Scripts
  * [add-ssh-key](https://github.com/seudev/env-config/tree/v1.2.0#add-ssh-key)
  * [set-git-config](https://github.com/seudev/env-config/tree/v1.2.0#set-git-config)
  * [get-git-target-branch](https://github.com/seudev/env-config/tree/v1.2.0#get-git-target-branch)
  * [update-build-branch](https://github.com/seudev/env-config/tree/v1.2.0#update-build-branch)
  * [hash-dir](https://github.com/seudev/env-config/tree/v1.2.0#hash-dir)

## Using Java 4dev

```sh
docker run -ti --rm -p 8080:8080 -v `pwd`:/usr/src/app seudev/java-4dev:11
```

### Using to commit with local config

```sh
docker run -ti --rm -p 8080:8080 -e GIT_USER_NAME="$(git config --get user.name)" -e GIT_USER_EMAIL="$(git config --get user.email)" -v `pwd`:/usr/src/app seudev/java-4dev:11
```

Execute in the container:

```sh
set-git-config
```

### Building this image:

```sh
docker build -t seudev/java-4dev:11 .
```

## Licensing

**seudev/docker-4dev** is provided and distributed under the [Apache Software License 2.0](http://www.apache.org/licenses/LICENSE-2.0).

Refer to *LICENSE* for more information.
