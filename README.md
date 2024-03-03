# Learn Kubernestes
- minikube and kubernetes

## Version
```shell
➜  ~ kubectl version         
Client Version: v1.29.2
Kustomize Version: v5.0.4-0.20230601165947-6ce0bf390ce3
Server Version: v1.28.3

➜  ~ minikube version
minikube version: v1.32.0
commit: 8220a6eb95f0a4d75f7f2d7b14cef975f050512d

➜  ~ helm version
version.BuildInfo{Version:"v3.14.2", GitCommit:"c309b6f0ff63856811846ce18f3bdc93d2b4d54b", GitTreeState:"clean", GoVersion:"go1.21.7"}
```

## Install
### Install kubernetes
```shell
https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
```

### Install minikube
```shell
https://minikube.sigs.k8s.io/docs/start/
```

### Install helm
```shell
https://helm.sh/#Snap
```

### Install vagrant
```shell
https://developer.hashicorp.com/vagrant/install#linux
```

## Common
```shell
kubectl get all
```

## Pod
### Deploy pod
```shell
kubectl create -f pod.yml
```

### get pods
```shell
kubectl get pods -o wide
```

### describe pod
```shell
kubectl describe pod nginx
```

### delete pod
```shell
kubectl delete pod nginx
```

## Replication Controllers
### Deploy
```shell
kubectl create -f replicationcontroller.yml
```

### get
```shell
kubectl get replicationcontroller
```

## Replica set
### Deploy
```shell
kubectl create -f replicaset.yml
```

### get
```shell
kubectl get replicaset
```

### delete
```shell
kubectl delete replicaset nginx-rs
```

## Deployment
### Deploy
```shell
kubectl create -f deployment.yml --record
```

### get
```shell
kubectl get deployments
```

### delete
```shell
kubectl delete deployments nginx-deployment
```

### update
```shell
kubectl apply -f deployment.yml
```

### check status deployment
```shell
kubectl rollout status deployment.apps/nginx-deployment
```

### check history
```shell
kubectl rollout history deployment.apps/nginx-deployment
```

### rollback
```shell
kubectl rollout undo deployment.apps/nginx-deployment
```

### update CHANGE-CAUSE
```shell
kubectl patch deployment nginx-deployment --patch '{"metadata": {"annotations": {"kubernetes.io/change-cause": "Update version 1"}}}'
```

## Service
### Deploy
```shell
kubectl create -f nodeport.yml
```

### Get url
```shell
minikube service myapp-service --url
```

### Persistent Volume
- get list Persistent Volume
```shell
kubectl get pv 
```
### Persistent Volume Claims
- get list Persistent Volume Claims
```shell
kubectl get pvc
```
### Config Maps
- get list Config Map
```shell
kubectl get configmap
```
