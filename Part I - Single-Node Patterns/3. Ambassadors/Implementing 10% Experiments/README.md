### Implementing 10% Experiments

```bash
kubectl create -f experiment-config.yml
kubectl create -f experiment.yml
```

```bash
kubectl port-forward experiment 30080:8080
```

- Go to localhost:30080 and refresh the page.
