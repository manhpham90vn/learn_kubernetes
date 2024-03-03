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

## Kuberneters
- Kubernetes is an open-source container orchestration system for automating software deployment, scaling, and management.

## Cluster
- a set of node machines which are running the Containerized Application (Worker Nodes) or control other Nodes (Master Node)

## Node
- a node refers to a physical or virtual machine that serves as a worker machine in a Kubernetes cluster. Each node is responsible for running containers and managing networking, storage, and other components required to run applications.

### Worker Node
- A node, also known as a worker or a minion, is a machine where containers (workloads) are deployed. Every node in the cluster must run a container runtime, as well as the below-mentioned components, for communication with the primary network configuration of these containers.
- Each node in a Kubernetes cluster can run multiple pods, which are the smallest deployable units in Kubernetes, consisting of one or more containers that share resources and networking

### Master Node
- The Kubernetes master node handles the Kubernetes control plane of the cluster, managing its workload and directing communication across the system.

## Pod
- The basic scheduling unit in Kubernetes is a pod, which consists of one or more containers that are guaranteed to be co-located on the same node. Each pod in Kubernetes is assigned a unique IP address within the cluster, allowing applications to use ports without the risk of conflict. Within the pod, all containers can reference each other.

- A container resides inside a pod. The container is the lowest level of a micro-service, which holds the running application, libraries, and their dependencies.

## ReplicationController

## ReplicaSet

## Service
- a service is an abstract way to expose an application running on a set of Pods (one or more) as a network service. It provides a stable endpoint (IP address and port) that other applications can use to communicate with the Pods backing the Service

### LoadBalancer

### NodePort

### ClusterIP

## Deployment

## Volume

### emptyDir

### hostPath

### Persistent Volumes

### persistentVolumeClaim

## Network

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