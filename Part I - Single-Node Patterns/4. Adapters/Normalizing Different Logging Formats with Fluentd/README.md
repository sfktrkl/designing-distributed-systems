### Manual

```bash
kubectl create -f redis-service.yml
kubectl create -f redis-deployment.yml
```

```bash
kubectl create -f fluentd-configmap.yml
kubectl create -f fluentd-deployment.yml
kubectl create -f fluentd-service.yml
```

```bash
kubectl port-forward service/redis 6379:6379
```
