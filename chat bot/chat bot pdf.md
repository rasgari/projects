# chat bot PDF

راه‌اندازی ساده چت‌بات PDF در داکر (مثال با Haystack)
نصب Docker و Docker Compose
```
docker pull dyrnq/open-webui:git-7a47ba1
docker save -o openwebui-git.tar dyrnq/open-webui:git-7a47ba1
docker load -i openwebui-git.tar
```

نسخه‌ ها به بالا باشه:
```
OpenWebUI v0.6.5
Ollama v0.5.1
```
با نسخه‌ی ۰.۷.۴ به بالا دکمه‌ی Ingest Documents فعال میشه → فایل‌های PDF و Word رو می‌خونه → توی جواب‌ها نشون میده.
 دکمه‌ی Ingest Documents (یا همون RAG / Docs) وجود داشته باشه
پشتیبانی از Document Search / RAG تازه از نسخه‌های 0.7.x به بعد توی OpenWebUI اضافه شد.

🔹 توی نسخه‌ی 0.6.5 هنوز قابلیت Ingest Documents / RAG اضافه نشده بود.
از نسخه‌ی 0.7.x به بعد دکمه‌ی Ingest Documents اومده و می‌تونی PDF / Word بدی تا داخل محیط OpenWebUI سرچ و پاسخ تولید بشه.

```
ایمیج dyrnq/open-webui:git-7a47ba1 رو اجرا کن و به Admin Panel بری → Settings → Documents ببین
```

اجرای سرویس:

```bash
docker-compose up -d
```

آپلود PDF به مسیر ./pdfs و استفاده از API Haystack برای استخراج و پرسش پاسخ.

4. نکات مهم
استخراج دقیق متن از PDF به ساختار فایل و نوع محتوا بستگی دارد (متن ساده، اسکن شده، جدول و غیره).

برای PDFهای اسکن شده نیاز به OCR (مثل Tesseract) دارید که می‌توان آن را هم در داکر اجرا کرد.

مدل‌های هوش مصنوعی معمولاً نیاز به منابع سخت‌افزاری مناسب (GPU) دارند.

جمع‌بندی
برای ساخت چت‌بات داکری که PDF را بخواند، می‌توانید از فریم‌ورک‌هایی مثل Haystack یا LangChain استفاده کنید.

ابتدا متن PDF استخراج می‌شود، سپس با مدل‌های زبان سوالات پاسخ داده می‌شود.

کل سیستم را می‌توان در داکر کانتینر کرد تا به راحتی اجرا و مدیریت شود.

اگر دنبال راه‌حل آماده هستید، سرویس‌های آنلاین مثل ChatPDF هم وجود دارند اما آفلاین و داکری نیستند.



==================================================================

## error RAG / Ingest Documents


```
OSError: We couldn't connect to 'https://huggingface.co' to load this file,
couldn't find it in the cached files...
sentence-transformers/all-MiniLM-L6-v2
```

عنی:
وقتی OpenWebUI می‌خواد ماژول RAG / Ingest Documents رو فعال کنه، نیاز داره یک مدل embedding (مثل all-MiniLM-L6-v2) از HuggingFace بگیره.
ولی سرورت آفلاینه و نمی‌تونه به اینترنت وصل بشه → بنابراین کرش می‌کنه و دکمه Ingest Documents هم عملاً کار نمی‌کنه.

✅ راه حل‌ها
1. بهترین نسخه پایدار با RAG

از OpenWebUI ≥ 0.7.2 به بالا استفاده کن (۰.۷.۴ یا ۰.۸.۰ خوبه).
این نسخه‌ها RAG رو کامل دارن و تست شدن.
نسخه‌های ۰.۶.۵ یا بیلدهای غیررسمی مثل dyrnq/open-webui مشکل‌دارن.

2. رفع خطای بدون اینترنت

چون آفلاین هستی باید embedding model رو دستی بیاری:

روی یک سیستم وصل به اینترنت این دستور رو بزن:
```
git lfs install
git clone https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2
```

یا:
```
wget https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2/resolve/main/config.json
wget https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2/resolve/main/pytorch_model.bin
wget https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2/resolve/main/tokenizer.json
```

پوشه‌ی دانلودشده رو بذار داخل مسیر:
```
./openwebui/embeddings/all-MiniLM-L6-v2
```

به OpenWebUI بگو از همین لوکال لود کن:
توی docker-compose.yml اضافه کن:
```
volumes:
  - ./openwebui:/app/backend/data
  - ./openwebui/embeddings:/root/.cache/huggingface/transformers
```
3. ری‌استارت
```
docker compose down
docker compose up -d
```

بعد از بالا اومدن، دکمه‌ی Ingest Documents در تنظیمات ظاهر میشه و می‌تونی PDF / Word بدی.

🔹 پس:

نسخه پیشنهادی: ghcr.io/open-webui/open-webui:0.7.4 یا بالاتر.

خطا: به خاطر نبودن مدل embedding روی سیستم آفلاین.

راهکار: مدل all-MiniLM-L6-v2 رو دستی دانلود و mount کن.
