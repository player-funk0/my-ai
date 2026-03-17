# SmartVoiceAssistant (Kotlin)

## 🇸🇦 شرح بالعربي

تطبيق مساعد صوتي بسيط يعمل مثل مساعد الهاتف:
- يستمع للأوامر بالصوت باستخدام `SpeechRecognizer`
- يحوّل الكلام إلى نص
- يفسّر النص إلى أوامر داخل `CommandParser`
- ينفّذ الأوامر على الهاتف عن طريق `ActionExecutor` (Intents + فلاش + كاميرا)
- يرد عليك بالصوت باستخدام `TextToSpeech`
- يحتوي على خدمة إمكانية وصول مستقبلية `AssistantAccessibilityService`

### ما الذي يفعله التطبيق؟
- **فتح تطبيقات**: واتساب، يوتيوب، الكاميرا، الإعدادات  
- **التحكم في الفلاش**: تشغيل / إيقاف فلاش الكاميرا (الكشاف)  
- **إرسال رسالة واتساب**:
  - إلى **رقم مباشرة** (مفضل وأسهل)
  - أو إلى **اسم** (Demo بسيط داخل الكود)

### أمثلة أوامر مدعومة
- "open WhatsApp"
- "open YouTube"
- "open camera"
- "open settings"
- "turn on flashlight"
- "turn off flashlight"
- "send message to Ahmed saying hello"
- "send message to 0123456789 saying hello"
- "ابعت ل 0123456789 قول hello"
- "افتح الواتس و ابعت ل 0123456789 الرسالة ازيك"
- "افتح واتساب و ابعت ل Ahmed قول hello"

### ملاحظات عن إرسال واتساب
- **إرسال لرقم مباشرة (مفضل)**  
  استخدم أمر فيه الرقم، مثل:  
  `send message to 0123456789 saying hello`
- **إرسال لاسم (Demo)**  
  يوجد mapping بسيط في `ActionExecutor.kt` يربط الاسم (مثل Ahmed) برقم هاتف.  
  عدّل رقم Ahmed لرقمك الحقيقي قبل الاستخدام.

### طريقة تثبيت وتشغيل التطبيق (بشكل عام)
هذا المشروع يحتوي على **سورس كود تطبيق أندرويد** فقط (Kotlin + Resources). لتحويله إلى APK وتثبيته على الهاتف تحتاج إلى بيئة تطوير أندرويد:

1. ثبّت Android Studio (أو أي IDE يدعم مشاريع Gradle وKotlin لأندرويد).
2. افتح المجلد `SmartVoiceAssistant` كمشروع جديد في الـIDE.
3. انتظر حتى ينتهي Sync لمشروع Gradle.
4. نفّذ عملية **Build** للتطبيق (Debug أو Release) لتوليد ملف APK.
5. انسخ ملف الـAPK الناتج إلى هاتفك.
6. من إعدادات الهاتف، فعّل تثبيت التطبيقات من مصادر غير معروفة (إن احتجت).
7. افتح ملف الـAPK على الهاتف ثم اضغط **Install**.

### الصلاحيات المطلوبة على الهاتف
- إذن الميكروفون: لتحويل الصوت إلى نص.
- إذن الكاميرا: لفتح الكاميرا والتحكم في الفلاش.

### خدمة إمكانية الوصول (للمستقبل)
تم تجهيز خدمة `AssistantAccessibilityService` لتُستخدم لاحقًا لأتمتة واجهات التطبيقات الأخرى.  
بعد تثبيت التطبيق ووجود إعدادات الخدمة داخل الـAPK يمكنك تفعيلها من:
Settings → Accessibility → Installed services → Assistant automation service

---

## 🇬🇧 English Description

SmartVoiceAssistant is a simple voice assistant app:
- Listens to your voice using `SpeechRecognizer`
- Converts speech to text
- Parses the text into commands via `CommandParser`
- Executes phone actions via `ActionExecutor` (Intents + flashlight + camera)
- Replies using `TextToSpeech`
- Includes a prepared `AssistantAccessibilityService` for future UI automation

### What can it do?
- **Open apps**: WhatsApp, YouTube, Camera, Settings  
- **Control flashlight**: turn the torch on / off  
- **Send WhatsApp messages**:
  - Directly to a **phone number** (recommended)
  - Or to a **contact name** (simple demo mapping inside the code)

### Example commands
- "open WhatsApp"
- "open YouTube"
- "open camera"
- "open settings"
- "turn on flashlight"
- "turn off flashlight"
- "send message to Ahmed saying hello"
- "send message to 0123456789 saying hello"
- "ابعت ل 0123456789 قول hello"
- "افتح الواتس و ابعت ل 0123456789 الرسالة ازيك"
- "افتح واتساب و ابعت ل Ahmed قول hello"

### WhatsApp sending notes
- **Send to a phone number (recommended)**  
  Use a command that contains the number, for example:  
  `send message to 0123456789 saying hello`
- **Send to a name (demo only)**  
  There is a simple name → number mapping inside `ActionExecutor.kt` (e.g. Ahmed).  
  Edit Ahmed’s number to a real phone number before using.

### How to build and install (high‑level)
This folder contains **Android app source code only** (Kotlin + resources).  
To turn it into an APK and install it on a phone you need an Android build environment:

1. Install Android Studio (or any IDE that supports Android Gradle + Kotlin projects).
2. Open the `SmartVoiceAssistant` folder as a project.
3. Wait until Gradle sync finishes successfully.
4. Run a **Build** (Debug or Release) to generate an APK.
5. Copy the produced APK file to your Android phone.
6. On the phone, enable “Install unknown apps” for your file manager / browser (if needed).
7. Open the APK file on the phone and press **Install**.

### Required runtime permissions
- Microphone permission: for speech recognition.
- Camera permission: to open the camera and control the flashlight.

### Accessibility service (for future use)
The app defines `AssistantAccessibilityService` which can later be used to automate other apps’ UIs.  
Once you have a built APK that includes this service, you can enable it from:
Settings → Accessibility → Installed services → Assistant automation service

