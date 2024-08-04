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
etcdctl --endpoints=http://localhost:2379 lock mutex
```

- Try to lock the same mutex from another terminal again.
