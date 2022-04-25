# Linux下 安装 Git

安装编译 Git 所需要的依赖：

```
yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel gcc perl-ExtUtils-MakeMaker
```

安装编译源码所需依赖的时候，yum 自动安装了 Git，需要先卸载这个旧版的 Git：

```
yum -y remove git
```

下载 Linux 下 Git 的安装包，地址：

https://mirrors.edge.kernel.org/pub/software/scm/git/

将压缩包上传至 Linux 服务器的 /usr 目录下

进入到/user目录：cd /usr

解压压缩包：

```
tar -zxvf git-2.22.0.tar.gz
```

进入到解压后的文件夹：

```
cd git-2.22.0
```

编译 Git 源码：

```
make prefix=/usr/local/git all
```

安装 Git 至 /usr/local/git 路径：

```
make prefix=/usr/local/git install
```

配置环境变量：

```
vim /etc/profile
```

在环境变量配置文件底部加上：

```
export PATH=$PATH:/usr/local/git/bin
```

刷新环境变量：

```
source /etc/profile
```

查看Git是否安装完成：

```
git --version
```


————————————————
版权声明：本文为CSDN博主「Nice2cu_Code」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/weixin_49343190/article/details/123529976