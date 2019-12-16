FROM ubuntu:18.04
MAINTAINER imzhi <yxz_blue@126.com>

COPY ./sources.list /etc/apt/sources.list
RUN apt update\
    && apt install -y \
        net-tools\
        iputils-ping\
        iproute2\
        iptables\
        bridge-utils\
        nano\
    && apt purge -y --auto-remove\
    && rm -rf /var/lib/apt/lists/*

