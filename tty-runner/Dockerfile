#
# 基于 Ubuntu 16.04，包含 PHP、Node.js、Python、Vim 运行环境
#
# author: imzhi
# date: 2017-01-17
#
FROM ubuntu:xenial-20161213
MAINTAINER imzhi <yxz_blue@126.com>

ENV DEBIAN_FRONTEND noninteractive

# 修改时区
# 安装常用软件
# 设置 UTF-8 环境
# 安装 PHP 7
# 安装 Node.js
# 新增用户
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    dpkg-reconfigure -f noninteractive tzdata && \
    echo 'deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse' > /etc/apt/sources.list && \
    echo 'deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse' >> /etc/apt/sources.list && \
    echo 'deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse' >> /etc/apt/sources.list && \
    echo 'deb http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse' >> /etc/apt/sources.list && \
    echo 'deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse' >> /etc/apt/sources.list && \
    apt-get update && apt-get install -y \
    python-software-properties \
    software-properties-common \
    vim \
    man \
    wget \
    curl && \
    locale-gen "en_US.UTF-8" && \
    dpkg-reconfigure locales && \
    echo "export LC_ALL=en_US.UTF-8" >> ~/.bashrc && \
    echo "export LANG=en_US.UTF-8" >> ~/.bashrc && \
    . ~/.bashrc && \
    LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php && \
    apt-get update && apt-get install -y \
    php7.1 && \
    cd /tmp && \
    wget -q https://npm.taobao.org/mirrors/node/v6.5.0/node-v6.5.0-linux-x64.tar.gz && \
    tar xzf node-v6.5.0-linux-x64.tar.gz && \
    mv node-v6.5.0-linux-x64 /opt/node && \
    chown root.root -R /opt/node/ && \
    ln -s /opt/node/bin/node /usr/local/bin/node && \
    ln -s /opt/node/bin/npm /usr/local/bin/npm && \
    useradd -m -d /home/imzhi imzhi && \
    cd /home/imzhi
