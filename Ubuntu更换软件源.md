# Ubuntu更换软件源

---

[toc]



---

第一次更改时备份原sources.list文件

```shell
$ sudo cp /etc/apt/sources.list /etc/apt/sources.list.backup
```

用 gedit 打开根目录下 /etc/apt/sources.list文件

```shell
$ sudo gedit /etc/apt/sources.list
```

选择一家镜像源，将文件内容替换为指定Ubuntu版本的镜像源

以Ubuntu20.04(focal)阿里云软件源为例：

```shell
deb http://mirrors.aliyun.com/ubuntu/ focal main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ focal-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-security main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ focal-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-updates main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ focal-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-proposed main restricted universe multiverse

deb http://mirrors.aliyun.com/ubuntu/ focal-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ focal-backports main restricted universe multiverse
```

其它版本的 [Ubuntu](https://so.csdn.net/so/search?q=Ubuntu&spm=1001.2101.3001.7020) 可去 [阿里云镜像站](https://developer.aliyun.com/mirror/ubuntu?spm=a2c6h.13651102.0.0.3e221b113cjdoj)



更新软件列表

```shell
$ sudo apt-get update
//访问源列表里的每个网址，并读取软件列表，更新软件源
```

更新软件

```shell
$ sudo apt-get upgrade
//将本地已安装的软件与刚更新的软件列表里对应软件进行对比，如果发现已安装的软件版本太低就会提示更新
```



