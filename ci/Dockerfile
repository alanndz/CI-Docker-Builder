FROM ubuntu:22.04
LABEL maintainer "alanndz <alanndz7@gmail.com>"

# Indonesian Timezone (GMT+8)
ENV TZ=Asia/Makassar
ENV USER=cirrus
ENV HOSTNAME=bianca
WORKDIR /tmp

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Install packages
RUN sudo apt-get update -qq && \
    sudo apt-get upgrade -y && \
    sudo apt-get install --no-install-recommends -y \
        autoconf \
        autogen \
        automake \
        autotools-dev \
        bc \
        binutils \
        binutils-aarch64-linux-gnu \
        binutils-arm-linux-gnueabi \
        bison \
        brotli \
        bzip2 \
        ca-certificates \
        ccache \
        coreutils \
        cmake \
        curl \
        cpio \
        expect \
        flex \
        g++ \
        gawk \
        gcc \
        git \
        gnupg \
        gperf \
        help2man \
        jq \
        lftp \
        libc6-dev \
        libelf-dev \
        libgomp1-* \
        liblz4-tool \
        libncurses5-dev \
        libssl-dev \
        libstdc++6 \
        libtool \
        libtool-bin \
        libtinfo5 \
        llvm \
        lld \
        m4 \
        make \
        nano \
        openjdk-8-jdk \
        openssh-client \
        openssl \
        ovmf \
        patch \
        pigz \
        python3 \
        repo \
        rclone \
        rsync \
        shtool \
        sshpass \
        subversion \
        tar \
        texinfo \
        tzdata \
        u-boot-tools \
        unzip \
        wget \
        xz-utils \
        zip \
        zlib1g-dev \
        zstd

# Add user
RUN groupadd -g 1000 -r ${USER} \
    && useradd -u 1000 --create-home -r -g ${USER} ${USER}

RUN echo "${USER} ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/${USER} \
    && usermod -aG sudo ${USER}

VOLUME ["/tmp/rom", "/tmp/ccache"]
ENTRYPOINT ["/bin/bash"]