###
# start builder
###

# starting image to customize
FROM ubuntu:18.04

ARG GO_VER=1.15.1
ARG GO_PROJECT=learn-go

# Prepare common tools
RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get install -y curl unzip wget git lsb-release software-properties-common

# Install Go
RUN wget https://dl.google.com/go/go${GO_VER}.linux-amd64.tar.gz
RUN tar -xvf go${GO_VER}.linux-amd64.tar.gz
RUN mv go /usr/local

ENV GOROOT /usr/local/go
ENV GOPATH /workspaces/${GO_PROJECT}
ENV PATH $GOPATH/bin:$GOROOT/bin:$PATH

# LABEL and EXPOSE to document runtime settings
LABEL maintainer="justin.dynamicd@gmail.com"
LABEL description="go-env"
