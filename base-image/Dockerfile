FROM codercom/code-server:latest

USER root

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
    bzip2 \
    zip \
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
    wget \
    inetutils-ping \
    net-tools \
    nginx
RUN wget https://github.com/fatedier/frp/releases/download/v0.43.0/frp_0.43.0_linux_amd64.tar.gz

USER coder

# Apply VS Code settings
COPY settings.json .local/share/code-server/User/settings.json

# Use bash shell
ENV SHELL=/bin/bash

# Use our custom entrypoint script first
COPY heroku-entrypoint.sh /usr/bin/heroku-entrypoint.sh
ENTRYPOINT ["/usr/bin/heroku-entrypoint.sh"]
