### Knative Serverless Functions

```bash
kubectl apply -f helloworld-python-knative.yaml
```

```bash
kubectl get ksvc helloworld-python -o=jsonpath='{.status.url}'
```

```bash
curl -v public-url-of-your-service
```
