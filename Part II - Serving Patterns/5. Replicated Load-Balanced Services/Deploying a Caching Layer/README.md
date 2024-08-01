### Deploying a Caching Layer

```bash
kubectl create -f dictionary-service.yml
kubectl create -f dictionary-deployment.yml
```

```bash
kubectl create configmap varnish-config --from-file=default.vcl
kubectl create -f varnish-service.yml
kubectl create -f varnish-service-nodeport.yml
kubectl create -f varnish-deployment.yml
```

```bash
kubectl exec -it pod-name -- varnishstat
```

```bash
minikube ip
```

- Go to http://minikube-ip:30081/dog to get a response.
- From varnishstat it is possible to see cache hit and cache misses (to toggle counters press 'd').
