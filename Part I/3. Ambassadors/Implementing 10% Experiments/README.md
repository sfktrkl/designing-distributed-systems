## Delete local cluster

```bash
minikube delete
```

### Manual

```bash
kubectl create configmap experiment-config --from-file=nginx.conf
kubectl create -f experiment.yml
kubectl create -f prod.yml
kubectl create -f ambassador.yml
```
