PWA‌:

- فقط روی پروتکل HTTPS کار می‌کنند. مطمئن شوید که وب‌سایت شما از HTTPS استفاده می‌کند

- سرویس ورکر باید فعال باشد

- code service worker : 

if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/service-worker.js')
    .then(() => console.log('Service Worker Registered'))
    .catch(err => console.error('Service Worker Registration Failed:', err));
}

- display:
-  مقدار این ویژگی باید روی standalone تنظیم شود تا اپلیکیشن به صورت مستقل اجرا شود.

-  مقدار scope در فایل منیفست
-  "scope": "/"

- حذف ویژگی‌های غیرضروری مانند display_override.


