FROM ubuntu:noble as build

WORKDIR /tmp

RUN \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get install -y build-essential curl libncurses-dev git libjemalloc-dev openssl libssl-dev python3 python3-pip python3.12-venv python3-sphinx liblz4-dev && \
  apt-get install -y python3-sphinx-bootstrap-theme python3-sphinx-autobuild python3-docutils python3-ndg-httpsclient python3-jinja2 && \
  apt-get install -y ninja-build cmake mono-devel && \
  apt-get install -y openjdk-21-jdk openjdk-21-doc golang ruby

RUN \
  curl -fLs https://download.swift.org/swift-5.10-release/ubuntu2204-$(uname -m)/swift-5.10-RELEASE/swift-5.10-RELEASE-ubuntu22.04-$(uname -m).tar.gz -o latest-toolchain.tar.gz && \
  tar -xzf latest-toolchain.tar.gz --directory / --strip-components=1 && \
  chmod -R o+r /usr/lib/swift