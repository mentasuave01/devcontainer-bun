ARG VARIANT=latest
# Get latest Bun from docker Hub
FROM oven/bun:${VARIANT}

# Install required system packages
RUN apt-get update && apt-get install -y \
    curl \
    git \
    nano \
    && rm -rf /var/lib/apt/lists/* \
    && apt-get clean

# Set up nvm environment
ENV NVM_DIR /usr/local/nvm
ENV NODE_VERSION lts/*

# Install nvm
RUN rm /bin/sh && ln -s /bin/bash /bin/sh
RUN mkdir -p $NVM_DIR \
    && curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash \
    && . $NVM_DIR/nvm.sh 

# install Node.js
RUN nvm install $NODE_VERSION 

# Change the shell prompt
ENV PS1="bun:\\w# "

# Set username
USER developer

WORKDIR /com.docker.devenvironments.code/
