# Designing Distributed Systems

Brendan Burns: "Designing Distributed Systems: Patterns and Paradigms for Scalable, Reliable Services", 1st Edition, February 2018

## Installation Steps for Docker

### [Install Docker](https://docs.docker.com/engine/install/ubuntu/)

```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

```bash
sudo docker run hello-world
```

### [Post-Install Docker](https://docs.docker.com/engine/install/linux-postinstall/)

```bash
sudo groupadd docker
```

```bash
sudo usermod -aG docker $USER
```

```bash
newgrp docker
```

```bash
docker run hello-world
```

### [Install Compose Plugin](https://docs.docker.com/compose/install/linux/)

```bash
sudo apt-get update
sudo apt-get install docker-compose-plugin
```

```bash
sudo docker compose version
```

## Installation Steps for Kubernetes

### [Install Minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download)

```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64
```

```bash
minikube start
```

```bash
minikube kubectl -- get po -A
```

```bash
alias kubectl="minikube kubectl --"
```

```bash
kubectl cluster-info
```

### [Post-Install Minikube](https://minikube.sigs.k8s.io/docs/handbook/kubectl/)

```bash
sudo ln -s $(which minikube) /usr/local/bin/kubectl
```

## Installation Steps for mkcert

### Install [brew](https://brew.sh/)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```bash
test -d ~/.linuxbrew && eval "$(~/.linuxbrew/bin/brew shellenv)"
test -d /home/linuxbrew/.linuxbrew && eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
echo "eval \"\$($(brew --prefix)/bin/brew shellenv)\"" >> ~/.bashrc
```

### Install [mkcert](https://github.com/FiloSottile/mkcert)

```bash
sudo apt install libnss3-tools
```

```bash
brew install mkcert
```

## Installation Steps for Knative

### Install [cosign](https://docs.sigstore.dev/system_config/installation/)

```bash
brew install cosign

```

### Install [jq](https://jqlang.github.io/jq/download/)

```bash
sudo apt-get install jq
```

### Install [Knative](https://knative.dev/docs/install/yaml-install/serving/install-serving-with-yaml/#verifying-image-signatures)

```bash
curl -sSL https://github.com/knative/serving/releases/download/knative-v1.15.1/serving-core.yaml \
  | grep 'gcr.io/' | awk '{print $2}' | sort | uniq \
  | xargs -n 1 \
    cosign verify -o text \
      --certificate-identity=signer@knative-releases.iam.gserviceaccount.com \
      --certificate-oidc-issuer=https://accounts.google.com
```

```bash
kubectl apply -f https://github.com/knative/serving/releases/download/knative-v1.15.1/serving-crds.yaml
kubectl apply -f https://github.com/knative/serving/releases/download/knative-v1.15.1/serving-core.yaml
```

```bash
kubectl apply -f https://github.com/knative/net-kourier/releases/download/knative-v1.15.1/kourier.yaml
```

```bash
kubectl patch configmap/config-network \
  --namespace knative-serving \
  --type merge \
  --patch '{"data":{"ingress-class":"kourier.ingress.networking.knative.dev"}}'
```

```bash
kubectl --namespace kourier-system get service kourier
```

## Other Helpful Commands

### How to use Compose plugin?

```bash
docker compose up -d
```

```bash
docker compose down
```

### How to view/delete/describe Kubernetes resources?

```bash
kubectl get po
kubectl delete po pod-name
kubectl describe po pod-name
```

```bash
kubectl get svc
kubectl delete svc service-name
kubectl describe svc service-name
```

```bash
kubectl get cm
kubectl delete cm configmap-name
kubectl describe cm configmap-name
```

```bash
kubectl get deploy
kubectl delete deploy deployment-name
kubectl describe deploy deployment-name
```

### How to view Kubernetes logs?

```bash
kubectl logs pod-name
```

```bash
kubectl logs pod-name -c container-name
```

### How to push to Docker?

```bash
docker login
```

```bash
docker build -t your-username/image-name:tag .
```

```bash
docker images
```

```bash
docker tag local-image:tag your-username/image-name:tag
```

```bash
docker push your-username/image-name:tag
```

### How to create the local CA and certificate a domain in mkcert?

```bash
mkcert -install
```

```bash
mkcert localhost
```
