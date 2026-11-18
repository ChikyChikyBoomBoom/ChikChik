# ChikChik 📸

**English** · [فارسی](#فارسی)

An Android camera app that helps you recreate poses. Put a reference photo over the live camera preview, follow on-screen pose guidance, and browse the built-in Explore screen for new pose ideas.

## Features

- **Camera** — front/back switch, zoom, tap to focus, flash, timer (3 / 5 / 10 s), grid, exposure and white balance controls.
- **Reference overlay** — pick a photo from your gallery and place it over the preview: adjust opacity, move, pinch to scale, rotate, lock, reset, and flip it horizontally.
- **Pose Coach** — live pose detection with dots and short on-screen guidance that tells you how to match the reference. You can show or hide the dots and guidance in Settings.
- **Explore / Inspiration** — search and filter pose photos (gender, style, pose type), save Favorites, see History, find Similar Ideas, and tap **Use as Reference** to send a photo straight to the camera.
- **Saved photos** — captures are saved to the `ChikChik` album and can be shared.
- **Persian / English** — switch language from Settings.
- **Settings** — grid, pose dots & guidance, language, contact, and an About section (version 1.0.0).

## Privacy

- Pose detection runs **on your device** (ML Kit bundled models). No camera frames are uploaded.
- The internet permission is used **only** by Explore to load photos from the Pexels API.
- The camera permission is required for the camera features.

## Tech stack

Kotlin · Jetpack Compose · CameraX · ML Kit Pose Detection · Pexels API
Package `com.chikchik.posecamera` · minSdk 24 · targetSdk 35

## Build

1. Get a free API key at <https://www.pexels.com/api/>.
2. Copy `secrets.properties.example` to `secrets.properties` and set `PEXELS_API_KEY`
   (or provide it as the `PEXELS_API_KEY` environment variable). Never commit this file.
3. Build:
   ```bash
   ./gradlew assembleRelease
   ```
   Output: `app/build/outputs/apk/release/app-release.apk`

**Smaller APK for modern phones (64-bit ARM only):**
```bash
./gradlew assembleRelease -PabiOnly=arm64-v8a
```
Without this option the APK is universal (arm64-v8a, armeabi-v7a, x86, x86_64) and larger.

**Signing:** copy `keystore.properties.example` to `keystore.properties` and fill it in to sign with your own key. Without it, release builds are signed with the debug key (installable, but not suitable for Google Play and not stable across machines).

A GitHub Actions workflow (`.github/workflows/build.yml`) builds the APK on demand (**Actions → Run workflow**).

## Credits

Photos in Explore are provided by [Pexels](https://www.pexels.com) and credit their photographers.

---

<div dir="rtl" align="right">

## فارسی

**ChikChik** یک اپ دوربین اندروید برای بازسازی ژست است. عکس مرجع را روی پیش‌نمایش زنده‌ی دوربین بگذارید، راهنمایی‌های ژست را دنبال کنید و از بخش کاوش ایده‌های تازه پیدا کنید.

### امکانات

- **دوربین** — تعویض دوربین جلو/عقب، زوم، فوکوس با لمس، فلش، تایمر (۳ / ۵ / ۱۰ ثانیه)، خطوط راهنما (Grid)، کنترل نوردهی و تعادل رنگ سفید.
- **عکس مرجع (Overlay)** — یک عکس از گالری انتخاب و روی پیش‌نمایش قرار دهید: تنظیم شفافیت، جابه‌جایی، بزرگ/کوچک کردن با دو انگشت، چرخش، قفل، بازنشانی و برعکس کردن (Flip) افقی.
- **راهنمای ژست (Pose Coach)** — تشخیص زنده‌ی ژست با نقطه‌ها و راهنمایی کوتاه روی صفحه که می‌گوید چطور با عکس مرجع هماهنگ شوید. در تنظیمات می‌توانید نقاط و راهنمایی‌ها را نمایش دهید یا مخفی کنید.
- **کاوش و الهام** — جستجو و فیلتر عکس‌های ژست (جنسیت، سبک، نوع ژست)، علاقه‌مندی‌ها، تاریخچه، ایده‌های مشابه و دکمه‌ی **استفاده به‌عنوان مرجع** برای فرستادن عکس مستقیم به دوربین.
- **ذخیره‌ی عکس‌ها** — عکس‌ها در آلبوم `ChikChik` ذخیره می‌شوند و قابل اشتراک‌گذاری‌اند.
- **فارسی / انگلیسی** — زبان را از تنظیمات عوض کنید.
- **تنظیمات** — Grid، نقاط و راهنمایی ژست، زبان، ارتباط با من و بخش درباره (نسخه‌ی ۱.۰.۰).

### حریم خصوصی

- تشخیص ژست **روی خود گوشی** انجام می‌شود (مدل‌های ML Kit داخل اپ). هیچ تصویری از دوربین آپلود نمی‌شود.
- دسترسی اینترنت **فقط** برای بخش کاوش و دریافت عکس از Pexels استفاده می‌شود.
- دسترسی دوربین برای قابلیت‌های دوربین لازم است.

### ساخت (Build)

1. از <https://www.pexels.com/api/> یک کلید API رایگان بگیرید.
2. فایل `secrets.properties.example` را به `secrets.properties` کپی کنید و `PEXELS_API_KEY` را بنویسید
   (یا آن را به‌صورت متغیر محیطی `PEXELS_API_KEY` بدهید). این فایل را هرگز در گیت قرار ندهید.
3. ساخت:
   ```bash
   ./gradlew assembleRelease
   ```
   خروجی: `app/build/outputs/apk/release/app-release.apk`

**APK کم‌حجم‌تر برای گوشی‌های جدید (فقط ARM ۶۴ بیتی):**
```bash
./gradlew assembleRelease -PabiOnly=arm64-v8a
```
بدون این گزینه، APK یونیورسال است (arm64-v8a، armeabi-v7a، x86، x86_64) و حجم بیشتری دارد.

**امضا:** برای امضا با کلید خودتان، `keystore.properties.example` را به `keystore.properties` کپی و پر کنید. بدون آن، نسخه‌ی Release با کلید debug امضا می‌شود (قابل نصب است، ولی برای گوگل‌پلی مناسب نیست و روی ماشین‌های مختلف کلید ثابتی ندارد).

یک workflow در GitHub Actions (`.github/workflows/build.yml`) هم هست که APK را در صورت درخواست می‌سازد (**Actions ← Run workflow**).

### منابع

عکس‌های بخش کاوش از [Pexels](https://www.pexels.com) هستند و نام عکاس‌ها در اپ نمایش داده می‌شود.

</div>
