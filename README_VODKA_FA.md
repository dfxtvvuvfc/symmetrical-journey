# VODKA Panel — بدون KV

این نسخه هیچ KV Namespace لازم ندارد و در `wrangler.toml` هیچ KV binding وجود ندارد.

## ورود دو مرحله‌ای
در Cloudflare → Workers → Settings → Variables and Secrets دو Secret بساز:

- `VODKA_DEFAULT_PASSWORD` — رمز مرحله اول
- `VODKA_MASTER_PASSWORD` — رمز اصلی مرحله دوم

رمزها را داخل GitHub یا کد Worker قرار نده.

## Cloudflare
- Build command: خالی
- Deploy command: `npx wrangler deploy`
- Build output directory: خالی

فایل اصلی Worker: `_worker.js`
فایل‌های رابط کاربری: `public/`

## KV
هیچ KV لازم نیست و نباید KV binding اضافه کنی.

## ذخیره دائمی تنظیمات
برای ذخیره دائمی تنظیمات و لاگ‌ها، این نسخه در صورت نیاز از D1 با binding اختیاری `IOT_DB` استفاده می‌کند. اگر D1 نداشته باشی، ورود دو مرحله‌ای با Secretها همچنان کار می‌کند، اما داده‌هایی که نیاز به ذخیره دائمی دارند بعد از اجرای مجدد Worker تضمین نمی‌شوند.
