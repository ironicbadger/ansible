FROM debian:jessie
MAINTAINER IronicBadger <ironicbadger@linuxserver.io>

# Builds SnapRAID from source
RUN apt-get update && \
  apt-get upgrade -y && \
  apt-get install -y \
    gcc \
    git \
    make \
    checkinstall \
    curl && \
  curl -LO https://github.com/amadvance/snapraid/releases/download/v9.1/snapraid-9.1.tar.gz && \
  tar -xvf snapraid-9.1.tar.gz && \
  cd snapraid-9.1 && \
  ./configure && \
  make -j8 && \
  make -j8 check && \
  checkinstall -Dy --install=no --nodoc && \
  mkdir /artifact && \
  cp *.deb /artifact/snapraid-from-source.deb
