## Common
```shell
kubectl get all
```
## Name Spaces
```shell
kubectl get namespaces
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

## Switch Context
```shell
aws eks --region ap-southeast-1 update-kubeconfig --name myCluster
```