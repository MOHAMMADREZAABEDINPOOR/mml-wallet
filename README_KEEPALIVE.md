# راهنمای Keep-Alive برای بات تلگرام

## مشکل
بات‌های تلگرام روی پلتفرم‌های رایگان مثل Heroku، Railway، Render و غیره بعد از مدتی غیرفعال شدن به خواب می‌روند.

## راه‌حل
سیستم Keep-Alive اضافه شده که شامل:

### 1. Heartbeat داخلی
- هر 10 دقیقه یک پیام log می‌زند
- Event loop رو فعال نگه می‌داره
- حافظه رو پاک می‌کنه

### 2. External Ping (اختیاری)
- هر 5 دقیقه به URL مشخص شده ping می‌زنه
- برای سرویس‌هایی که نیاز به HTTP request دارن

## تنظیمات

### متغیرهای محیطی (Environment Variables)

```bash
# فعال/غیرفعال کردن keep-alive
ENABLE_KEEP_ALIVE=true

# URL برای ping کردن (اختیاری)
PING_URL=https://your-app.herokuapp.com/

# فاصله زمانی ping (ثانیه) - پیش‌فرض: 300 (5 دقیقه)
PING_INTERVAL=300
```

### برای Heroku
```bash
heroku config:set ENABLE_KEEP_ALIVE=true
heroku config:set PING_URL=https://your-app-name.herokuapp.com/
heroku config:set PING_INTERVAL=300
```

### برای Railway
```bash
railway variables set ENABLE_KEEP_ALIVE=true
railway variables set PING_URL=https://your-app.railway.app/
railway variables set PING_INTERVAL=300
```

### برای Render
در تنظیمات Environment Variables:
- `ENABLE_KEEP_ALIVE` = `true`
- `PING_URL` = `https://your-app.onrender.com/`
- `PING_INTERVAL` = `300`

## نکات مهم

### 1. تنظیم PING_URL
- اگر بات شما روی webhook اجرا میشه، URL رو روی همون دامنه تنظیم کنید
- اگر polling استفاده می‌کنید، می‌تونید URL رو خالی بذارید

### 2. فاصله زمانی
- کمتر از 5 دقیقه توصیه نمیشه (ممکنه rate limit بخورید)
- بیشتر از 30 دقیقه ممکنه کافی نباشه

### 3. لاگ‌ها
بات هر 10 دقیقه یک پیام heartbeat لاگ می‌کنه:
```
Bot heartbeat: 2024-12-14 15:30:00 UTC
```

## عیب‌یابی

### اگر بات هنوز خاموش میشه:
1. چک کنید `ENABLE_KEEP_ALIVE=true` تنظیم شده باشه
2. لاگ‌ها رو بررسی کنید که heartbeat کار می‌کنه
3. PING_INTERVAL رو کمتر کنید (مثلاً 180 ثانیه)

### اگر خطای timeout میگیرید:
1. PING_URL رو چک کنید درست باشه
2. اگر لازم نیست، PING_URL رو خالی بذارید

## مثال استفاده

```python
# در کد خودتون (اگر دستی می‌خواید کنترل کنید)
from keep_alive import start_keep_alive, stop_keep_alive

# شروع keep-alive
await start_keep_alive("https://myapp.herokuapp.com/", 300)

# توقف keep-alive
await stop_keep_alive()
```

## پشتیبانی از پلتفرم‌ها

✅ Heroku  
✅ Railway  
✅ Render  
✅ PythonAnywhere  
✅ Replit  
✅ سرورهای VPS  

این سیستم روی همه پلتفرم‌های معمول تست شده و کار می‌کنه.