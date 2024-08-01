### Deploying nginx and SSL Termination

```bash
kubectl create -f dictionary-service.yml
kubectl create -f dictionary-deployment.yml
```

```bash
kubectl create configmap varnish-config --from-file=default.vcl
kubectl create -f varnish-service.yml
kubectl create -f varnish-deployment.yml
```

```bash
kubectl create secret generic ssl --from-file=tls.crt=tls.crt --from-file=tls.key=tls.key
```

```bash
kubectl create configmap nginx-config --from-file=nginx.conf
kubectl create -f nginx-service.yml
kubectl create -f nginx-service-nodeport.yml
kubectl create -f nginx-deployment.yml
```

```bash
minikube ip
```

- Go to https://minikube-ip:30082/dog to get a response.
- Check certificate in the browser.
