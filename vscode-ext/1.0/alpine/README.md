# VSCode ext 4dev

[![docker-4dev](http://dockeri.co/image/seudev/vscode-ext-4dev)](https://hub.docker.com/r/seudev/vscode-ext-4dev)

## What is it?

A Docker image for create VSCode extensions

# Resources

This image has the below resources:

* [yo](https://www.npmjs.com/package/yo)
* [generator-code](https://www.npmjs.com/package/generator-code)
* [vsce](https://www.npmjs.com/package/vsce)

## Using VSCode ext 4dev

```sh
docker run -ti --rm -v `pwd`:/usr/src/app seudev/vscode-ext-4dev:1.0-alpine
```

### Building this image:

```sh
docker build -t seudev/vscode-ext-4dev:1.0-alpine .
```

## Licensing

**seudev/docker-4dev** is provided and distributed under the [Apache Software License 2.0](http://www.apache.org/licenses/LICENSE-2.0).

Refer to *LICENSE* for more information.
