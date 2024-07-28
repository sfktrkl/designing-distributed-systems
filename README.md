# Designing Distributed Systems

Brendan Burns: "Designing Distributed Systems: Patterns and Paradigms for Scalable, Reliable Services", 1st Edition, February 2018

## Install Docker

- https://docs.docker.com/engine/install/ubuntu/

```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
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

## Install Compose plugin

- https://docs.docker.com/compose/install/linux/

```bash
sudo apt-get update
sudo apt-get install docker-compose-plugin
```

```bash
sudo docker compose version
```

## Use Compose plugin

- Start container

```bash
sudo docker compose up -d
```

- Stop container

```bash
sudo docker compose down
```
