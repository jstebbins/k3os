### BASE ###
FROM alpine:3.9 as base
ARG ARCH
RUN apk -U add \
    bash \
    bash-completion \
    blkid \
    busybox-initscripts \
    ca-certificates \
    connman \
    conntrack-tools \
    coreutils \
    curl \
    dbus \
    dosfstools \
    e2fsprogs \
    e2fsprogs-extra \
    findutils \
    grub-efi \
    haveged \
    iproute2 \
    iptables \
    jq \
    kbd-bkeymaps \
    logrotate \
    nfs-utils \
    open-iscsi \
    openrc \
    openssh-client \
    openssh-server \
    parted \
    procps \
    rsync \
    strace \
    sudo \
    tar \
    udev \
    util-linux \
    vim \
    xz
RUN if [ "$ARCH" == "amd64" ]; then \
        apk add open-vm-tools grub-bios \
    ;fi
RUN apk --no-cache add \
    --repository 'http://dl-cdn.alpinelinux.org/alpine/edge/community' \
    --repository 'http://dl-cdn.alpinelinux.org/alpine/edge/testing' \
    efibootmgr
RUN rc-update add udev sysinit
RUN rc-update add udev-trigger sysinit
RUN rc-update add udev-settle sysinit
