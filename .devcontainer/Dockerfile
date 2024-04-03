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

# Add group and user
RUN groupadd --gid 1000 developer \
    && useradd --uid 1000 --gid developer --shell /bin/zsh --create-home developer

# Change the prompt in the .bashrc and .zshrc 
RUN echo 'export PS1="/com.docker.devenvironments.code/ "' >> /home/developer/.bashrc \
    && echo 'export PS1="/com.docker.devenvironments.code/ "' >> /home/developer/.zshrc

# Set username
USER developer

WORKDIR /com.docker.devenvironments.code/
