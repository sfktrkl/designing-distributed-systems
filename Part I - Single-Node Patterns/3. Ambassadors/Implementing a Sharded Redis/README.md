### Implementing a Sharded Redis

```bash
kubectl create -f redis-shards.yml
kubectl create -f redis-service.yml
kubectl create configmap twem-config --from-file=nutcracker.yml
kubectl create -f ambassador.yml
```

```bash
kubectl port-forward ambassador 6379:6379
```

```bash
redis-cli -h localhost -p 6379
```

- Use any redis command after connection is accepted.

```bash
kubectl port-forward ambassador 6222:6222
```

- Go to http://localhost:6222 to see the stats of the twemproxy.
