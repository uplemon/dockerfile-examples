# Examples

* [python3.6.9](/python/python3.6.9)
* [scrapyd](/scrapyd)

# Docker Commands
```bash
# 查看本地镜像
$ docker images
$ docker rmi <image-id|image-name>

# 查看所有的容器（包括退出的）
$ docker ps -a
# 启动/停止/重启容器
$ docker <start|stop|restart> <container-id|container-name>
# 查看容器状态
$ docker stats <container-id|container-name>
# 删除容器
$ docker rm <container-id|container-name>

# 基于镜像启动容器
# -i 交互式操作
# -t 终端
# -d 后台运行
# -p 宿主机和容器进行端口映射
# --name 给容器命名（没有该参数会给容器随机分配个名字）
$ docker run -itd --name python honeylz/python:3.6.9 /bin/bash
$ docker run --name scrapyd -d -p 6800:6800 uplemon/scrapyd:1.0

# 进入容器（在使用-d参数时，容器启动后会进入后台，此时进入容器可以使用docker-attach或者docker-exec命令）
# docker-attach命令退出容器终端会导致容器的终止 
# docker-exec命令退出容器终端不会导致容器的停止
$ docker attach <container-id|container-name>
$ docker exec -it <container-id|container-name> /bin/bash
```
