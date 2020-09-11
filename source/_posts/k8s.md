---
title: K8S
date: 2020-06-01 10:29:46
tags:
- Linux
- 容器
categories:
- DevOpts
---

# 集群环境
1、https://labs.play-with-k8s.com/
> 快速搭建集群环境(仅可用4小时)
2、https://github.com/kubernetes/minikube
3、docker desktop 内置 (推荐)

> 单纯使用容器，存在的问题
* 怎么去管理这么多容器
* 怎么能方便的横向扩展
* 如果容器down了，怎么能自动恢复
* 如果更新容器而不影响业务
* 如何去监控追踪这些容器
* 怎么去调度容器的创建
* 保护隐私数据？

## kubelet
相当于一个在node上的代理，管理容器相关。可以在node上面创建pod，创建pod里面的网络、volumns

## kube-proxy
主要负责容器上的网络代理，负载均衡的实现

## kubectl
客户端（命令行）与k8s交互的一个中介

`kubectl completion -h `
打开自动补全，以mac的zsh举例：`source <(kubectl completion zsh)`

在本地访问远端的k8s集群:
1、把远端的K8S集群的配置放到本地，一般在 `~/.kube/config`，将里面的`cluster`、`context`和`user`的key-value复制过来，放在本地的`~/.kube/config`进行和原来的配置合并（注意`server-certificate-data和client-certificate-data`都是一行）
2、执行`kubectl get contexts`应该能看到新加的context
3、执行`kubectl config use-context <context-name>`切换到预期的context进行集群管理


`kubectl get node` 查看node list
`kubectl get node -o wide` 查看node list 的详细信息（常用）
`kubectl get node -o yaml` 查看node list 的yaml 详细信息
`kubectl get node -o json` 查看node list 的json 详细信息
`kubectl get node --show-labels` 查看node list 的 label
`kubectl descibe node <node-name>` 查看node的详情

设置label
`kubectl label node <node-name> env=test` 给node设置label`env=test`
`kubectl label node <node-name> env-` 给node删除label`env`

设置roles
`kubectl label node <node-name> node-role.kubernetes.io/master=` 设置master
`kubectl label node <node-name> node-role.kubernetes.io/worker=` 设置worker


# Pod
* 一个或者一组应用容器，他们分享资源（比如volume）
* 分享相同命名空间（如网络空间）的容器
* Pod是k8s最小的调度单位

## create pod

create pod through yml file

```bash
$ kubectl create -f nginx_busybox.yml
pod "nginx-busybox" created
```

## get pod list

```bash
$ kubectl get pods
NAME            READY     STATUS    RESTARTS   AGE
nginx-busybox   2/2       Running   0          57s
```

## get pod detail

we use use describe or get pod with `-o` option to display more information about this pod

```bash
$ kubectl describe pod nginx-busybox
```

```bash
$ kubectl get pods nginx-busybox -o wide
NAME            READY     STATUS    RESTARTS   AGE       IP           NODE
nginx-busybox   2/2       Running   0          3m        172.17.0.4   minikube
```

here `-o` we can use `wide`, `json`, `yaml`, etc.

## get into pod(container)

```bash
$ kubectl exec nginx-busybox -it sh
Defaulting container name to nginx.
Use 'kubectl describe pod/nginx-busybox -n default' to see all of the containers in this pod.
#
#
#
```

## delete pod

```bash
$ kubectl delete -f nginx_busybox.yml
pod "nginx-busybox" deleted
```

# Namespace
* Namespace命名空间用于不同的team，不同的project之间的隔离
* 在不同的命名空间中，各种资源的名字是相互独立，比如可以具有相同名称的pod存在

## get all namesapce

```bash
$ kubectl get namespace
NAME          STATUS    AGE
default       Active    1d
kube-public   Active    1d
kube-system   Active    1d
```

## create namespace

```bash
% kubectl create namespace demo
namespace "demo" created
```

## delete namespace

Please makesure there are no resources within this namespace you want to delete.

```bash
$ kubectl delete namespace demo
namespace "demo" deleted
```

## create pod with namespace

```bash
$ more nginx_namespace.yml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
  namespace: demo
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
```

```bash
$ kubectl create -f nginx_namespace.yml
Error from server (NotFound): error when creating "nginx_namespace.yml": namespaces "demo" not found
$ kubectl create namespace demo
namespace "demo" created
$ kubectl create -f nginx_namespace.yml
pod "nginx" created
```

## get pod with namespace

```bash
$ kubectl get pod --namespace demo
NAME      READY     STATUS    RESTARTS   AGE
nginx     1/1       Running   0          6m
```

## get pod with all namespace
```bash
$ kubectl get pod --all-namespaces
```

## create our own context

```bash
$ kubectl config set-context demo --user=minikube --cluster=minikube --namespace=demo
Context "demo" created.
$ kubectl config get-contexts
CURRENT   NAME       CLUSTER    AUTHINFO   NAMESPACE
          demo       minikub    minikube   demo
          minikube   minikube   minikube
$ kubectl config use-context demo
Switched to context "demo".
```

# Deployment

## Create a Deployment

```bash
$ kubectl create -f nginx_depolyment.yml
deployment.apps "nginx-deployment" created
```

## Get deployment

Get deployment and pod information

```bash
$ kubectl get deployment
NAME               DESIRED   CURRENT   UP-TO-DATE   AVAILABLE   AGE
nginx-deployment   2         2         2            2           12s
$ kubectl get deployment -o wide
NAME               DESIRED   CURRENT   UP-TO-DATE   AVAILABLE   AGE       CONTAINERS   IMAGES        SELECTOR
nginx-deployment   2         2         2            2           40s       nginx        nginx:1.7.9   app=nginx
$ kubectl get pod -l app=nginx
NAME                                READY     STATUS    RESTARTS   AGE
nginx-deployment-75675f5897-bwz4j   1/1       Running   0          1m
nginx-deployment-75675f5897-z626w   1/1       Running   0          1m
```

also can use describe

```bash
$ kubectl describe deployment nginx-deployment
Name:                   nginx-deployment
Namespace:              default
CreationTimestamp:      Tue, 26 Jun 2018 23:15:17 +0800
Labels:                 <none>
Annotations:            deployment.kubernetes.io/revision=1
Selector:               app=nginx
Replicas:               2 desired | 2 updated | 2 total | 2 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  app=nginx
  Containers:
   nginx:
    Image:        nginx:1.7.9
    Port:         80/TCP
    Host Port:    0/TCP
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      True    MinimumReplicasAvailable
  Progressing    True    NewReplicaSetAvailable
OldReplicaSets:  <none>
NewReplicaSet:   nginx-deployment-75675f5897 (2/2 replicas created)
Events:
  Type    Reason             Age   From                   Message
  ----    ------             ----  ----                   -------
  Normal  ScalingReplicaSet  3m    deployment-controller  Scaled up replica set nginx-deployment-75675f5897 to 2
```

## keep desired pod state

```bash
$ kubectl get pod -l app=nginx
NAME                                READY     STATUS    RESTARTS   AGE
nginx-deployment-75675f5897-bwz4j   1/1       Running   0          3m
nginx-deployment-75675f5897-z626w   1/1       Running   0          3m
$ kubectl delete pod nginx-deployment-75675f5897-bwz4j
pod "nginx-deployment-75675f5897-bwz4j" deleted
$ kubectl get pod -l app=nginx
NAME                                READY     STATUS    RESTARTS   AGE
nginx-deployment-75675f5897-6fdvh   1/1       Running   0          <invalid>
nginx-deployment-75675f5897-z626w   1/1       Running   0          4m
$ kubectl get pod -l app=nginx
NAME                                READY     STATUS    RESTARTS   AGE
nginx-deployment-75675f5897-6fdvh   1/1       Running   0          0s
nginx-deployment-75675f5897-z626w   1/1       Running   0          4m
```

## Updating the deployment

```yaml
apiVersion: apps/v1 # for versions before 1.9.0 use apps/v1beta2
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  selector:
    matchLabels:
      app: nginx
  replicas: 2
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.8 # Update the version of nginx from 1.7.9 to 1.8
        ports:
        - containerPort: 80
```

```bash
$ kubectl apply -f nginx_depolyment_update.yml
depolyment "nginx-deployment" updated
```

## 更新Deployment，Scaling the application by increasing the replica count

```bash
$ kubectl apply -f nginx_depolyment_scale.yml
depolyment "nginx-deployment" updated
```

```bash
$ kubectl get pods -l app=nginx
NAME                               READY     STATUS    RESTARTS   AGE
nginx-deployment-148880595-4zdqq   1/1       Running   0          25s
nginx-deployment-148880595-6zgi1   1/1       Running   0          25s
nginx-deployment-148880595-fxcez   1/1       Running   0          2m
nginx-deployment-148880595-rwovn   1/1       Running   0          2m
```

### 只更新replication

*执行后会有提示，安装提示更新相应的deployment*

```bash
$ kubectl scale
```

### 只更新image或者env...

*执行后会有提示，如更新镜像：`kubectl set image deployment/nginx-deployment nginx=nginx:1.9.1`*
```bash
$ kubectl set
```

## Delete a Deployment

```bash
$ kubectl delete deployment nginx-deployment
depolyment "nginx-deployment" deleted
```

# Replicaset

## create deployment

```bash
$ kubectl apply -f nginx_deployment.yml
deployment.apps "nginx-deployment-test" created
```

describe and get the relicaset event

```bash
$ kubectl describe deployment nginx-deployment-test
Name:                   nginx-deployment-test
Namespace:              default
CreationTimestamp:      Wed, 27 Jun 2018 00:51:10 +0800
Labels:                 <none>
Annotations:            deployment.kubernetes.io/revision=1
                        kubectl.kubernetes.io/last-applied-configuration={"apiVersion":"apps/v1","kind":"Deployment","metadata":{"annotations":{},"name":"nginx-deployment-test","namespace":"default"},"spec":{"replicas":4,"se...
Selector:               app=nginx
Replicas:               4 desired | 4 updated | 4 total | 4 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  app=nginx
  Containers:
   nginx:
    Image:        nginx:1.7.9
    Port:         80/TCP
    Host Port:    0/TCP
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Available      True    MinimumReplicasAvailable
  Progressing    True    NewReplicaSetAvailable
OldReplicaSets:  <none>
NewReplicaSet:   nginx-deployment-test-75675f5897 (4/4 replicas created)
Events:
  Type    Reason             Age   From                   Message
  ----    ------             ----  ----                   -------
  Normal  ScalingReplicaSet  8h    deployment-controller  Scaled up replica set nginx-deployment-test-75675f5897 to 4
```

## scale and check the replicaset event

```bash
$ kubectl scale --current-replicas=4 --replicas=6 deployment/nginx-deployment-test
deployment.extensions "nginx-deployment-test" scaled
```

```bash
$ kubectl describe deployment nginx-deployment-test
Name:                   nginx-deployment-test
Namespace:              default
CreationTimestamp:      Wed, 27 Jun 2018 00:51:10 +0800
Labels:                 <none>
Annotations:            deployment.kubernetes.io/revision=1
                        kubectl.kubernetes.io/last-applied-configuration={"apiVersion":"apps/v1","kind":"Deployment","metadata":{"annotations":{},"name":"nginx-deployment-test","namespace":"default"},"spec":{"replicas":4,"se...
Selector:               app=nginx
Replicas:               6 desired | 6 updated | 6 total | 6 available | 0 unavailable
StrategyType:           RollingUpdate
MinReadySeconds:        0
RollingUpdateStrategy:  25% max unavailable, 25% max surge
Pod Template:
  Labels:  app=nginx
  Containers:
   nginx:
    Image:        nginx:1.7.9
    Port:         80/TCP
    Host Port:    0/TCP
    Environment:  <none>
    Mounts:       <none>
  Volumes:        <none>
Conditions:
  Type           Status  Reason
  ----           ------  ------
  Progressing    True    NewReplicaSetAvailable
  Available      True    MinimumReplicasAvailable
OldReplicaSets:  <none>
NewReplicaSet:   nginx-deployment-test-75675f5897 (6/6 replicas created)
Events:
  Type    Reason             Age   From                   Message
  ----    ------             ----  ----                   -------
  Normal  ScalingReplicaSet  8h    deployment-controller  Scaled up replica set nginx-deployment-test-75675f5897 to 4
  Normal  ScalingReplicaSet  8h    deployment-controller  Scaled up replica set nginx-deployment-test-75675f5897 to 6
```

## check rollout status

```bash
kubectl rollout status deployment nginx-deployment-test
```

rollout history

```bash
$ kubectl rollout history deployment nginx-deployment-test
deployments "nginx-deployment-test"
REVISION  CHANGE-CAUSE
1         <none>
2         <none>
$ kubectl rollout history deployment nginx-deployment-test --revision 2
deployments "nginx-deployment-test" with revision #2
Pod Template:
  Labels:	app=nginx
	pod-template-hash=703038527
  Containers:
   nginx:
    Image:	nginx:1.9.1
    Port:	80/TCP
    Host Port:	0/TCP
    Environment:	<none>
    Mounts:	<none>
  Volumes:	<none>

```

## rollout undo

```bash
$ kubectl rollout undo deployment nginx-deployment-test
deployment.apps "nginx-deployment-test"
```