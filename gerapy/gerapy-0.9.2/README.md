### 启动容器
```bash
$ docker run --name gerapy -d -v ~/gerapy:/data/app/gerapy -p 8000:8000 uplemon/gerapy:0.9.2
```

### 创建管理员账号
```bash
# 进入容器
$ docker exec -it gerapy /bin/bash
# 进入项目目录
$ cd /data/app/gerapy
# 创建账号
$ /data/server/www/gerapy/bin/gerapy createsuperuser
```
