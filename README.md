## Tekton安装指南

官方安装文档  

[Install Tekton Pipelines](https://tekton.dev/docs/installation/pipelines/)

[Install Tekton Pipelines](https://tekton.dev/docs/installation/triggers/)

由于Tekton的镜像使用的是google镜像服务，境内机器无法访问gcr.io，拉取不到镜像，导致安装失败。

需要把镜像替换为docker hub.

以下为替换完成的安装版本：

```
git clone git@github.com:C-Q-Native/tekton-install.git

```

安装pipeline


```
kubectl apply -f {version}/tekton-release.yaml
```


安装triggers


```
kubectl apply -f {version}/triggers-release.yaml

kubectl apply -f {version}/triggers-interceptors.yaml

```

观察安装情况：

```
kubectl get pods --namespace tekton-pipelines --watch
```

