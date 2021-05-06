# Base Docker image
FROM ubuntu:20.04

# Set Environment Variable
ENV DEBIAN_FRONTEND=noninteractive

# Install packages via apt-get
RUN set -x \
    && apt-get -y update \
    && apt-get -y install git \
    wget \
    python3=3.8.2-0ubuntu2 \
    python3-pip \
    clang-format \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists \
    && : # last line

# Install Python modules via pip3
RUN set -x \
    && pip3 install -U \
    cmake==3.18.4 \
    && : # last line
    
    
# Download and Install arm-none-eabi-gcc
RUN set -x \
    && wget -q -O /tmp/arm-gcc-9-2019-q4.tar.bz2 https://developer.arm.com/-/media/Files/downloads/gnu-rm/9-2019q4/RC2.1/gcc-arm-none-eabi-9-2019-q4-major-x86_64-linux.tar.bz2 \
    && tar -xjf /tmp/arm-gcc-9-2019-q4.tar.bz2 -C /opt \
    && rm /tmp/arm-gcc-9-2019-q4.tar.bz2 \
    && : # last line
ENV PATH=/opt/gcc-arm-none-eabi-9-2019-q4-major/bin:$PATH

