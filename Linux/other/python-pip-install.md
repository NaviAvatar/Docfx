# centos 下安装 python-pip

[1]: https://zhuanlan.zhihu.com/p/27677121	"文章内容来源"

需要先安装扩展源EPEL。

EPEL([EPEL - FedoraProject](https://link.zhihu.com/?target=http%3A//fedoraproject.org/wiki/EPEL)) 是由 Fedora 社区打造，为 RHEL 及衍生发行版如 CentOS、Scientific Linux 等提供高质量软件包的项目。

首先安装epel扩展源：

```
sudo yum -y install epel-release
```

然后就可以安装成功了：

```
sudo yum -y install python-pip
```

