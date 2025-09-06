# Snyk 

یک ابزار امنیت اپلیکیشن و DevOps هست.

تمرکزش روی پیدا کردن آسیب‌پذیری‌های شناخته‌شده (CVE) در:

کتابخانه‌ها و پکیج‌های Third-party (npm, pip, Maven و …)

کانتینرها (Docker Images)

Kubernetes

Infrastructure as Code (IaC) مثل Terraform یا Helm

نمونه استفاده:

اگر توی پروژه Node.js هستی، با دستور:
```
snyk test
```

لیست پکیج‌های آسیب‌پذیر و نسخه امن رو می‌ده.

با snyk monitor می‌تونی پروژه رو مانیتور کنی و اگه بعداً پکیجی آسیب‌پذیر شد بهت هشدار بده.

خیلی جاها با GitHub و GitLab ادغام میشه که Pull Requestها رو قبل از Merge بررسی کنه.
