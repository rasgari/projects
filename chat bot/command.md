command:

## windows 

- cmd

```bash
docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```

- exe
https://ollama.com/

- cmd
ollama run llama3.1
  
- browser 
http://localhost:3000

  


## linux 

- docker image
https://hub.docker.com/r/dyrnq/open-webui
===>>> docker pull dyrnq/open-webui


https://hub.docker.com/r/ollama/ollama/tags
===>>> docker pull ollama/ollama


- docker load -i open-webui
- docker load -i ollama

- docker compose up -d

- browser 
http://localhost:3000

ollama pull llama3.2


