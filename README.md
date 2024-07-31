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

## Other Helpful Commands

### How to use Compose plugin?

```bash
docker compose up -d
```

```bash
docker compose down
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
