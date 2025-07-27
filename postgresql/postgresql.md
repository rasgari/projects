# postgresql

## error:
pq: no space left on device

یعنی دیسک پر شده و PostgreSQL نمی‌تونه اطلاعات جدید ذخیره کنه.

❌ توجه خیلی مهم:
پوشه‌ی base در PostgreSQL رو اصلاً پاک نکن!

این پوشه تمام دیتابیس‌ها رو در خودش نگه‌می‌داره. پاک‌کردنش = نابودی کامل دیتای PostgreSQL

✅ مراحل رفع مشکل در ویندوز
1. 🧊 بررسی فضای دیسک
روی درایوی که PostgreSQL نصب شده (معمولاً C:\ یا D:\) راست‌کلیک کن → Properties → ببین چقدر فضای خالی داره.

2. 🔍 پیدا کردن پوشه‌هایی که حجم زیاد گرفتن
ابزار سریع:
از File Explorer برو به مسیر:

```
C:\Program Files\PostgreSQL\
```
یا محل نصب MapServer/GeoServer/پایگاه‌داده‌ات (اگر Docker نیست).

از نرم‌افزار رایگان مثل TreeSize Free استفاده کن:
```
https://www.jam-software.com/treesize_free
```
→ می‌گه کدوم فولدر حجم زیادی گرفته.

3. 🧹 پاک‌سازی مطمئن فضای اشغال‌شده
مواردی که می‌تونی پاک کنی (امن):
✅ پاک‌سازی لاگ‌های PostgreSQL:

```
C:\Program Files\PostgreSQL\<version>\data\pg_log\
```

→ فایل‌های .log چند گیگ حجم می‌گیرن. می‌تونی فایل‌های قدیمی رو پاک کنی.

✅ پاک کردن کش ویندوز و موقت‌ها:

اجرا کن:

matlab
Copy
Edit
Win + R → %temp%
و همه فایل‌ها رو پاک کن.

Disk Cleanup:

mathematica
Copy
Edit
Start → Disk Cleanup → انتخاب درایو → پاک‌کردن Temporary files، Thumbnailها و غیره
✅ سطل زباله (Recycle Bin) رو خالی کن.

4. 🧾 در خود PostgreSQL:
اگر هنوز فضای کمی داری ولی می‌تونی باهاش ارتباط بگیری:
وارد pgAdmin شو یا psql و اجرا کن:

sql
Copy
Edit
VACUUM FULL;
→ جدول‌ها رو فشرده می‌کنه.

5. 🧭 جابه‌جا کردن دیتا به درایو دیگر
اگر یک درایو دیگر داری (مثلاً D:)، می‌تونی پوشه دیتا رو منتقل کنی.

مراحل:
Stop PostgreSQL service

کل پوشه data رو از:

kotlin
Copy
Edit
C:\Program Files\PostgreSQL\<version>\data
منتقل کن به مثلاً:

makefile
Copy
Edit
D:\PostgresData\
فایل postgresql.conf رو باز کن و مسیر data_directory رو تغییر بده به:

ini
Copy
Edit
data_directory = 'D:/PostgresData'
دوباره سرویس PostgreSQL رو Start کن.

6. اگر از MapServer یا GeoServer با PostgreSQL استفاده می‌کنی:
بررسی کن که فایل‌های cache یا output اون‌ها کجا ذخیره می‌شن (مثلاً temp, logs, یا mapcache) و اون‌ها رو هم پاکسازی کن.

======================================================================
======================================================================
