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
RUN export GOROOT=/usr/local/go
RUN export GOPATH=/workspaces/${GO_PROJECT}
RUN export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
RUN echo "export GOROOT=/usr/local/go\n" >> ~/.profile
RUN echo "export GOPATH=/workspaces/${GO_PROJECT}\n" >> ~/.profile
RUN echo "export PATH=$GOPATH/bin:$GOROOT/bin:$PATH\n" >> ~/.profile


# LABEL and EXPOSE to document runtime settings
LABEL maintainer="justin.dynamicd@gmail.com"
LABEL description="go-env"
