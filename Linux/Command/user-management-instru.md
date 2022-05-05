# 用户管理

## 如何创建新用户

创建新用户

```
useradd tony
```

给用户 tony 设置密码

```
passwd	tony
```

查看当前用户

```
less /etc/passwd
```

查看当前用户 tony 是否已登录

```
id tony
```

切换用户

```
su tony
```

查看原始创建会话用户

```
who am i
```

------

## 如何临时赋予普通用户有root权限

回退到 root 权限，打开 sudoers 文件

```
vim /etc/sudoers
```

添加tony权限

```
tony	ALL=(ALL)	ALL
```

强制保存文件

```
:wq!
```

切换到 tony 用户，在无权限区域，使用 sudo + 命令。

------

## 如何删除普通用户

删除用户但是保留其主文件夹

```
userdel tony
```

如果不需要主目录，可在删除用户时指定删除主目录

```
userdel -r tony
```

------

## 如何添加用户组

添加用户组 meifa

```
group meifa
```

添加用户到用户组 meifa

```
usermod -g meifa tony
usermod -g meifa david
```

重命名用户组

```
groupmod -n haircut meifa
```

删除用户组

```
groupdel tony
groupdel david
```

给组以 sudo 权限

* 打开 sudoers 文件