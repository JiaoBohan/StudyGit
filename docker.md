# Docker 命令

**centOS7**

## 服务相关

启动	 	``systemctl start docker``

停止 	``systemctl stop docker``

重启 	``systemctl restart docker``

查看状态 	``systemctl status docker``

## 镜像相关

查看本地	``docker images``

搜索镜像	``docker search {name}``

拉取镜像	``docker pull {name[:version]}``

删除镜像	``docker rmi {id}``	``docker rmi `{name[:version]}` ``

删除所有	``docker rmi 'docker images -q'``

## 容器相关

查看正在运行的容器 ``docker ps``，``-a``查看所有容器，``-q``查看所有容器 ID

创建并启动容器 ``docker run [option] --name={name}``

> - -i	保持容器运行，通常与 ``-t``同时使用
> - -t	为容器重新分配一个伪输入终端
> - -d 	以后台模式运行容器，退出后不会关闭。需使用 ``docker exec {name}``来进入容器
> - -p 宿主机端口:容器端口	进行端口映射

进入容器 ``docker exec {name}``

停止容器 ``docker stop {name}``

启动容器 ``docker start {name}``

删除容器 ``docker rm {name}``

查看容器信息 ``docker inspect {name}``

# 数据卷

配置数据卷

``docker run ... -v 宿主机目录(文件):容器内目录(文件) 镜像名:镜像版本``

# Dockerfile文件制作镜像

示例

```
FROM centos:7			#定义父镜像
MAINTAINER jbh<123@qq.com>	#定义作者信息
RUN yum install -y vim		#执行安装 vim 命令
WORKDIR /usr			#定义默认的工作目录
CMD /bin/bash			#定义容器启动执行的命令
```
