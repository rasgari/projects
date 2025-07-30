[reference](https://github.com/ollama/ollama)

## Quickstart

## link video youtube

[![Watch the video](https://img.youtube.com/vi/n2Xjgh-vqv8/0.jpg)](https://www.youtube.com/watch?v=n2Xjgh-vqv8)


To run and chat with [Llama 3.2](https://ollama.com/library/llama3.2):

```shell
ollama run llama3.2
```

## Model library

Ollama supports a list of models available on [ollama.com/library](https://ollama.com/library 'ollama model library')

Here are some example models that can be downloaded:

| Model              | Parameters | Size  | Download                         |
| ------------------ | ---------- | ----- | -------------------------------- |
| Gemma 3            | 1B         | 815MB | `ollama run gemma3:1b`           |
| Gemma 3            | 4B         | 3.3GB | `ollama run gemma3`              |
| Gemma 3            | 12B        | 8.1GB | `ollama run gemma3:12b`          |
| Gemma 3            | 27B        | 17GB  | `ollama run gemma3:27b`          |
| QwQ                | 32B        | 20GB  | `ollama run qwq`                 |
| DeepSeek-R1        | 7B         | 4.7GB | `ollama run deepseek-r1`         |
| DeepSeek-R1        | 671B       | 404GB | `ollama run deepseek-r1:671b`    |
| Llama 3.3          | 70B        | 43GB  | `ollama run llama3.3`            |
| Llama 3.2          | 3B         | 2.0GB | `ollama run llama3.2`            |
| Llama 3.2          | 1B         | 1.3GB | `ollama run llama3.2:1b`         |
| Llama 3.2 Vision   | 11B        | 7.9GB | `ollama run llama3.2-vision`     |
| Llama 3.2 Vision   | 90B        | 55GB  | `ollama run llama3.2-vision:90b` |
| Llama 3.1          | 8B         | 4.7GB | `ollama run llama3.1`            |
| Llama 3.1          | 405B       | 231GB | `ollama run llama3.1:405b`       |
| Phi 4              | 14B        | 9.1GB | `ollama run phi4`                |
| Phi 4 Mini         | 3.8B       | 2.5GB | `ollama run phi4-mini`           |
| Mistral            | 7B         | 4.1GB | `ollama run mistral`             |
| Moondream 2        | 1.4B       | 829MB | `ollama run moondream`           |
| Neural Chat        | 7B         | 4.1GB | `ollama run neural-chat`         |
| Starling           | 7B         | 4.1GB | `ollama run starling-lm`         |
| Code Llama         | 7B         | 3.8GB | `ollama run codellama`           |
| Llama 2 Uncensored | 7B         | 3.8GB | `ollama run llama2-uncensored`   |
| LLaVA              | 7B         | 4.5GB | `ollama run llava`               |
| Granite-3.2         | 8B         | 4.9GB | `ollama run granite3.2`          |

> [!NOTE]
> You should have at least 8 GB of RAM available to run the 7B models, 16 GB to run the 13B models, and 32 GB to run the 33B models.


```bash

docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama

```

Open WebUI یک پلتفرم هوش مصنوعی قابل گسترش و کاربرپسند است که به شما امکان می‌دهد به صورت کاملاً آفلاین با مدل‌های زبان بزرگ (LLM) تعامل داشته باشید. این ابزار قابلیت بارگذاری اسناد سفارشی را دارد تا بتوانید از آنها به عنوان منبع اطلاعات در پاسخ‌های چت استفاده کنید. در ادامه توضیح داده شده که چگونه می‌توانید فایل‌های آموزشی (مانند FAQ) را آپلود کنید تا چت‌بات بتواند بر اساس آن پاسخ دهد.




نصب Docker Desktop از وب‌سایت رسمی Docker.

فعال کردن WSL2 (Windows Subsystem for Linux) برای پشتیبانی بهتر از Docker.

دانلود و اجرای Open WebUI
Open WebUI یکی از بهترین گزینه‌ها برای اجرای چت‌بات لوکال است.

مراحل نصب:
اجرای دستور زیر در Docker:

```bash

docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main

```

دسترسی به رابط کاربری:

مرورگر را باز کنید و به آدرس 'http://localhost:3000' بروید.

حساب کاربری ایجاد کنید و مدل مورد نظر خود (مانند Llama 3) را انتخاب کنید.

۴. دانلود و استفاده از مدل‌های LLM
مدل‌هایی مانند Llama 3 یا GPT می‌توانند برای پاسخ به سوالات متداول استفاده شوند.

نصب مدل‌ها:
در محیط Open WebUI یا ابزارهایی مانند Ollama، می‌توانید مدل‌ها را دانلود و اجرا کنید:

```bash

ollama run llama3

```

۵. آپلود فایل‌های FAQ
یکی از قابلیت‌های چت‌بات لوکال این است که می‌توانید فایل‌های متنی (مانند PDF یا TXT) مربوط به سوالات متداول را آپلود کنید تا چت‌بات بتواند بر اساس آنها پاسخ دهد.

مراحل آپلود:
فایل FAQ خود را در رابط کاربری Open WebUI آپلود کنید.

از چت‌بات بخواهید که اطلاعات را خلاصه کند یا سوالات شما را پاسخ دهد.

۶. تنظیمات شبکه لوکال
برای دسترسی کاربران شبکه به چت‌بات:

آدرس IP سیستم میزبان را پیدا کنید.

پورت مربوطه (مانند 3000) را باز کنید تا کاربران بتوانند از طریق مرورگر به چت‌بات دسترسی داشته باشند:


'**http://<Your-IP>:3000**'

مزایای این روش
حفظ حریم خصوصی داده‌ها، زیرا همه چیز روی شبکه داخلی باقی می‌ماند.

بدون نیاز به اتصال اینترنت.

قابلیت سفارشی‌سازی کامل برای نیازهای خاص کسب‌وکار.

با این روش‌ها، می‌توانید یک چت‌بات هوش مصنوعی قدرتمند برای پاسخگویی به سوالات متداول در شبکه لوکال راه‌اندازی کنید.

اگر بخواید مانیتورینگ داشته باشید
grafana & promethus 
فعال کنید که روند memory & CPU  مشاهده کنید


[persian LLAMA 13B ](https://huggingface.co/ViraIntelligentDataMining/PersianLLaMA-13B)
[ github mistral ](https://github.com/mehdihosseinimoghadam/AVA-Mistral-7B)

```bash
./main -t 10 -ngl 32 -m persian_llama_7b.Q4_K_M.gguf --color -c 2048 --temp 0.7 --repeat_penalty 1.1 -n -1 -p "### Instruction: یک شعر حماسی در مورد کوه دماوند بگو ### Input:  ### Response:"

```
