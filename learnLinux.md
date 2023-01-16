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

``r`` 读 4    ``w`` 写 2    ``x`` 执行 1

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
  >

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
