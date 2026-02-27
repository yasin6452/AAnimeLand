# AAnimeLand Android App

اپ اندروید برای سایت aanimeland.ir

---

## ساختار پروژه

```
AAnimeLand/
├── app/
│   ├── src/main/
│   │   ├── java/ir/aanimeland/app/
│   │   │   └── MainActivity.java
│   │   ├── res/
│   │   │   ├── layout/activity_main.xml
│   │   │   ├── values/styles.xml
│   │   │   └── values/strings.xml
│   │   └── AndroidManifest.xml
│   └── build.gradle
├── gradle/wrapper/
├── build.gradle
└── settings.gradle
```

---

## مراحل بیلد APK

### ۱. نصب Android Studio
از سایت developer.android.com/studio دانلود و نصب کنید

### ۲. باز کردن پروژه
- Android Studio را باز کنید
- روی **"Open"** کلیک کنید
- پوشه AAnimeLand را انتخاب کنید

### ۳. Sync پروژه
- صبر کنید Gradle Sync کامل شود (اولین بار چند دقیقه طول می‌کشد)
- اگر خطا دید: **File > Sync Project with Gradle Files**

### ۴. افزودن آیکون (اختیاری)
- راست‌کلیک روی پوشه `res`
- **New > Image Asset**
- آیکون دلخواه را اضافه کنید

### ۵. بیلد APK
**روش ۱ - Debug APK (برای تست):**
```
Build > Build Bundle(s) / APK(s) > Build APK(s)
```
فایل APK در مسیر زیر ساخته می‌شود:
`app/build/outputs/apk/debug/app-debug.apk`

**روش ۲ - Release APK (برای انتشار):**
```
Build > Generate Signed Bundle / APK
```
- APK را انتخاب کنید
- یک Keystore بسازید (برای اولین بار)
- فایل امضاشده در `app/build/outputs/apk/release/` خواهد بود

---

## انتشار APK روی سایت

بعد از بیلد، فایل APK را روی سایت وردپرسی آپلود کنید:
1. وارد پیشخوان وردپرس شوید
2. **رسانه > افزودن** - فایل APK را آپلود کنید
3. لینک دانلود را در صفحه مورد نظر قرار دهید

**نکته:** برای آپلود APK در وردپرس، باید mime type را اضافه کنید:
در فایل `functions.php` قالب خود این کد را اضافه کنید:
```php
function add_apk_mime_type($mimes) {
    $mimes['apk'] = 'application/vnd.android.package-archive';
    return $mimes;
}
add_filter('upload_mimes', 'add_apk_mime_type');
```

---

## ویژگی‌های اپ
- نمایش کامل سایت aanimeland.ir
- پشتیبانی از JavaScript و DOM Storage
- دکمه Back برای رفتن به صفحه قبل
- صفحه خطا هنگام عدم اتصال به اینترنت
- Progress bar هنگام لود صفحات
- تم تاریک کامل (Full Screen, No Title Bar)
- حداقل Android 5.0 (API 21)

