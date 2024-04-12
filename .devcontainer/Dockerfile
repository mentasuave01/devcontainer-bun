ARG VARIANT=latest
# Get latest Bun from docker Hub
FROM oven/bun:${VARIANT}

# Update and install required packages
RUN apt-get update \
    && apt-get -y install --no-install-recommends \
    curl \       
    git \
    nano \
    zsh \
    && apt-get auto-remove -y \
    && apt-get clean -y

# Change the shell prompt
ENV PS1="bun:\\w# "

# Optionally, set Zsh as the default shell if desired
RUN chsh -s $(which zsh)

# Installing Node.js 
ENV NVM_DIR /usr/local/nvm
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash \
    && . $NVM_DIR/nvm.sh \
    && nvm install --lts

# Set username
USER dev

WORKDIR /com.docker.devenvironments.code/
