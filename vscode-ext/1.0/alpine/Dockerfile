FROM node:12-alpine

LABEL vendor="Seudev" \
    homepage="http://docker-4dev.seudev.com" \
    author="Thomás Sousa Silva <thomassousa.dev>"

RUN npm i -g yo generator-code vsce

USER node

WORKDIR /usr/src/app

CMD ["sh"]
