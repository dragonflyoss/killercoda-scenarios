### 查看 Docker 版本和 Docker Compose 版本

`docker version`{{execute T1}}

`docker-compose version`{{execute T1}}

### 获取本机ip

`export IP=$(hostname -I | cut -d' ' -f1)`{{execute T1}}

### 拉取依赖的 MySQL Redis Nginx 镜像

`docker-compose up --no-start`{{execute T1}}

### 修改 Docker Registry

```sh
cat << EOF > /etc/docker/daemon.json
{
  "exec-opts": ["native.cgroupdriver=systemd"],
  "log-driver": "json-file",
  "storage-driver": "overlay2",
  "registry-mirrors": ["http://127.0.0.1:65001","https://mirror.gcr.io","https://docker-mirror.killer.sh"],
  "mtu": 1454
}
EOF
```{{execute T1}}

重启 Docker 服务

`service docker restart`{{execute T1}}

### 启动 MySQL Redis Nginx 服务

`docker-compose up -d `{{execute T1}}

`docker-compose ps `{{execute T1}}
