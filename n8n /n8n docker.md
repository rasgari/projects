# n8n

[ docker hub ](https://hub.docker.com/r/n8nio/n8n) 


## docker pull n8n
```
docker pull docker.n8n.io/n8nio/n8n
```

## docker save
```
docker save -o n8n.tar docker.n8n.io/n8nio/n8n
```


### Updating
Before you upgrade to the latest version make sure to check here if there are any breaking changes which may affect you: Breaking Changes⁠

From your Docker Desktop, navigate to the Images tab and select Pull from the context menu to download the latest n8n image.

You can also use the command line to pull the latest, or a specific version:

Pull latest (stable) version
```
docker pull docker.n8n.io/n8nio/n8n
```

Pull specific version
```
docker pull docker.n8n.io/n8nio/n8n:0.220.1
```

Pull next (unstable) version
```
docker pull docker.n8n.io/n8nio/n8n:next
```

Stop the container and start it again:

Get the container ID:
```
docker ps -a
```

Stop the container with ID container_id:
```
docker stop [container_id]
```

Remove the container (this does not remove your user data) with ID container_id:
```
docker rm [container_id]
```

Start the new container:
```
docker run --name=[container_name] [options] -d docker.n8n.io/n8nio/n8n
```

Updating with Docker Compose
If you run n8n using a Docker Compose file, follow these steps to update n8n:

### Pull latest version
```
docker compose pull
```

### Stop and remove older version
```
docker compose down -v
```

### Start the container
```
docker compose up -d
```
