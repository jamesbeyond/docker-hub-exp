# Base Docker image
FROM ubuntu:20.04

# Set Environment Variable
ENV DEBIAN_FRONTEND=noninteractive

# Install packages via apt-get
RUN set -x \
    && apt-get -y update \
    && apt-get -y install git \
    wget \
    curl \
    python3=3.8.2-0ubuntu2 \
    python3-pip \
    awscli \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists \
    && : # last line

# Install Python modules via pip3
RUN set -x \
    && pip3 install -U \
    mbed-os-tools \
    && : # last line

