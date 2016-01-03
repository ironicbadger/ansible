FROM debian:jessie
MAINTAINER IronicBadger <ironicbadger@linuxserver.io>

# Builds MergerFS from source
RUN apt-get update && \
  apt-get upgrade -y && \
  apt-get install -y \
    g++ \
    pkg-config \
    git \
    git-buildpackage \
    pandoc \
    debhelper \
    libfuse-dev \
    libattr1-dev && \
  git clone https://github.com/trapexit/mergerfs.git && \
  cd mergerfs && \
  make clean && \
  make deb && \
  mkdir /artifact/ && \
  cp /*.deb /artifact/mergerfs-from-source.deb
