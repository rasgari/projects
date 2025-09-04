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
