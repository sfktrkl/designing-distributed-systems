### Manual

```bash
kubectl create -f prometheus-configmap.yml
kubectl create -f prometheus-deployment.yml
kubectl create -f prometheus-service.yml
```

```bash
kubectl apply -f redis-service.yml
kubectl apply -f redis-exporter-service.yml
kubectl apply -f adapter.yml
```

```bash
kubectl port-forward service/prometheus 9090:9090
```

#### Prometheus

```
redis_up
```
