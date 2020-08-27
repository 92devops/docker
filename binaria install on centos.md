#### 1. 获取二进制包

```
~]# wget https://download.docker.com/linux/static/stable/x86_64/docker-18.09.9.tgz
```

#### 2. 复制可执行文件到 /usr/bin 目录下

```
~]# tar -xf docker-18.09.8.tar
~]# cd docker &&  cp ./* /usr/bin/
```

#### 3. 提供启动时相关文件

从一个已经yum安装好的机器上复制启动相关的文件

```
~]# scp 192.168.124.231:/usr/lib/systemd/system/{docker.service,containerd.service,docker.socket} /usr/lib/systemd/system
```

#### 4. 解锁
