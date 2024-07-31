### Creating a Replicated Service in Kubernetes

```bash
kubectl create -f dictionary-service.yml
kubectl create -f dictionary-service-nodeport.yml
kubectl create -f dictionary-deployment.yml
```

```bash
minikube ip
```

- Go to http://minikube-ip:30080/dog to get a response.
- It will show the name of the pod, use private windows.
