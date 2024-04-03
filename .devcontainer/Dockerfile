ARG VARIANT=latest
# Get latest Bun from docker Hub
FROM oven/bun:${VARIANT}

# Update and install required packages
RUN apt-get update \
    && apt-get -y install --no-install-recommends \
    git \
    nano \
    zsh \
    && apt-get auto-remove -y \
    && apt-get clean -y

# Change the shell prompt
ENV PS1="bun:\\w# "

# Optionally, set Zsh as the default shell if desired
RUN chsh -s $(which zsh)

# Set username
USER developer

WORKDIR /com.docker.devenvironments.code/
