# Use the latest Ubuntu image from the Docker Hub
FROM ubuntu:latest

# Set environment variable to make apt-get install non-interactive
ENV DEBIAN_FRONTEND=noninteractive
# Set the timezone
ENV TZ=Etc/UTC
# Update the package list and install basic packages
RUN apt-get update && apt-get install -y \
    build-essential \
    curl \
    wget \
    git \
    vim \
    cmake \
    gcc \
    xorg-dev \
    libglu1-mesa-dev \
    zlib1g-dev \
    libbz2-dev \
    liblzma-dev \
    libglfw3 \
    libglfw3-dev \
    autoconf \
    curl \
    libcrypto++-dev \
    libdeflate-dev \
    libfontconfig-dev \
    libhts-dev


# Set the working directory
WORKDIR /opt

RUN git clone https://github.com/kcleal/gw.git
WORKDIR /opt/gw
RUN make prep && make -j4
RUN cp gw /usr/local/bin

RUN gw --version

CMD [ "gw" ]