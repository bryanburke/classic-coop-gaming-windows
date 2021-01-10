FROM node:14-buster

COPY system.pkgs ./
RUN set -eux \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
    && apt-get --assume-yes --no-install-recommends install apt-utils dialog \
    && cat system.pkgs | sed 's/#.*$//' \
        | xargs -E "" apt-get --assume-yes --no-install-recommends install \
    && apt-get --assume-yes --auto-remove \
        --option APT::AutoRemove::RecommendsImportant=false purge \
    && apt-get --assume-yes clean \
    && rm -rf /var/lib/apt/lists/* \
    && rm -f system.pkgs \
    \
    && rm -f /usr/local/bin/docker-entrypoint.sh \
    && userdel --remove node

ARG USER_NAME=dev
ARG USER_UID=1000
ARG USER_GID=${USER_UID}
RUN set -eux \
    && groupadd --gid "${USER_GID}" "${USER_NAME}" \
    && useradd --create-home --gid "${USER_GID}" --shell /bin/bash \
        --uid "${USER_UID}" "${USER_NAME}"

USER ${USER_NAME}
WORKDIR /home/${USER_NAME}

ARG LOCAL_PREFIX=/home/${USER_NAME}/.local
ENV NODE_ENV=dev \
    NODE_PATH=${LOCAL_PREFIX}/npm/lib/node_modules \
    NPM_CONFIG_PREFIX=${LOCAL_PREFIX}/npm
ENV PATH=${NPM_CONFIG_PREFIX}/bin:${LOCAL_PREFIX}/bin:${PATH}

ARG HIST_PREFIX=/home/${USER_NAME}/.history
RUN set -eux \
    && mkdir -p "${HIST_PREFIX}" \
    && { \
        printf "%s\n" "HISTFILE=${HIST_PREFIX}/.bash_history"; \
        printf "%s\n" "PROMPT_COMMAND='history -a'"; \
        printf "%s\n" 'PATH=${NPM_CONFIG_PREFIX}/bin:${PATH}'; \
    } >>"/home/${USER_NAME}/.profile"

COPY npm.pkgs ./
RUN set -eux \
    && cat npm.pkgs | sed 's/#.*$//' | xargs -E "" npm install --global \
    && npm cache clean --force \
    && rm -f npm.pkgs

ENTRYPOINT []
CMD ["/bin/bash", "--login"]
