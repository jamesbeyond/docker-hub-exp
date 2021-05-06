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

# Install cmake 3.20 - refer https://cmake.org/install/
RUN set -x \
    && wget https://github.com/Kitware/CMake/releases/download/v3.20.0-rc2/cmake-3.20.0-rc2-linux-x86_64.sh \
    && chmod +x cmake-3.20.0-rc2-linux-x86_64.sh \
    && sh cmake-3.20.0-rc2-linux-x86_64.sh --exclude-subdir --prefix=/usr/local \
    && rm cmake-3.20.0-rc2-linux-x86_64.sh \
    && : # last line
   
    
# Download and Install arm-none-eabi-gcc
RUN set -x \
    && wget -q -O /tmp/arm-gcc-9-2019-q4.tar.bz2 https://developer.arm.com/-/media/Files/downloads/gnu-rm/9-2019q4/RC2.1/gcc-arm-none-eabi-9-2019-q4-major-x86_64-linux.tar.bz2 \
    && tar -xjf /tmp/arm-gcc-9-2019-q4.tar.bz2 -C /opt \
    && rm /tmp/arm-gcc-9-2019-q4.tar.bz2 \
    && : # last line
ENV PATH=/opt/gcc-arm-none-eabi-9-2019-q4-major/bin:$PATH

