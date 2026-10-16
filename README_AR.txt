لياقتي — مشروع أندرويد لتحويل التطبيق إلى APK

مهم:
- هذا مشروع Android حقيقي يحتوي على غلاف Android WebView وواجهة التطبيق داخل assets/index.html.
- لم أتمكن من تجميع APK في بيئة العمل الحالية لأنها لا تحتوي على Android SDK أو Gradle، كما أن تنزيل أدوات البناء غير متاح من هذه البيئة. لذلك لن أزعم أن ملف APK جاهز.
- يحتوي المشروع على GitHub Actions workflow لبناء APK تلقائياً بعد رفع المشروع إلى مستودع GitHub.

الطريقة المختصرة للبناء عبر GitHub من الهاتف:
1. أنشئ مستودعاً جديداً على GitHub.
2. ارفع جميع ملفات هذا المشروع كما هي إلى المستودع، مع إظهار الملفات المخفية مثل مجلد .github.
3. افتح تبويب Actions وشغّل "Build Liaqati APK" عبر Run workflow.
4. بعد انتهاء البناء بنجاح، افتح تشغيل Workflow ونزّل artifact باسم liaqati-debug-apk.
5. فك ZIP الناتج، ثم ثبّت app-debug.apk على هاتف Android. قد يطلب الهاتف السماح بالتثبيت من هذا المصدر.

للبناء محلياً باستخدام Android Studio:
- افتح مجلد المشروع LiaqatiAndroid.
- استخدم JDK 17 وAndroid SDK platform 35.
- نفّذ Gradle task: app > Tasks > build > assembleDebug.
- APK الناتج: app/build/outputs/apk/debug/app-debug.apk

هذه نسخة Debug للتجربة وليست نسخة متجر موقّعة للنشر. قبل نشرها على Google Play يلزم إعداد توقيع إصدار Release ومراجعة سياسات المتجر.
