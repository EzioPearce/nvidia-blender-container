FROM nvidia/cuda:11.4.1-devel-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive
ARG OPENCV_VERSION=4.5.3

RUN apt-get update && apt-get upgrade -y && \
    # Install build tools and build dependencies
    apt-get install -y \
	python3-pip \
        build-essential \
        cmake \
        git \
        wget \
        unzip \
        yasm \
        pkg-config \
        libswscale-dev \
        libtbb2 \
        libtbb-dev \
        libjpeg-dev \
        libpng-dev \
        libtiff-dev \
        libavformat-dev \
        libpq-dev \
        libxine2-dev \
        libglew-dev \
        libtiff5-dev \
        zlib1g-dev \
        libjpeg-dev \
        libavcodec-dev \
        libavformat-dev \
        libavutil-dev \
        libpostproc-dev \
        libswscale-dev \
        libeigen3-dev \
        libtbb-dev \
        libgtk2.0-dev \
        pkg-config \
        ## Python
        python3-dev \
        python3-numpy \
        ##blender dependencies
        curl \
		libfreetype6 \
		libglu1-mesa \
		libxi6 \
		libxrender1 \
		xz-utils && \
    && rm -rf /var/lib/apt/lists/*


ENV BLENDER_MAJOR 2.82
ENV BLENDER_VERSION 2.82a
ENV BLENDER_URL https://download.blender.org/release/Blender${BLENDER_MAJOR}/blender-${BLENDER_VERSION}-linux64.tar.xz

RUN curl -L ${BLENDER_URL} | tar -xJ -C /usr/local/ && \
	mv /usr/local/blender-${BLENDER_VERSION}-linux64 /usr/local/blender

VOLUME /media
ENTRYPOINT ["/usr/local/blender/blender", "-b"]

