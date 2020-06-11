ARG NODE_VERSION="8"
FROM node:${NODE_VERSION}

WORKDIR /

RUN apt-get update && \
    apt-get install -y \
    git \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common  \
    libcurl3

# Git Version
RUN wget https://github.com/GitTools/GitVersion/releases/download/5.3.5/gitversion-debian.9-x64-5.3.5.tar.gz
RUN tar -zxvf gitversion-debian.9-x64-5.3.5.tar.gz

RUN mv ./gitversion /bin/gitversion 
RUN chmod +x /bin/gitversion

# Docker
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - 
RUN add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/debian \
    $(lsb_release -cs) \
    stable"
RUN apt-get update && apt-get install -y docker-ce
