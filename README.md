# TyutorAI 2.0 — Android APK, boshlang'ich versiya

## Nima tayyor?
- Android WebView orqali `https://test.tyutorai.uz/` ochiladi.
- PHP/MySQL mavjud serverda qoladi, rollar va login saytdan olinadi.
- JavaScript, cookies, dark/light va til almashtirish saytdagi implementatsiyaga bog'liq holda ishlaydi.
- Faqat `test.tyutorai.uz`, `tyutorai.uz`, `www.tyutorai.uz` manzillari ichkarida ochiladi; tashqi havolalar brauzerga o'tadi.
- HTTPS talab qilinadi; noto'g'ri sertifikat qabul qilinmaydi.
- Android fayl tanlash qo'llab-quvvatlanadi; tashqi yuklab olish brauzerga o'tadi.

## APK olishning eng oson usuli (GitHub, bepul)
1. GitHub'da yangi private repository yarating.
2. ZIP ichidagi **barcha fayllarni** repo ildiziga yuklang, `.github/workflows/build-apk.yml` ham.
3. `Actions` → `Build TyutorAI APK` → `Run workflow` bosing.
4. Muvaffaqiyatli tugagach, bajarilgan ish sahifasidagi `TyutorAI-2.0-debug-APK` artifactini yuklab oling.
5. ZIP ichidan `app-debug.apk` ni chiqarib, Android telefonga o'rnating (test uchun).

## Android Studio orqali
- Android Studio'da loyihani oching.
- Agar Gradle wrapper so'ralsa, Gradle 8.9 va Android Gradle Plugin 8.7.3 dan foydalaning.
- `Build` → `Build APK(s)` ni ishga tushiring.
- Debug APK: `app/build/outputs/apk/debug/app-debug.apk`.

## Domenni asosiy serverga almashtirish
`app/src/main/java/uz/tyutorai/mobile/MainActivity.java` ichidagi
`MAIN_URL` qiymatini `https://tyutorai.uz/` ga o'zgartiring. Barcha rollar
bir xil sayt serveridan ishlaydi.

## Keyingi bosqichda zarur testlar
Super Admin rejimiga qaytish, profil, rol navigatsiyasi, til, rang rejimi,
PHP sessiya davomiyligi, mobil responsivlik, fayl yuklash/yuklab olish,
PDF ko'rish, onlayn/offsiz holat, xavfsizlik, notification.

Bu **tayyor loyiha manba kodi**. Ushbu muhitda Android SDK/Gradle mavjud
bo'lmagani uchun APK fayl binari ayni vaqtda yaratilmadi va telefonda test qilinmadi.
Bu debug yig'ilma; Play Store uchun release imzosi va qo'shimcha sinov kerak.
