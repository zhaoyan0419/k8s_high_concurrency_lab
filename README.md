# 1 高并发基础+环境准备

> 目标回顾
>
> - 理解高并发场景下资源瓶颈
> - 构建个人测试环境（本地多节点k8s集群）
> - 部署监控体系（prometheus+grafana）



## 1.1 理解高并发场景下资源瓶颈

```shell




```

## 1.2 构建个人测试环境（本地多节点k8s集群）

> 使用kind在本地计算机上创建一个kuberntes集群并安装kubectl进行api-server交互
>
> 环境准备：
>
> - 1台linux机器（4c8g）ubuntu22.04
> - 安装docker，用于kind（Kubernetes IN Docker）
> - 打通网络限制以便镜像拉取，使用docker pull image:tag  然后使用kind load docker-image --name zy-test image:tag将image导入到node(实际为docker的一个容器)中

- 安装kind & kubctl

```shell
# 安装kubectl
apt -y install kubectl

# 下载kind二进制包
wget https://github.com/kubernetes-sigs/kind/releases/download/v0.29.0/kind-linux-amd64

# 将kind二进制包放入path内
mv ./kind-linux-amd64 /usr/local/bin/kind

# 测试kind是否可用
kind --version
```

- 部署集群

```shell
# 部署集群，指定配置文件以及集群名称
kind create cluster --config week1_setup/kind-config.yaml --name zy-test

# 查看集群是否创建成功，kind创建集群之后会自动生成kubeconfig；查看节点信息
kind get clusters
kubectl get no
```

## 1.3 部署监控体系





# 部署微服务应用+首次压测










# k8s自动扩缩容与流量治理







# redis+mysql高并发下的表现与优化









# 故障注入与恢复能力演练





