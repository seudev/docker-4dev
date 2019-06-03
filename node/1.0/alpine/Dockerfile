FROM node:10-alpine

LABEL vendor="Seudev" \
      homepage="http://docker-4dev.seudev.com" \
      author="Thomás Sousa Silva <thomassousa.dev>"

RUN apk add --no-cache openssh \
    && apk add --no-cache git \
    && rm -rf /var/cache/apk/*

RUN npm i -g --unsafe-perm nwb
RUN npm i -g firebase-tools
RUN npm i -g surge

ARG ENV_CONFIG_VERSION=v1.0.0

ARG SCRIPT_ADD_SSH_KEY="https://raw.githubusercontent.com/seudev/env-config/${ENV_CONFIG_VERSION}/bin/ssh/add-ssh-key"
ADD $SCRIPT_ADD_SSH_KEY /usr/local/bin/

ARG SCRIPT_SET_GIT_CONFIG="https://raw.githubusercontent.com/seudev/env-config/${ENV_CONFIG_VERSION}/bin/git/set-git-config"
ADD $SCRIPT_SET_GIT_CONFIG /usr/local/bin/

ARG SCRIPT_GET_GIT_TARGET_BRANCH="https://raw.githubusercontent.com/seudev/env-config/${ENV_CONFIG_VERSION}/bin/git/get-git-target-branch"
ADD $SCRIPT_GET_GIT_TARGET_BRANCH /usr/local/bin/

RUN chmod +x \
    /usr/local/bin/add-ssh-key \
    /usr/local/bin/set-git-config \
    /usr/local/bin/get-git-target-branch

WORKDIR /usr/src/app

CMD ["sh"]
