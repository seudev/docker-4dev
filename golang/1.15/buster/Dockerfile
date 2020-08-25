ARG VARIANT="1.15-buster"
FROM golang:${VARIANT}

LABEL vendor="Seudev" \
    homepage="http://docker-4dev.seudev.com" \
    author="Thomás Sousa Silva <thomassousa.dev>"

RUN apt-get update && apt-get install -y \
    ssh \
    git \
    && rm -rf /var/lib/apt/lists/*

RUN go get -u github.com/spf13/cobra/cobra \
    && go clean --modcache

ARG ENV_CONFIG_VERSION="v1.2.0"

ARG SCRIPT_ADD_SSH_KEY="https://raw.githubusercontent.com/seudev/env-config/${ENV_CONFIG_VERSION}/bin/ssh/add-ssh-key"
ADD $SCRIPT_ADD_SSH_KEY /usr/local/bin/

ARG SCRIPT_SET_GIT_CONFIG="https://raw.githubusercontent.com/seudev/env-config/${ENV_CONFIG_VERSION}/bin/git/set-git-config"
ADD $SCRIPT_SET_GIT_CONFIG /usr/local/bin/

ARG SCRIPT_GET_GIT_TARGET_BRANCH="https://raw.githubusercontent.com/seudev/env-config/${ENV_CONFIG_VERSION}/bin/git/get-git-target-branch"
ADD $SCRIPT_GET_GIT_TARGET_BRANCH /usr/local/bin/

ARG SCRIPT_UPDATE_BUILD_BRANCH="https://raw.githubusercontent.com/seudev/env-config/${ENV_CONFIG_VERSION}/bin/git/update-build-branch"
ADD $SCRIPT_UPDATE_BUILD_BRANCH /usr/local/bin/

ARG SCRIPT_HASH_DIR="https://raw.githubusercontent.com/seudev/env-config/${ENV_CONFIG_VERSION}/bin/helpers/hash-dir"
ADD $SCRIPT_HASH_DIR /usr/local/bin/

RUN chmod +x \
    /usr/local/bin/add-ssh-key \
    /usr/local/bin/set-git-config \
    /usr/local/bin/get-git-target-branch \
    /usr/local/bin/update-build-branch \
    /usr/local/bin/hash-dir

ENV WORKDIR=/usr/src/app

WORKDIR $WORKDIR

CMD ["bash"]
