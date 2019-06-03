# Node 4dev

[![docker-4dev](http://dockeri.co/image/seudev/node-4dev)](https://hub.docker.com/r/seudev/node-4dev)

## What is it?

A Docker image for developers that use node

# Resources

This image has the below resources:

* openssh
* git
* [Nwb](https://github.com/insin/nwb)
* [Firebase Tools](https://firebase.google.com/docs/cli)
* [Surge](https://surge.sh)
* Shell Scripts
  * [add-ssh-key](https://github.com/seudev/env-config#add-ssh-key)
  * [set-git-config](https://github.com/seudev/env-config#set-git-config)
  * [get-git-target-branch](https://github.com/seudev/env-config#get-git-target-branch)

## Using Node 4dev

```sh
docker run -ti --rm -p 3000:3000 -v `pwd`:/usr/src/app seudev/node-4dev:1.0-alpine
```

### Using to deploy on Firebase

```
docker run -ti --rm -p 3000:3000 -e FIREBASE_TOKEN="$FIREBASE_TOKEN" -v `pwd`:/usr/src/app seudev/node-4dev:1.0-alpine
```

Executes in the container:

```
firebase deploy --token "$FIREBASE_TOKEN"
```

### Using to deploy on Surge

```
docker run -ti --rm -p 3000:3000 -e SURGE_TOKEN="$SURGE_TOKEN" -v `pwd`:/usr/src/app seudev/node-4dev:1.0-alpine
```

Executes in the container:

```
surge --token "$SURGE_TOKEN" --domain my-project.surge.sh --project build
```

### Building this image:

```
docker build -t seudev/node-4dev:1.0-alpine .
```

## Licensing

**seudev/docker-4dev** is provided and distributed under the [Apache Software License 2.0](http://www.apache.org/licenses/LICENSE-2.0).

Refer to *LICENSE* for more information.
