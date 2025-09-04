# edu n8n

n8n معمولاً به یک دیتابیس Postgres هم نیاز داره (برای پایدار بودن داده‌ها). من فایل رو جوری می‌نویسم که هم خود n8n و هم Postgres بیاد بالا و داده‌ها توی volume ذخیره بشه.

فایل رو با نام docker-compose.yml ذخیره کن.

دستور زیر رو اجرا کن:
```
docker compose up -d
```

بعدش n8n روی
```
http://localhost:5678
```
 اجرا میکنی

username: admin

password: admin (تغییرش بدید!)


==========================================================

# دامنه و ایمیل
N8N_DOMAIN=n8n.example.com
LETSENCRYPT_EMAIL=you@example.com
TIMEZONE=Asia/Baku

# کلیدهای حساس (قابل تولید با: openssl rand -hex 32)
N8N_ENCRYPTION_KEY=change_me_to_a_random_64_hex

# Postgres
POSTGRES_USER=n8n
POSTGRES_PASSWORD=strong_pg_password
POSTGRES_DB=n8n

# Redis
REDIS_PASSWORD=strong_redis_password

# Worker
WORKER_CONCURRENCY=5

==========================================================


راه‌اندازی

DNS رکورد A/AAAA دامنه N8N_DOMAIN را به IP سرور بدون Proxy/Orange-Cloud اشاره بده (برای HTTP-01).

پوشه‌ها را بساز:

mkdir -p letsencrypt postgres_data redis_data n8n_data
# برای امنیت فایل گواهی
touch letsencrypt/acme.json && chmod 600 letsencrypt/acme.json


اجرا:

docker compose up -d


بعد از چند دقیقه، با https://YOUR_DOMAIN بالا می‌آید.

نکات امنیت و تولید

پس از اولین ورود، یک کاربر ادمین بساز و 2FA را فعال کن.

پورت‌های 80/443 تنها پورت‌های باز روی فایروال باشند؛ پورت 5678 به بیرون باز نشود (Traefik هندل می‌کند).

بکاپ منظم از postgres_data و n8n_data بگیر.

برای مقیاس‌پذیری بیشتر:

docker compose up -d --scale n8n-worker=3

==========================================================
