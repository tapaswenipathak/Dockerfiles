FROM ubuntu:16.04

MAINTAINER Tapasweni Pathak

RUN apt update
RUN echo | apt-get install --no-install-recommends \
    ssh \
    python \
    python-pip \
    python-virtualenv \
    vim \
    zip

WORKDIR /home/aws

USER root

RUN mkdir aws && \
    python -m pip install --upgrade pip && \
    pip install --upgrade virtualenv && \
    virtualenv aws/env && \
    ./aws/env/bin/pip install awscli && \
    echo 'source $HOME/aws/env/bin/activate' >> .bashrc
