### Building a Consistent HTTP Sharding Proxy

```bash
kubectl create -f dictionary-deployment.yml
kubectl create -f dictionary-service.yml
```

```bash
kubectl create configmap nginx-config --from-file=nginx.conf
kubectl create -f nginx-deployment.yml
kubectl create -f nginx-service.yml
kubectl create -f nginx-service-nodeport.yml
```

```bash
minikube ip
```

- Go to http://minikube-ip:30080/dog
- Go to http://minikube-ip:30080/bear
- Go to http://minikube-ip:30080/pig
- They will be served by different pods.
