FROM ubuntu:16.04

MAINTAINER Tapasweni Pathak

RUN apt update
RUN echo | apt-get install  --no-install-recommends \
    autoconf \
    automake \
    build-essential \
    git \
    libgmp-dev \
    libmpc-dev \
    libmpfr-dev \
    libsqlite3-dev \
    m4 \
    opam \
    openjdk-8-jdk \
    unzip \
    zlib1g-dev \
    rsync \
    pkg-config \
    libncurses-dev \
    python \
    aspcud && \
    rm -rf /var/lib/apt/lists/*

RUN echo | curl -sL git@github.com:facebook/infer.git && cd infer && ./build-infer.sh java

RUN echo | sudo make install

RUN export PATH=`pwd`/infer/bin:$PATH
