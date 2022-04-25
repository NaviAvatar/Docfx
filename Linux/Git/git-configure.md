# Git 配置和远程连接

[参考教程]: https://www.liaoxuefeng.com/wiki/896043488029600/896067074338496	"本文内容参考来源"
[参考]: https://www.jianshu.com/p/198803de9ee2



## 配置用户名和邮箱：

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

将当前目录变成Git仓库：

```
$ git init
```

## 生成ssh密钥（用于远程连接仓库）

```
ssh-keygen -t rsa -C "your email"
```

然后看到信息：

```
Your identification has been saved in /root/.ssh/id_rsa.
Your public key has been saved in /root/.ssh/id_rsa.pub.
```

去 /root/.ssh/id_rsa.pub 路径下查看公钥，把它添加到你的远程仓库允许连接的SSH keys 管理组中。

github 上是点击个人头像，下拉里的 

settings--SSHandGPG keys--New SSH key。

好像如果连接到远程，git clone 就无法使用。

## 关联到某个仓库

```
git remote add origin 仓库地址
```

origin是仓库的别名，以后推送就可以这样：

```
git push -u origin
```

