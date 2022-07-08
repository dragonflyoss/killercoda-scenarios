### View Docker version and  Docker Compose version

`docker version`{{execute T1}}

`docker-compose version`{{execute T1}}

### Document

Official document [Install Dragonfly by Docker Compose](https://d7y.io/docs/getting-started/quick-start/docker-compose/)

### Clone Dragonfly repo

`git clone https://github.com/dragonflyoss/Dragonfly2.git`{{execute T1}}

Wait for clone success.

### Get Local ip

`export IP=$(hostname -I | cut -d' ' -f1)`{{execute T1}}

### Startup Dragonfly by Docker Compose

`cd Dragonfly2/deploy/docker-compose/ && docker-compose up --no-start`{{execute T1}}

### Modify Docker Registry

Modify Docker Daemon Config file

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

Restart Docker Service

`service docker restart`{{execute T1}}

### Startup Dragonfly

Startup

`./run.sh`{{execute T1}}

View status

`docker-compose ps`{{execute T1}}

### Access Dragonfly Manager Console Web UI

Click `Manager Console UI` dashboard or this link [Manager Console UI]({{TRAFFIC_HOST1_8080}})

