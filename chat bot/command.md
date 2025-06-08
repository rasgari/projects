# command:

## windows 

- cmd

```bash
docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```

- [ exe ](https://ollama.com/)

- cmd
 
```bash

ollama run llama3.1

```

- [ browser ](http://localhost:3000)


### windows ===>>>

```bash
docker run -it --rm --network=host --add-host=host.docker.internal:host-gateway ghcr.io/open-webui/open-webui:main
```  


## linux 

- [ docker image ](https://hub.docker.com/r/dyrnq/open-webui)

```bash

 docker pull dyrnq/open-webui
```

[ docker hub ](https://hub.docker.com/r/ollama/ollama/tags)

```bash

docker pull ollama/ollama

```

```bash

- docker load -i open-webui
- docker load -i ollama

- docker compose up -d

```

- [ browser ](http://localhost:3000)

```bash

ollama pull llama3.2

```

## help

```bash

ollama -v
ollama --version
ollama start
ollama list
ollama show
ollama ps -start
oolama ps -stop
ollama serve
ollama pull llama3.2

```
