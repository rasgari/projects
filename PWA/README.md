PWA‌:

- فقط روی پروتکل HTTPS کار می‌کنند. مطمئن شوید که وب‌سایت شما از HTTPS استفاده می‌کند

- سرویس ورکر باید فعال باشد

- code service worker : 

if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/service-worker.js')
    .then(() => console.log('Service Worker Registered'))
    .catch(err => console.error('Service Worker Registration Failed:', err));
}
