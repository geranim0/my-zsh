#-------------------------------------------------------------------------------------------------------------
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License. See https://go.microsoft.com/fwlink/?linkid=2090316 for license information.
#-------------------------------------------------------------------------------------------------------------

# To fully customize the contents of this image, use the following Dockerfile instead:
# https://github.com/microsoft/vscode-dev-containers/tree/v0.106.0/containers/alpine-3.10-git/.devcontainer/Dockerfile
#FROM mcr.microsoft.com/vscode/devcontainers/base:0-alpine-3.10

# ** [Optional] Uncomment this section to install additional packages. **
#
# RUN apk update \
#     && apk add --no-cache <your-package-list-here>
FROM ubuntu:18.04

RUN \
    apt-get update && \
    apt-get -y upgrade && \
    apt-get -y install sudo git && \
    cd ~root && \
    git clone https://github.com/geranim0/my-zsh.git && \
    cd my-zsh && \
    ./install.sh && \
    /bin/zsh --login -c "/bin/zsh ~/my-zsh/.zshrc" && \
    apt-get clean && \
    apt-get autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/cache/* && \
    rm -rf /var/lib/log/*

ENTRYPOINT ["/bin/zsh"] 