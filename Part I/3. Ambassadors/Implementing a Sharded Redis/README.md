## Deploy

```bash
kubectl create -f FILE.yaml
```

## See pods

```bash
kubectl get pods
```

### See services

```bash
kubectl get services
```

### See configmaps

```bash
kubectl get configmaps
```

### Manual

```bash
kubectl create -f redis-shards.yml
kubectl create -f redis-service.yml
kubectl create configmap twem-config --from-file=nutcracker.yml
kubectl create -f ambassador.yml
```
