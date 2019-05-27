# Node 4dev

## What is it?

A Docker image for developers that use node

# Resources

This image has the below resources:

* openssh
* git
* [Nwb](https://github.com/insin/nwb)
* [Firebase Tools](https://firebase.google.com/docs/cli)
* Shell Scripts
  * [add-ssh-key](https://github.com/seudev/env-config#add-ssh-key)
  * [set-git-config](https://github.com/seudev/env-config#set-git-config)
  * [get-git-target-branch](https://github.com/seudev/env-config#get-git-target-branch)

## Using Node 4dev

```
docker run -ti --rm -p 3000:3000 -v `pwd`:/usr/src/app seudev/node-4dev:1.0-alpine
```

### Building this image:

```
docker build -t seudev/node-4dev:1.0-alpine .
```

## Licensing

**seudev/docker-4dev** is provided and distributed under the [Apache Software License 2.0](http://www.apache.org/licenses/LICENSE-2.0).

Refer to *LICENSE* for more information.
