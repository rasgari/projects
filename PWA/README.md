PWA‌:

برنامه های وب پیشرفته با یک وب سایت/برنامه سنتی شروع می شوند و به تدریج با ویژگی های مدرن بهبود می یابند. وقتی سایت‌ها امن هستند، می‌توانند از ServiceWorkers برای کاربران ارائه‌دهنده با پشتیبانی آفلاین استفاده کنند، اعلان‌های Push می‌توانند به جذب مجدد کاربران کمک کنند، و Web App Manifests به کاربران اجازه می‌دهد PWA را در کنار برنامه‌های بومی نصب کنند.

وب اپلیکیشن پیش رونده (Progressive Web App) یا به اختصار PWA این امکان رو به ما میده که از وب سایتمون یه نسخه اپلیکیشن ایجاد کنیم. این مبحث وقتی توی ایران پر رنگ شد که شرکت اپل برنامه های مالی ایران رو محدود کرد و دیگه نمیشد اپلیکیشن های ایرانی ios رو روی گوشی های آیفون نصب کرد. چاره کار همین PWA شد.


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


دو منبع برای نصب pwa که می توانید استفاده کنید

فارسی
https://github.com/alirahimi818/simple-PWA


انگلیسی
https://github.com/khmyznikov/pwa-install

