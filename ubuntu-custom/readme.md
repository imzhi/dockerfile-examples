ubuntu-custom
===

定制 ubuntu 18.04。在看《docker 从入门到实践》的【高级网络配置】一章节，需要额外安装基础的网络命令，如 ip、iptables 等。

### 构建命令

```bash
$ docker build -t ubuntu:custom .
```

### 运行容器

```bash
$ docker run -it --rm --privileged --name ubuntu1 ubuntu:custom bash
```
> --privileged 参数表示：Give extended privileges to this container（在容器中使用 iptables 需要加上此参数）
