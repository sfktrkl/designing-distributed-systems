### Deploying an Ambassador and Memcache for a Sharded Cache

```bash
kubectl create -f memcached-shards.yml
kubectl create -f memcached-service.yml
```

```bash
kubectl create configmap twem-config --from-file=nutcracker.yml
kubectl create -f shared-twemproxy-deployment.yml
kubectl create -f shared-twemproxy-service.yml
```

```bash
kubectl port-forward service/shared-twemproxy-service 11211:11211
```

```bash
telnet localhost 11211
```

- Use any memcached command after connection is accepted.

```bash
kubectl port-forward service/shared-twemproxy-service 6222:6222
```

- Go to http://localhost:6222 to see the stats of the twemproxy.
- It will show the name of the pod, use private windows.
