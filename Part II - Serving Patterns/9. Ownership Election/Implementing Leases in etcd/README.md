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
etcdctl --endpoints=http://localhost:2379 lease grant 300
```

```bash
etcdctl --endpoints=http://localhost:2379 put sample value --lease=2be7547fbc6a5afa
etcdctl --endpoints=http://localhost:2379 get sample
```

```bash
etcdctl --endpoints=http://localhost:2379 lease keep-alive 2be7547fbc6a5afa
etcdctl --endpoints=http://localhost:2379 lease revoke 2be7547fbc6a5afa
```

```bash
etcdctl --endpoints=http://localhost:2379 get sample
```
