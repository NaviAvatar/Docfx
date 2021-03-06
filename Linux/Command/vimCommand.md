# vim 命令操作

[尚硅谷]: https://www.bilibili.com/video/BV1WY4y1H7d3?p=19&amp;spm_id_from=pageDriver	"文档内容来源于哔哩哔哩尚硅谷课程视频"



## 1 一般模式

| 按键           | 操作                                                         |
| -------------- | ------------------------------------------------------------ |
| yy             | 复制当前行                                                   |
| y2y            | 赋值当前行开始往下两行                                       |
| 4yl            | 复制当前光标往后4个字符                                      |
| p              | 粘贴                                                         |
| 5p             | 连续粘贴五次                                                 |
| u              | 撤回上一步操作                                               |
| dd             | 删除当前光标所在行                                           |
| d10d           | 删除当前光标所在行开始往下连续10行                           |
| y$             | 复制当前光标到行尾                                           |
| y^             | 复制当前光标到行头                                           |
| x              | 删除光标标记的字符                                           |
| shift + x      | 删除光标前面的一个字符                                       |
| d$             | 删除当前光标位置到行尾                                       |
| d^             | 删除当前光标位置到行头                                       |
| r              | 按一次r，可以改一次光标所在的字符                            |
| shift + r      | 更改光标的内容，光标自动右移（不会跳到下一行）               |
| shift + ^      | 移动到行头                                                   |
| shift + $      | 移动到行尾                                                   |
| w              | 切换到下一个词的词头                                         |
| e              | 切换到下一个词的词尾                                         |
| b              | 切换到上一个词的词头                                         |
| gg             | 移动到文档内容的第一行的第一个字符                           |
| shift + g      | 移动到文档内容的最后一行的第一个字符                         |
| shift + H      | 移动到当前命令窗口显示文档的第一行                           |
| shift + L      | 移动到当前命令窗口的最后一行行首                             |
| 3 + shift + g  | 跳到文档第3行                                                |
| 12 + shift + H | 如果当前窗口存在第12行，跳到第12行，否则，跳到当前窗口显示的行号最大的那一行 |

## 2 命令模式

| 命令              | 操作                                                         |
| ----------------- | ------------------------------------------------------------ |
| : set nu          | 显示行号                                                     |
| : set nonu        | 隐藏行号                                                     |
| :w                | 保存                                                         |
| :q                | 转到一般模式                                                 |
| :wq               | 保存并转换到一般模式                                         |
| :q!               | 强制退出                                                     |
| :/boot            | 文档中所有 boot 单词高亮。<br />此时按 n 键，光标会在高亮词之间跳动（上往下循环）。<br />此时按shift + n 键，光标会在高亮词之间跳动（下往上循环） |
| :noh              | 取消高亮                                                     |
| : $/boot/booot    | 替换当前行匹配到的第一个 boot 为 booot                       |
| : $/boot/booot/g  | 针对光标所在行的所有 boot 改为 booot                         |
| : %$/boot/booot   | 替换每一行中第一个匹配到的 boot 改为 booost                  |
| : %$/boot/booot/g | 文档中每一行的 boot 都被替换成 booost                        |

## 3 编辑模式

从一般模式切换到编辑模式，按以下键：

| 按键      | 操作                                     |
| --------- | ---------------------------------------- |
| i         | 当前光标                                 |
| a         | 光标后移一个字符                         |
| o         | 在当前光标之后插入一行空行，光标跳到空行 |
| shift + i | 光标跳到当前行的行首                     |
| shift + a | 光标跳到当前行的行尾                     |
| shift + o | 在当前行的前面插入一行空行，光标跳到空行 |

退出编辑模式是 按 Esc 键。