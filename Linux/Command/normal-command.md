# 常用基本命令

[1]: https://www.bilibili.com/video/BV1WY4y1H7d3?p=28	" 视频来源于尚硅谷视频教程"
[2]: https://www.bilibili.com/video/BV1WY4y1H7d3?p=35	"less, more，cat 用法"
[3]: https://blog.csdn.net/weixin_32501329/article/details/116768385	"查找文件中关键字"

可以把 Shell 看做一个命令解释器，它负责解释命令并交给内核执行。centos 7 默认的 shell 是 dash。



这条命令可以将 /bin/ 目录下筛选 sh 的文件详细列出来：

```
ls -l /bin/ | grep sh
```

```
ls -l          这条代码是显示目录和文件的详细资料，不会显示子目录里的文件细节
```

<font color='red'>命令记不住怎么办？</font>

网上查，或者 man 去查，或者 xx --help。

基本语法：man [命令]

<font color='red'>如果进入 3 级别模式，查询命令 --help信息太多怎么办？</font>

```c++
ls --help|less
```

或者

```
ls --help|more
```

一些常用的命令：

| 命令           | 说明                                                         | 例子                                                 |
| -------------- | ------------------------------------------------------------ | ---------------------------------------------------- |
| pwd            | print working directory，显示当前所在的绝对路径，常用于定位自己位置 | pwd                                                  |
| cd             | changing directory，切换目录                                 | cd /root/public                                      |
| ../            | 当前路径的上一层目录                                         | cd ../video                                          |
| cd -           | 返回上一次所在的位置目录，常用于频繁切换两个路径             | cd -                                                 |
| cd             | 返回主目录，不同用户返回的主目录不同                         | cd                                                   |
| su             | switch user，切换用户                                        | su                                                   |
| ls             | list，列出当前目录的文件和文件夹                             | ls                                                   |
| ls -a          | list all，显示当前目录的所有文件，包括隐藏文件               | ls -a                                                |
| ..             | 表示上层目录                                                 | cd ../                                               |
| .              | 表示当前目录                                                 | cd ./桌面                                            |
| 以.开头的文件  | 说明是隐藏文件                                               |                                                      |
| ls -l          | list long，显示当前目录下的文件和目录的详细信息              | ls -l                                                |
| ll             | 等同于 ls -l                                                 | ll                                                   |
| mkdir          | making directory，创建目录                                   | mkdir a                                              |
| mkdir a b      | 创建 a 文件夹和 b文件夹                                      | mkdir a b                                            |
| mkdir a/b/c    | 如果a目录存在且a/b目录存在，a/b/c文件夹创建成功；<br />如果a目录不存在或者a/b目录不存在，a/b/c 文件夹创建失败。<br />如果目录已存在，不会更改文件的创建时间属性。 | mkdir a/b/c                                          |
| mkdir -p a/b/c | 不管父辈级目录（a，a/b）存不存在，都将创建到 a/b/c。<br />如果目录已存在，不会更改文件的创建时间属性。 | mkdir -p a/b/c                                       |
| rmdir          | remove directory，删除目录                                   | rmdir a                                              |
| rmdir a b      | 如果a、b目录有文件或文件夹，那么删除失败。                   | rmdir a b                                            |
| rmdir a/b/c    | 如果a/b/c有文件或者文件，那么删除失败。<br />如果父辈级的目录还有其他文件或者文件夹，那么删除是吧 | rmdir a/b/c                                          |
| touch          | 创建文件。后面可以跟文件的绝对路径和相对路径。<br />如果文件存在，那么文件的内容不会变，时间属性会变成指令执行的时候的时间。 | touch a.c                                            |
| cp s d         | s:source，被拷贝的文件或文件夹。<br />d:拷贝文件放到的路径，可以是一个文件的绝对路径或者相对路径。<br />d也可以是一个文件夹的相对路径或者绝对路径。<br />如果是文件夹，请使用 -r 参数去递归复制。 | cp -r /code /sourcecode                              |
| \cp            | 同cp一样，不过不会进行拷贝询问。                             |                                                      |
| alias          | 可以查看有什么指令有别名。                                   |                                                      |
| rm             | 删除。                                                       |                                                      |
| rm s.c         | 会进行删除前询问。                                           |                                                      |
| \rm s.c        | 删除前不会询问。                                             |                                                      |
| rm -f s.c      | 删除前不会询问。                                             |                                                      |
| rm -rf s/      | 删除 s目录下的子文件和 子目录，并且不会询问。                |                                                      |
| rm -f ./*      | 清空当前目录。                                               |                                                      |
| mv             | 移动，可以移动文件，可以移动目录，或者给目录和文件重命名。   |                                                      |
| cat            | 查看文档，一下子全打印在黑眶上。                             | cat fileName\|grep “待查找字符串”                    |
| more           | 全部加载文件，但是现实开头文件。                             |                                                      |
| less           | 根据当前显示的文件加载部分内容，比more 强，还可以进行搜索。/keyword。即可搜索。<br />shift+G : 到文尾；g：到文首。 |                                                      |
| echo           | 打印。如果待打印字串之间有很长空格，这些长空格会被替换成一个空格。<br />如果有双引号，则按原样输出。 | echo "hello world"                                   |
| echo -e        | -e，表示支持\引号里的转义字符。                              | echo -e "hello world\nlinux"                         |
| <、>           | 输入输出重定向，可以将内容写到文件上。                       | ls -l > a.txt，将当前目录的文件详细信息写入a.txt中。 |
| <<、>>         | 输入输出追加，将内容追加到文件尾部。                         |                                                      |
| head           | 默认打开文件前10行。                                         | head a.c                                             |
| head -n 20     | 显示文件前20行，立即退出（不像tail）。                       | head a.c -n 20                                       |
| tail           | 默认查看文件最后10行。                                       | tail a.c                                             |
| tial -n 20     | 查看文件最后20行。                                           | tail a.c -n 20                                       |
| tial -f        | 实时跟踪刷新文件内容。                                       | tail -f a.c -n 20                                    |
| history        | 查看当前命令，可以搭配 less 使用。                           | history\|less                                        |
| history 10     | 表示过去最近输入的10条指令。                                 |                                                      |
| history -c     | 删除过去使用的指令的记录。                                   |                                                      |
| date           | 获取当前时间信息。                                           |                                                      |
| cal            | 查看日历。获取当天所在月份的日历                             |                                                      |
| cal -3         | 前后两个月也放出来                                           |                                                      |

## ln软连接

可以理解为快捷键。文件类型以 l 开头，表示软连接 ln。可以创建连接到软连接的连接。

基本语法：

```
ln -s [原文件或目录] [软连接名]
如：ln -s /home/aaaa/code/a.c programfile
```

删除软连接：

```
rm -rf [软连接名]
rm -rf programfile
```

如果删除了源文件，用 ls 显示软连接名就变成红色的。

如果想显示物理路径，用 pwd -p。

否则，进入软连接目录下，pwd显示的是软连接路径

如果想通过进入软连接名到其真是物理地址，可以用 cd -p [软连接路径]

查看倒数第 1000 行日志(具有实时追踪日志内容变化的功能)：<font color='red'>tail -f catalina.out -n 1000 | less</font>







1、find [选项] [目录] [条件] [动作] 

如果不指定任何目录，find 将会查找当前目录。如果 不指定条件，则条件相当于“true”，这样会把全部文件都找出来。选项、条件和动作的设置十分繁多，  看看 几个参数选项：

-xdev：不在其它文件系统的目录中搜索。

-mindepth <n>：搜索文件时至少要深入到指定目录的第 n 层子目录。

-maxdepth <n>：搜索文件时最多深入到指定目录的第 n 层子目录。

-follow：如果符号链接到目录，则跟随符号链接进入。默认情况下，find 不跟随链接。

-daystart：当使用与事件相关的测试时(见下文)，将当天的开始时间作为时间戳，而不是默认值(从当前时间倒退24个小时)。

条件可以是一个或多个原子测试。这是一些有用的测试：

-type <文件类型>：搜索给定类型的文件。文件类型可以是以下之一：f(普通文件)、d(目录)、l(符号链接)、s(套接字)、b(块模式文件)、c(字符模式文件)或p(命名管道)。

-name <模式>：查找文件名与给定模式匹配的文件。使用此选项，模式将被看作shell 全局模式(参见“Shell 通配符”一节)。

-iname <模式>：与 -name 类似，但不区分大小写。

-atime <n>、-amin <n>：查找上次访问时间在 n 天前(-atime)或 n 分钟前(-amin) 的文件。您还可以指定 <+n> 或 <-n>，这代表要搜索访问时间在至多或者至少 n 天/分钟前的文件。

-anewer <文件>：查找上次访问时间晚于文件的文件。

-ctime <n>、-cmin <n>、-cnewer <file>：与 -atime、-amin 和 -anewer 相同，但比较的是文件上次修改的时间。

-regex <模式>：与 -name 相同，但模式将被看作正则表达式。

-iregex <pattern>：与 -regex 相同，但不区分大小写。



2、利用find加grep，find找出文件，grep查找文件内容

```
# find . -type f -print | xargs grep "hostname"
```

用grep命令在所有的普通文件中搜索hostname这个词

