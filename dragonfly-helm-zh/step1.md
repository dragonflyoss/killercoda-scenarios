### 获取节点状态

`kubectl get nodes`{{execute T1}}

输出如下信息

```
NAME       STATUS   ROLES    AGE   VERSION
minikube   Ready    master   51s   v1.17.3
```

### 安装 Helm

Download and install helm into `/usr/local/bin/`

`wget https://get.helm.sh/helm-v3.8.1-linux-amd64.tar.gz`{{execute T1}}

`tar -zxvf helm-v3.8.1-linux-amd64.tar.gz && mv linux-amd64/helm /usr/local/bin/helm`{{execute T1}}

`helm --help`{{execute T1}}


