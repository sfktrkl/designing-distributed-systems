### Manual

```bash
sudo docker run -p 8080:80 --name web nginx
sudo docker run -p 8081:8080 --pid=container:web brendanburns/topz:db0fa58 /server --addr=0.0.0.0:8080
```

- Go to localhost:8080
- Go to localhost:8081/topz

### Compose

```bash
docker compose up -d
```

- Go to localhost:8080
- Go to localhost:8081/topz
