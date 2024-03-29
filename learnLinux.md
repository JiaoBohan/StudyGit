# Linux

## 基础

### 求助

``<command> --help``  ``man <command>``  ``info <command>``

### 关机

``sync``    将数据同步写入磁盘当中
``shutdown``
``-K``

## 文件权限与目录配置

### 文件权限

|  | 权限 | 数字对照 |
| :-: | :--: | :------: |
| r |  读  |    4    |
| w |  写  |    2    |
| x | 执行 |    1    |

``chgrp [-R] 用户组名 文件名``			修改文件所属用户组，-R为进行递归修改

``chown 账号名称[: 用户组名称] 文件名``	修改文件拥有者

``cp 源文件 目标文件``		复制文件

``chmod [-R] xyz 目录``	修改文件的权限，x对应拥有者u对应权限的和，y对应g，z对应o

``chmod [-R] u=rwx,g=rw,o=r 文件``	a+r,a-r,a=r

### 文件种类与扩展名

#### 种类

- 常规文件
  属性为 ``-``，包括纯文本文件、二进制文件、数据文件
- 目录
  属性为 ``d``
- 链接文件
  属性为 ``l``，类似快捷方式
- 设备与设备文件
  通常集中于 ``/dev``目录下，分为区块设备文件和字符设备文件

  > 区块	``b`` 存储数据
  > 字符 ``c`` 串行端口的接口设备
  >
- 数据接口文件
  属性为 ``s``，通常被用在网络上的数据交换
- 数据传输文件
  属性为 ``p``，用于解决多个程序同时读写一个文件所造成的错误问题

#### 扩展名

- ``*.sh``
- ``*Z``,``*.tar``,``*.zip``
- ``*.html``,``*.php``

### 目录配置

**FHS**标准

- 根目录	与启动系统有关
- /usr		与软件的安装执行有关
- /var		与系统运行过程有关

## 文件与目录

### 路径

``.``代表本目录    ``..``代表上一层目录    ``~``代表使用者的家目录

> ``ls -al`` 显示全部文件，包括目录

- ``cd``切换目录
- ``pwd``显示当前目录
- ``mkdir``建立一个新目录
- ``rmdir``删除一个空目录

### 管理

- ``ls``文件与目录查看
- ``cp 源文件 目标文件``复制
- ``rm 文件或目录`` 删除
- ``mv 源文件 目标目录`` 移动或重命名文件或目录

### 查看

- ``cat`` 从第一行开始显示文件内容
- ``tac`` 从最后一行开始显示文件内容
- ``nl`` 显示的同时输出行号
- ``more`` 一页一页地显示
  > 空格/回车：向下翻一页/行
  > /字符串：向下查找此关键字
  > :f	立即显示文件名及当前行数
  > q	立即离开
  >
- ``less`` 与 ``more``相似，但可以向前翻页
- ``head`` 只显示前面几行
- ``tail`` 只显示后面几行
- ``od`` 以二进制方式读取文件内容

### 修改

- 修改时间 mtime：文件内容变更时更新
- 状态时间 ctime：当文件的状态，如权限与属性更新时更新
- 读取时间 atime：当文件内容被读取时更新

``ls -l``默认显示文件的mtime，指定所显示的时间可用 ``--time=?``

``touch 文件名``建立空文件，``touch``还可以修改文件时间

### 权限

``umask [-S]``目前用户在建立文件或目录时的权限默认值

``umask xyz``修改默认权限

**文件隐藏属性**

``chattr``

``lsattr``

**文件特殊权限**

``SUID``

``SGID``

``SBIT``

### 查找

``which``查找

``find``

``whereis``只查找特定目录

``locate/updatedb``查找/更新数据库

---

## 基本命令

**查看命令作用**
``man <command>``

**管理文件和目录**
`touch` `cd` `mv` `rm` `file` `cat` `more` `less` `tail`
`head` `cd` `pwd` `ls` `mkdir` `rmdir`

**管理系统进程**
`ps` `top` `kill` `killall`

**管理磁盘空间**
`mount` `umount` `df` `du`

**处理数据文件**
`sort` `grep` `gzip` `tar`

---

## 条件脚本控制

**数值比较**

|   用法   |  描述  |
| :-------: | :----: |
| n1 -eq n2 | n1==n2 |
| n1 -ge n2 | n1>=n2 |
| n1 -gt n2 | n1>n2 |
| n1 -le n2 | n1<=n2 |
| n1 -lt n2 | n1<n2 |
| n1 -ne n2 | n1!=n2 |

**字符串比较**

|     用法     |     描述     |
| :----------: | :-----------: |
| str1 = str2 |   长度相等   |
| str1 != str2 |  长度不相等  |
| str1 > str2 |   长度大于   |
| str1 < str2 |   长度小于   |
|    -n str    | 长度是否不为0 |
|    -z str    |  长度是否为0  |

**if 语句**  [^1]

```
if [ ]; then
    <command>
elif []; then 
    <command>
else
    <command>
fi
```

**case 语句**

```
case <expression> in
    pattern1)
        <command>;;
    pattern2 | pattern3)
        <command>;;
    *)
        default <command>;;
esac
```

[^1]: ``[ ]``可用 ``test``来代替
