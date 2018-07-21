FROM ubuntu:16.04

MAINTAINER Tapasweni Pathak

RUN apt update
RUN echo | apt install curl gcc libc-dev make --no-install-recommends

ADD https://ftp.gnu.org/gnu/gcc/gcc-8.1.0/gcc-8.1.0.tar.gz /gcc-8.1.0.tar.gz
RUN tar xf gcc-8.1.0.tar.gz \
	&& cd gcc-8.1.0 \
	&& contrib/download_prerequisites \
  && ./configure -v --build=x86_64-linux-gnu --prefix=/usr/local/gcc-8.1 --enable-checking=release --enable-languages=c,c++,fortran --disable-multilib --program-suffix=-8.1 \
	&& make -j"$(nproc)" \
	&& make install
