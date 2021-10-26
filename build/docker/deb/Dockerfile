# initialize from the image

FROM blockbook-build:latest

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y devscripts systemd debhelper make dh-exec && \
    ( apt-get install -y -o Dpkg::Options::=--force-unsafe-io dh-systemd || true ) && \
    apt-get clean

ADD gpg-keys /tmp/gpg-keys
RUN gpg --batch --import /tmp/gpg-keys/*

ADD build-deb.sh /build/build-deb.sh

WORKDIR /build
