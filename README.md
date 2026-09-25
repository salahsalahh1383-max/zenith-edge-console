# VodiWalker — Cloudflare Worker Panel

این پروژه نسخه کامل پنل Worker است و شامل رابط مدیریت، ساخت و مدیریت کانفیگ‌های VLESS/Trojan، لینک اشتراک، تاریخ انقضا، آمار مصرف و مسیرهای اتصال تلگرام است.

## انتشار با Wrangler

1. داخل همین پوشه اجرا کن: `npm install`
2. برای بررسی بدون انتشار اجرا کن: `npm run check`
3. وارد Cloudflare شو: `npx wrangler login`
4. برای انتشار اجرا کن: `npm run deploy`

فایل `wrangler.toml` از قبل به دیتابیس D1 موجود با نام `vodi-independent-db` متصل شده است. توکن یا رمز داخل این پروژه قرار نگرفته است. این پروژه باید به‌عنوان **Worker** منتشر شود، نه Pages Static Upload.

## انتشار از داشبورد

در Cloudflare به Workers & Pages برو، Create application و سپس Deploy a Worker را انتخاب کن. نام Worker را `vodi-panel` بگذار و محتوای `Source.js` را در ادیتور قرار بده. سپس در Settings → Bindings یک D1 binding با نام `DB` به دیتابیس `vodi-independent-db` اضافه کن.

## تنظیمات امنیتی

رمز مدیریت را فقط بعد از اولین اجرا از داخل پنل تنظیم کن. توکن Cloudflare و توکن ربات تلگرام را داخل کد، ZIP یا چت قرار نده؛ آن‌ها باید به‌صورت Secret/Environment Variable تنظیم شوند.
