PWA‌:

برنامه های وب پیشرفته با یک وب سایت/برنامه سنتی شروع می شوند و به تدریج با ویژگی های مدرن بهبود می یابند. وقتی سایت‌ها امن هستند، می‌توانند از ServiceWorkers برای کاربران ارائه‌دهنده با پشتیبانی آفلاین استفاده کنند، اعلان‌های Push می‌توانند به جذب مجدد کاربران کمک کنند، و Web App Manifests به کاربران اجازه می‌دهد PWA را در کنار برنامه‌های بومی نصب کنند.




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


