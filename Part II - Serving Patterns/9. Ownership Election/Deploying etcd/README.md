### Deploying etcd

```bash
kubectl create -f etcd-configmap.yml
kubectl create -f etcd-deployment.yml
kubectl create -f etcd-service.yml
```

```bash
kubectl port-forward pod/etcd 2379:2379 -n etcd
```

```bash
etcdctl --endpoints=http://localhost:2379 endpoint health
```

```bash
etcdctl --endpoints=http://localhost:2379 put foo bar
etcdctl --endpoints=http://localhost:2379 get foo
```
