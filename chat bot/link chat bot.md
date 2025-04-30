## link chat bot:

# open web ui

[ website main ](https://openwebui.com/)

[github open webui](https://github.com/open-webui/open-webui/tree/main)

[ docs open webui ](https://docs.openwebui.com/)


# ollama

[ github ollama ](https://github.com/ollama/ollama)

[ site ollama ](https://ollama.com)

[ model ollama library ](https://ollama.com/library)


# llama

[ site llama ](https://www.llama.com/)


آموزش نصب و راه اندازی open webui ===>>>
بعد از نصب داکر این دستور در cmd وارد می کنید
```bash

docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main

```
مرورگر را باز کنید و به آدرس
''http://localhost:3000''
بروید
