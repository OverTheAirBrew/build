ARG NODE_VERSION="8"
FROM node:${NODE_VERSION}

WORKDIR /

RUN apt-get update && \
    apt-get install -y \
    git \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common 

# Docker
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - 
RUN add-apt-repository \
    "deb [arch=amd64] https://download.docker.com/linux/debian \
    $(lsb_release -cs) \
    stable"
RUN apt-get update && apt-get install -y docker-ce
