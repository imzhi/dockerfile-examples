#
# 基于 Ubuntu 14.04，包含 PHP、Node.js、Python、Vim 运行环境
#
# author: imzhi
# date: 2016-09-04
#
FROM ubuntu:trusty-20160819
MAINTAINER imzhi <yxz_blue@126.com>

# 修改时区
RUN echo "Asia/Shanghai" > /etc/timezone && \
    dpkg-reconfigure -f noninteractive tzdata

# 设置 UTF-8 环境
RUN locale-gen "en_US.UTF-8" && \
    dpkg-reconfigure locales && \
    echo "export LC_ALL=en_US.UTF-8" >> ~/.bashrc && \
    echo "export LANG=en_US.UTF-8" >> ~/.bashrc && \
    . ~/.bashrc

# 安装 PHP 7.0
RUN echo "deb http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse" > /etc/apt/sources.list
RUN apt-get update && apt-get install -y \
    software-properties-common
RUN LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php
RUN apt-get update && apt-get install -y \
    wget \
    curl \
    vim \
    php7.0

# 安装 Node.js
WORKDIR /tmp
RUN wget -q https://npm.taobao.org/mirrors/node/v6.5.0/node-v6.5.0-linux-x64.tar.gz
RUN tar xzf node-v6.5.0-linux-x64.tar.gz
RUN mv node-v6.5.0-linux-x64 /opt/node
RUN chown root.root -R /opt/node/
RUN ln -s /opt/node/bin/node /usr/local/bin/node
RUN ln -s /opt/node/bin/npm /usr/local/bin/npm
WORKDIR /root
