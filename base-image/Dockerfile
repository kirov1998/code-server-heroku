FROM codercom/code-server:latest

USER root

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
    bzip2 \
    curl \
    default-jdk \
    dumb-init \
    htop \
    locales \
    man \
    nano \
    git \
    procps \
    ssh \
    sudo \
    vim \
    wget

USER coder

# Apply VS Code settings
COPY settings.json .local/share/code-server/User/settings.json

# Use bash shell
ENV SHELL=/bin/bash

# Use our custom entrypoint script first
COPY heroku-entrypoint.sh /usr/bin/heroku-entrypoint.sh
ENTRYPOINT ["/usr/bin/heroku-entrypoint.sh"]
