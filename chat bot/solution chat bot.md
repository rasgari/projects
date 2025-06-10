# solution chat bot

1- unknown runtime specified nvidia :

پیکربندی رانتایم NVIDIA را به داکر اضافه کنید. فایل /etc/docker/daemon.json باید شامل بخش زیر باشد:

json
```bash
{
  "runtimes": {
    "nvidia": {
      "path": "nvidia-container-runtime",
      "runtimeArgs": []
    }
  }
}
```

پس از ویرایش فایل، داکر را ریستارت کنید:

```bash
sudo systemctl daemon-reload
sudo systemctl restart docker
```


2-
