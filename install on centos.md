在 CentOS 7.6 系统安装 Docker 服务

#### 1. 卸载老版本

```
~]$ sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```

#### 2. 配置阿里云yum 源

```
~]$ sudo yum install -y yum-utils device-mapper-persistent-data lvm2
~]$ sudo yum-config-manager --add-repo https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
~]$ sudo yum makecache fast
```

#### 3. 安装docker

```
// 列出所有的 docker 版本：yum list docker-ce --showduplicates | sort -r
// sudo yum install docker-ce docker-ce-cli containerd.io
~]$ sudo yum install docker-ce-18.09.8 docker-ce-cli-18.09.8 containerd.io
```

#### 4. 启动服务

```
~]$ sudo systemctl start docker.service
```

#### 5. 镜像加速

```
~]# vim /etc/docker/daemon.json
{
    "registry-mirrors": ["https://o4uba187.mirror.aliyuncs.com"]
}
~]# systemctl  restart docker
```
