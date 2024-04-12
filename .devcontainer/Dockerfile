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
ENV SHELL /bin/zsh

# Install nvm
RUN rm /bin/sh && ln -s /bin/bash /bin/sh
RUN mkdir -p $NVM_DIR \
    && curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash 

# install Node.js
RUN nvm install $NODE_VERSION 

# Change the shell prompt
ENV PS1="bun:\\w# "

# Optionally, set Zsh as the default shell if desired
RUN chsh -s $(which zsh)

# Set username
USER developer

WORKDIR /com.docker.devenvironments.code/
