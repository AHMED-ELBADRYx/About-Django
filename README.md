# الفهرس

- [الفهرس](#الفهرس)
  - [التعريف](#التعريف)
  - [تحميل البيئة الافتراضية](#تحميل-البيئة-الافتراضية)
  - [تعريف الملفات](#تعريف-الملفات)
    - [ملفات المشروع](#ملفات-المشروع)
    - [ملفات التطبيق](#ملفات-التطبيق)
  - [إضافة التطبيق](#إضافة-التطبيق)
  - [إضافة الواجهة](#إضافة-الواجهة)
  - [إضافة الصفحة](#إضافة-الصفحة)
    - [ملاحظات](#ملاحظات)
  - [التعامل مع TEMPLATES](#التعامل-مع-templates)
    - [إضافة القالب](#إضافة-القالب)
  - [DTL](#dtl)
  - [RENDER](#render)
  - [FILTER](#filter)
  - [الوراثة](#الوراثة)
  - [التضمين](#التضمين)
  - [استخدام IF و FOR](#استخدام-if-و-for)
  - [STATIC](#static)
  - [MODELS](#models)
    - [Table](#table)
    - [Columns](#columns)
    - [Rows](#rows)
    - [Relationship Detabase](#relationship-detabase)
      - [علاقة واحد لواحد](#علاقة-واحد-لواحد)
      - [علاقة واحد لمجموعة](#علاقة-واحد-لمجموعة)
      - [علاقة مجموعة لمجموعة](#علاقة-مجموعة-لمجموعة)
    - [class Meta](#class-meta)
    - [__str__](#str)
  - [Admin](#admin)
  - [HTML IMG](#html-img)
  - [FORM](#form)
    - [إنشاء قاعدة بيانات للنموذج](#إنشاء-قاعدة-بيانات-للنموذج)
    - [يوجد 3 طرق لإنشاء FORM](#يوجد-3-طرق-لإنشاء-form)
      - [1. إنشاء النموذج بملف `html` في templates](#1-إنشاء-النموذج-بملف-html-في-templates)
        - [استلام البيانات من request في views مباشرة وإرسالها للوحة الإدارة عن طريق القاعدة](#استلام-البيانات-من-request-في-views-مباشرة-وإرسالها-للوحة-الإدارة-عن-طريق-القاعدة)
      - [2. إنشاء النموذج بملف خارجي واستيراد وحدته لإنشائه](#2-إنشاء-النموذج-بملف-خارجي-واستيراد-وحدته-لإنشائه)
        - [استلام البيانـات من request في views عن طريق forms.py وإرسالها للوحة الإدارة عن طريق القاعدة](#استلام-البيانـات-من-request-في-views-عن-طريق-formspy-وإرسالها-للوحة-الإدارة-عن-طريق-القاعدة)
      - [3. إنشاء النموذج بملف خارجي واستيراد جدوله من قاعدة البيانات](#3-إنشاء-النموذج-بملف-خارجي-واستيراد-جدوله-من-قاعدة-البيانات)
        - [استلام البيانات من request عن طريق forms.py التي تلرسلها للوحة الإدارة](#استلام-البيانات-من-request-عن-طريق-formspy-التي-تلرسلها-للوحة-الإدارة)
    - [الفرق بين الطرق الثلاثة](#الفرق-بين-الطرق-الثلاثة)
  - [Views Strategies](#views-strategies)
    - [FBV (Function-Based Views) - واجهات قائمة على الدوال](#fbv-function-based-views---واجهات-قائمة-على-الدوال)
    - [CBV (Class-Based Views) - واجهات قائمة على الفئات](#cbv-class-based-views---واجهات-قائمة-على-الفئات)
    - [GCBV (Generic Class-Based Views) - واجهات عامة قائمة على الفئات](#gcbv-generic-class-based-views---واجهات-عامة-قائمة-على-الفئات)
    - [reverse vs reverse\_lazy vs redirect](#reverse-vs-reverse_lazy-vs-redirect)
      - [reverse](#reverse)
      - [reverse\_lazy](#reverse_lazy)
      - [redirect](#redirect)
    - [تنظيم الروابط](#تنظيم-الروابط)
    - [كيفية استخدام أسماء الروابط في القوالب](#كيفية-استخدام-أسماء-الروابط-في-القوالب)
    - [استخدام الروابط الديناميكية مع GCBV](#استخدام-الروابط-الديناميكية-مع-gcbv)
    - [مقارنة بين الأنواع الثلاثة](#مقارنة-بين-الأنواع-الثلاثة)
    - [مثال عملي يوضح الفروقات](#مثال-عملي-يوضح-الفروقات)
    - [ملخص تفصيلي سريع عن كيفية وصول البيانات إلى وحدة الإدارة](#ملخص-تفصيلي-سريع-عن-كيفية-وصول-البيانات-إلى-وحدة-الإدارة)
      - [1. *إدخال البيانات بواسطة المستخدم (User Input)*](#1-إدخال-البيانات-بواسطة-المستخدم-user-input)
      - [2. *إرسال البيانات إلى الخادم (HTTP Request)*](#2-إرسال-البيانات-إلى-الخادم-http-request)
      - [3. *التحقق من صحة البيانات (Validation)*](#3-التحقق-من-صحة-البيانات-validation)
      - [4. *معالجة البيانات (Processing)*](#4-معالجة-البيانات-processing)
      - [5. *التفاعل مع قاعدة البيانات (Database Interaction)*](#5-التفاعل-مع-قاعدة-البيانات-database-interaction)
      - [6. *الرد للمستخدم (HTTP Response)*](#6-الرد-للمستخدم-http-response)
      - [7. *عرض البيانات في واجهة الإدارة (Admin Interface)*](#7-عرض-البيانات-في-واجهة-الإدارة-admin-interface)
      - [مخطط توضيحي](#مخطط-توضيحي)
      - [أهم الدوال والطرق المستخدمة](#أهم-الدوال-والطرق-المستخدمة)
      - [مثال كامل (من النموذج إلى الإدارة)](#مثال-كامل-من-النموذج-إلى-الإدارة)
  - [التحكم بشكل لوحة الإدارة](#التحكم-بشكل-لوحة-الإدارة)
  - [إضافة مظهر suit للوحة الإدارة](#إضافة-مظهر-suit-للوحة-الإدارة)
  - [إضافة مظهر grappelli للوحة الإدارة](#إضافة-مظهر-grappelli-للوحة-الإدارة)
  - [تخصيص طريقة عرض النماذج](#تخصيص-طريقة-عرض-النماذج)
  - [تصدير النماذج لملف CSV من لوحة الإدارة](#تصدير-النماذج-لملف-csv-من-لوحة-الإدارة)
  - [إنشاء مشروع تجريبي](#إنشاء-مشروع-تجريبي)
    - [*الفرق بين UserCreationForm و User*](#الفرق-بين-usercreationform-و-user)
    - [PAGINATION](#pagination)
    - [كيفية إنشاء الكائن من خلال سطر الأوامر](#كيفية-إنشاء-الكائن-من-خلال-سطر-الأوامر)
    - [كيفية إنشاء عدد من الكائنات من خلال سطر الأوامر](#كيفية-إنشاء-عدد-من-الكائنات-من-خلال-سطر-الأوامر)
    - [WIDGET TWEAKS](#widget-tweaks)
  - [API](#api)
  - [تطبيق API على المشروع](#تطبيق-api-على-المشروع)
  - [عرض حالة الطقس من خلال API](#عرض-حالة-الطقس-من-خلال-api)
  - [نهاية الملف](#نهاية-الملف)

## التعريف

- اطار عمل مفتوح المصدر لانشاء تطبيقات الويب بطريقة سريعة
- صنع مواقع عملاقة كأنستجرام ويوتيوب ويوديمي
- يقوم بعمل طرق حماية تلقائية
- يجب ان يكون بايثون بأحدث اصدار ليكون به `pip` ينزل الحزم
- يجب عمل بيئة افتراضية لفصل التطبيق عن الجهاز كي لا يحدث تداخل بين المكتبات

---

## تحميل البيئة الافتراضية

- لتحميل البيئة الافتراضية على النظام نكتب في `cli`:
  - `pip install virtualenv`

- لعمل بيئة افتراضية للمشروع، نذهب للمسار الذي سنضعه فيه ونكتب:
  - `virtualenv test`
  أو:
  - `python -m venv`
    - `test`: اسم اختياري للبيئة

- لتفعيل البيئة يجب أن نكون في المسار الذي به البيئة ونكتب:
  - `test\Scripts\activate`

- أحيانا سياسة تنفيذ السكربتات قد تمنع تشغيلها فلتغييرها مؤقتا:
  - `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass`

- ثم تفعيل البيئة الافتراضية كالتالي:
  - `.\test\Scripts\Activate`

- لإلغاء تفعيل البيئة الافتراضية (فقط وقت الحاجة):
  - `test\Scripts\deactivate.bat`

- ثم تحميل دجانجو:
  - `pip install django`

- لانشاء مشروع البيئة الإفتراضية يجب أن نكون داخل `test` ونكتب:
  - `django-admin startproject project`
    - `project`: اسم اختياري للمشروع

- لتفعيل السيرفر ندخل إلى `project` لنكون عند `manage.py` ونكتب:
  - `python manage.py runserver`

- لتفعيله على منفذ (`port`) معين مثلا `5000`:
  - `python manage.py runserver 5000`

- `project` يكون داخل فولدر اسمه `venv` داخل `test`
  - `project` بداخلها ثلاثة مجلدات:
    - `project`: للمشروع
    - `manage.py`: لتشغيل السيرفر
    - `db.sqlite3`: قاعدة بيانات يتم إنشاءها بعد تشغيل السيرفر
      - إن تم مسحها وإعادة إنشاءها فيجب تطبيق 18 ترحيل لكن بعد الضعط على `Ctrl + c` لإيقاف السيرفر ثم كتابة:
        - `python manage.py migrate`

- يتم إنشاء المشروع داخل فولدر آخر باسمه (الذي داخل `venv`) فلإنشائه بجانب البيئة مباشرة نحذفه وننشئه بنفس المسار الموجود به بإضافة `.` ومن ثم تفعيل السيرفر:
  - `django-admin startproject project .`

- للانتقال إلى VSC:
  - `code .`

- يمكن تنزيل `Django` من `EXTENSIONS`

---

## تعريف الملفات

---

### ملفات المشروع

- داخل الـ `project` عدة ملفات:

- `__init__.py`: يظهر أثناء تحميل أي مكتبة جاهزة للاستيراد

- `settings.py`: إعدادات المشروع ويحتوي كوده على:
  - `SECRET_KEY`: المفتاح السري (يمنع مشاركته)
  - `INSTALLED_APPS`: التطبيقات المضافة للمشروع
  - `MIDDLEWARE`: خاصة بالأمان
  - `TEMPLATES`: لقوالب الفرونت إند
  - `DATABASES`: لقواعد البيانات (افتراضيا `SQL`)
    - يمكن تحميل قاعدة بيانات `PostgreSQL` للمشاريع الكبيرة من [هنا](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads)
    - ثم الضغط على ملف التحميل لإتمام عملية التثبيت والضغط على `Finish` بالنهاية
    - للتأكد من نجاح التنزبل يتم البحث والدخول على `SQL Shell` واتباع التعليمات وبعدها معرفة الإصدار من خلال كتابة: `select version();`
    - لإضافة واجهة يتم البحث والدخول على `pgAdmin` وإضافة السيرفر (كتابة اسمه في `General` وكتابة اسمه أو المعرف من البروتوكول في `Connection Host` ثم إضافة باقي البيانات) ثم إنشاء قاعدة البيانات
    - الدخول على `DATABASES` في `settings.py` ثم `ENGINE` ومسح `sqlite3` وإضافة `postgresql` ثم مسح قيمة `NAME` وكتابة اسم القاعدة وإضافة باقي العناصر وقيمتها (`USER`, `PASSWORD`, `HOST`, `PORT`)
    - حفظ التغييرات من خلال سطر الأوامر:
      - `py manage.py makemigrations`
      - `py manage.py migrate`
    - قد يطلب تنزيل حزمة `psycopg2` أولا
  - `AUTH_PASSWORD_VALIDATORS`: المتحقق في نوعية كلمات المرور المحددة

- `urls.py`: للتحكم في الروابط ووضع مساراتها

- `asgi.py`, `wsgi.py`: ملفات خاصة بالسيرفر نادرة الاستخدام

---

### ملفات التطبيق

لعمل تطبيق يجب عمل مجلد للمشروع بداخله عدة تطبيقات خاصة بجزئية معينة تسمى `APP` كل `APP` به عدة ملفات أهمها أربعة:

- `TEMPLATES`: هو الـ `FRONT END` --> التصميم الخاص بالـ `APP` ونحن من ننشئه

- `MODELS`: هو الـ `DATABASE` --> خاص بقاعدة البيانات

- `URLS`: خاص بروابط الـ `APP` نحن من ننشئه وغير الخاص بالمشروع
  - `project\urls.py` ≠ `project\pages\urls.py`
  - `pages`: اسم اختياري للتطبيق

- `VIEWS`: هو الـ `LEADER` --> المشرف عليهم

---

## إضافة التطبيق

- لإضافة `APP` يجب أن تكون البيئة الافتراضية مفعلة ثم نستخدم ملف `manage.py` فنكتب في الـ `cli`:
  - `python manage.py startapp pages`
    - `pages`: اسم اختياري للتطبيق بداخله يوجد عدة ملفات كما قلنا مثل:
      - `migrations`: مجلد مسؤل عن حفظ وتخزين تعديلات قواعد البيانات التي تتم في `models.py`
      - `__init__`: تظهر بعد الإنشاء
      - `admin.py`: خاصة بلوحة الإدارة
      - `apps.py`: إعدادات تكوين التطبيق
      - `models.py`: لقاعدة البيانات
      - `tests.py`: تجرية الدوال لاكتشاف الأخطاء
      - `views.py`: المشرف على باقي الملفات
      - `urls.py`: نحن من نضيفه لوضع روابط دوال العرض الخاصة بـ `views.py`

- بعد إنشاء الـ `app (pages)` يجب:
  - ضمه إلى `INSTALLED_APPS` داخل `settings` بكتابة:
  - `pages.apps.PagesConfig`
    - `pages`: اسم التطبيق
    - `PagesConfig`: اسم الفئة العائد منه الموجودة داخل `apps` داخل `pages`

- إنشاء رابطه في `urls.py` داخل `project` باستيراد أداة `include` من مكتبة `django.urls` (تكون مكتوبة في الكود ومستردة `path` فنضيف معها `include`)

- ثم إضافة الرابط في `urlpatterns` بكتابة:

  ```sh
  path("pages/", include("pages.urls"))
  ```

  - `pages`: هو اسم المسار بعد `/`
يمكن ابقاؤه فارغ باعتبارها الصفحة الرئيسية
  - `include`: الأداة المستوردة من `django.urls` التي تضم مسارات ملف التطبيق بدلا من وضع المسارات مباشرة
  - `pages.urls`: يرمز للملف الذي ننشؤه داخل `pages` وهو `urls.py`
    - نضع فيه روابط أي صفحة ننشئها من `views` داخل `pages`

- بدون إضافة رابط الصفحة فلا يمكن الوصول إليها من خلال دالة العرض

---

## إضافة الواجهة

- لاظهار الواجهة بمجرد ضغط المستخدم على الرابط:
  - في `pages\views`:

    ```sh
    from django.http import HttpResponse
    ```

  - ثم عمل دالة تطبع ما يظهر:

```sh
def home(request):
    return HttpResponse("hello")
```

- للانتقال لصفحة أخرى:

```python
from django.shortcuts import redirect

def about(request):
    return redirect('Home')
```

- `Home`: اسم دالة العرض المنتقل إليها

---

## إضافة الصفحة

- أي صفحة خاصة بالتطبيق تُضاف بعد اسم النطاق الأساسي باستخدام `/` مثال:
  - إذا كان النطاق هو `example.com`، والصفحة هي `about` يصبح الرابط:

```sh
example.com/about
```

- ثم كتابة رابط الدالة داخل `urls.py`:
  - في `pages\urls`:

    - أولا نستورد المسار (يكون من خلال نفس المكتبة في `project`):

    ```sh
    from django.urls import path 
    ```

    - ثانيا نستورد دوال العرض:

      ```sh
      from . import views
      ```

      - ( . ) يشير إلى الموقع الموجودين فيه

    - ثالثاً: تعريف أنماط الروابط باستخدام `urlpatterns` وهو نفسه الموجود في `project`:

    ```sh
    urlpatterns = [
    path("about", views.about, name="about"),
    ]
    ```

    - يمكن أيضا استيراد الدوال مباشرة من `import` فتتمكن من تعريفها دون الحاجة إلى `views` فتصبح بهذا الشكل:
  
    ```sh
    from .views import about
    urlpatterns = [
    path("about", about, name="about"),
    ]
    ```

    - وكلما تطلب إضافة رابط أي دالة تكتبها بعدها هكذا:

    ```sh
    from .views import about, home
    ```

    - `path()` تأخذ 3 عناصر رئيسية:
      1. المسار النسبي (له استخدامان):
          1. البروتوكول: إذا كان الموقع يعمل على `https`، فسيصبح الرابط الكامل: `https://example.com/about/`
          2. في ملفات `HTML`: يُستخدم مع وسم `<a>` من خلال الرابط المطلق بالشكل: `<a href="about/">عن التطبيق</a>`
      2. مكان الدالة: `def about(request)`
      3. اسمه في `url`: `<a href="{% url 'about' %}">عن التطبيق</a>`
          - يختلف عن المسار العادي المأخوذ من العنصر الأول في المرونة عند تغيير المسار مثلا لو تغير إلى `path("about_us", views.about, name="about")`، فسنذهب لكل مكان به المسار المطلق لتغييره إلى المسار الجديد أما مسار `url` فقيمته ثابتة مأخوذة من `name` لسنا بحاجة لتغييره إن تغيرت قيمة العنصر الأول

### ملاحظات

- لو كانت الصفحة هي الصفحة الرئيسية لا نعطي قيمة للمسار النسبي فتكون هكذا: `path("", views.home, name="home")`

- في `project\urls.py`: نحدد البادئة المشتركة (مثل `Facebook/`).

- في `pages\urls.py`: نحدد المسارات الفرعية (مثل `group1`).

- الرابط النهائي: `Facebook/group1`.

- يجب ان يكون المسار `/` داخل `path` إما بعد `Facebook` أو قبل `group` المهم يكتب بين أي صفحتين
- يجب إبقاء خادم التطوير مفتوحا فإن تم إيقافه يجب إعادة نشغيله بعد إجراء التعديلات (كإضافة ملفات جديدة أو نعديل الإعدادات) من خلال `runserver`

- خلاصة الأمر كلما أردنا عمل صفحة نكتبها كدالة في `pages\views` ونضع رابطها في `pages\urls`

---

## التعامل مع TEMPLATES

في `VIEWS`:

بدلا من استخدام مكتبة `http` للتعامل مع الروابط سنستخدم مكتبة `django.shortcuts` مع أداة `render`

- `VIEWS`: يتم ربطها مع `TEMPLATES` و `MODELS` لعرضهم للمستخدم
- `TEMPLATES`: بداخلها لغة تتعمامل معها تسمى لغة قوالب دجانجو (`Django templates language` (`dtl`))

---

### إضافة القالب

لعمل مجلد لـ `templates` إما عمله داخل كل `app` أو للـ `project` كله يعني في الخارج ونضع فيه مجلدات كل `app`

- أولا:
  - إنشاء مجلد باسم `templates`

- ثانيا:
  - وضعه داخل `TEMPLATES` في `settings` داخل أقواس `DIRS` أو وضعه بالمسار الخاص به (الأفضل)
  - كيف نضعه في مساره؟
    - نستورد `os`
    - في مفتاح `DIRS` نكتب:

      ```sh
      os.path.join(BASE_DIR, 'templates')
      ```

- ثالثا
  - ربط `TEMPLATES` مع `VIEWS`:
    - ننشئ ملف `html` داخل التطبيق الذي يتم إنشاؤه داخل `templates` مثل `pages`
    - داخل الدالة الموجودة في `views` نكتب:

    ```sh
    return render(request, "pages\file.html")
    ```

    - `request`: هو وسيط الدالة
    - يتم افتراض أن `pages` داخل `templates`
    - أما `file.html` نقوم بالعمل عليها وكذا

---

## DTL

محرك القوالب الإفتراضي المدمج مع دجانجو

مثل محرك `jinja` المستقل لكن الأمان فيه أكبر مقارنة بالسرعة

يتم كتابتها داخل ملفات `templates` مثل `home.html`

## RENDER

- `render` في `views` تأخذ ثلاث عوامل:
  - `request`: لتقديم طلب المستخدم
  - `templates`: لتشغيل الملف
  - `context`: لاستخدام `dtl`
    - فمثلا العامل الثالث يكون:
`{"key": "value"}`

- وفي `html` نضع `key` بين `{{}}` بدون `' '` ويعطي `value`

- `{{}}`: هذه الأقواس تابعة لمحرك قوالب خاص ببايثون اسمه `jinja` يحول القالب لمحتوى ديناميكي باستبدال العناصر النائبة بالبيانات الفعلية

- يمكن إدراج أكثر من مفتاح في `render` بعد (`,`)

- يمكن وضع القاموس في متغير ووضع المتغير كعامل ثالث لـ `render` ونضع في `html` المفتاح أيضا وليس المتغير فما يتم تمريره هو المفتاح فقط

- وهذا يعني أن العامل الثالث في `render` يجب نوع بياناته أن تكون قاموسا أما القيمة التي يقدمها المفتاح يمكن أن تكون أي نوع بيانات

---

## FILTER

- هو ما يتم إضافته للمفتاح في `html` للتعديل على قيمته، نكتبه بعد (`|`) مثلا:

  - `capfirst`: أول حرف كبير

  ```sh
  {{x | capfirst}}
  ```

  - `default`: للقيمة الفارغة

  ```sh
  {{x | default : "Not found"}}
  ```

  - `slice`: تقطيع

  ```sh
  {{x | slice: "2 : 4"}}
  ```

  - `length`: عدد الحروف

  ```sh
  {{x | length}}
  ```

  - `add`: إضافة نص

  ```sh
  {{x | add : " ok"}}
  ```

  - `cut`: إزالة حرف
    - مثلا لإزالة المسافات:

  ```sh
  {{x | cut: " "}}
  ```

  - `filesizeformat`: تحويل الفيم الرقمية لوحدات البايت:
    - لو كانت قيمة نصية ستكون `0 bytes`

  ```sh
  {{x | filesizeformat}}
  ```

  - `safe`: عرض الأوسمة بشكل آمن

  ```sh
  {{x | safe}}
  ```

    >توضيح: نظام القوالب يهرب الأحرف الخاصة تلقائيا لمنع هجمات `XSS` لذا عند استخدام `safe` تخبر القالب أن المحتوى آمن ولا يحتاج إلى تهريب، فيتم عرضه كـ `HTML` صالح بدلًا من نص خام
    هذا يكون بحالة أن المحتوى نفسه به أوسمة `html` مثلا بهذا الشكل في دالة العرض:

    ```python
    def contact(request):
    return render(request, "contact.html", 'logs_names': '<br>'.join([log.name for log in Login.objects.all()]))
    ```

    أو مع المتغيرات لتصبح أوضح:

    ```python
    def contact(request):
      logs = Login.objects.all()
      logs_names = '<br>'.join([log.name for log in logs])
    return render(request, "contact.html", 'x': logs_names)
    ```

  - `logs`: متغير لجلب كل صفوف الجدول
  - `logs_names`: متغير لعرض حقل الاسم من كل صف من خلال اللوب ويتم فصلهم بسطر جديد من خلال وسم `br`
  - `x`: مفتاح البيانات الذي سيتم عرضه في `html` مع فلتر `safe`

---

## الوراثة

- لإنشاء ملف موروث يتم وراثة معلوماته من باقي الملفات:
  - ننشئ الملف داخل `templates` خارج `pages` مثلا `base.html`
  - ننشئ هيكل `HTML`

- لعمل `Tags` في ملف `html` نستخدم `{%%}`

- نستخدم كلمة `block` لإضافة المحتوى ونضع له أي اسم يعبر عنه مثلا:

- `base.html`

```html
<head>
    <title>
        {% block title %}
        {% endblock %}
    </title>
    {% block extra_css %}
    {% endblock %}
</head>
<body>
    {% block content %}
    {% endblock %}
</body>
```

- `block title`: للعنوان
- `block extra_css`: لأكواد أو ملفات التنسيق
- `block content`: لعناصر الجسم

وفي ملفات `HTML` الوارثة مثل `home.html` نرث الملف باستخدام `extends` ثم كتابة كل شيء بمكانه داخل البلوك مثلا:

- `home.html`

```html
{% extends "base.html" %}

{% block title %}
    Home bage
{% endblock %}

{% block extra_css %}
    <style>
        body { color: red; }
    </style>
{% endblock %}

{% block content %}
    <p>Hello world!</p>
{% endblock %}
```

يفضل كتابة اسم البلوك بالـ `endblock` أيضا لزيادة الوضوح وعدم التداخل مع باقي البلوكات سواء بالملف الموروث أو الوارث (شرط أن يكون نفس اسم البلوك) مثلا:

```html
{% block title %}
{% endblock title %}
```

---

## التضمين

- داخل الملف الموروث يمكن كتابة محتويات ثابتة مثل `navpar` أو `footer` في الـ `body` مباشرة أو يمكن كتابة تلك المحتويات بملف آخر يتم تضمينه لللملف الموروث
- هذا الملف يجب أن يكون داخل `tamplates` سواء في `pages` أو بمجلد داخله (يستحب) مثلا ننشئ فولدر باسم `includes` وبداخله ملفات مثل `_navpar.html`, `_footer.html`
  - `_`: للتوضيح أنه ملف فرعي ثابت (اختياري)
- بداخل هذه الملفات نكتب كودها الثابت
- لإضافتها للـ `base.html` نضعها بالمكان المراد من خلال `include` مثلا:

- `base.html`

```html
<body>
    {% block content %}
        {% include "includes/_navpar.html" %}
        {% include "includes/_footer.html" %}
    {% endblock %}
</body>
```

---

## استخدام IF و FOR

يمكن استخدام `for` و `if` مع المفاتيح بالملفات الوارثة:

- `home.html`

```html
{% block content %}
{% for i in x %}
<p>{{ i }}</p>
{% endfor %}

{% if x == "Ali" %}
    <p>HELLO ALI!</p>
{% elif x == "Sarah" %}
    <p>HELLO SARAH!</p>
{% else %}
    <p>WELCOME!</p>
{% endif %}
{% endblock content %}
```

---

## STATIC

- طريقة يستخدمها جانغو لربط الملفات الخارجية بالـ `base.html` أو الملفات الوارثة مثل ملفات الصور أو `css` .إلخ

- يجب أولا أن ننشئ فولدر `static` في `project\project` بنفس المسار الخاص بـ `settings.py`

- داخله ننشئ فولدر يحمل ملفاته مثل فولدر `css` أو `img` .إلخ (للتنظيم)

- وداخل `css` ننشئ ملفات خاصة بتنسيقات كل ملف في `templates` مثل `home.css`, `about.css` .etc

- لتنشيط الـ `static` نذهب لملف `settings.py`:
  - ويكون مكتوب:  `STATIC_URL = '/static/'`
  - فوق `STATIC_URL` نكتب:
    - `STATIC_ROOT = os.path.join(BASE_DIR, 'static')`
      - هذا لنقل مسار الملفات للخارج
  - ولتحديد مكانه للخارج نكتب أسفل `STATIC_URL`:
    - `STATICFILES_DIRS = [ os.path.join(BASE_DIR, 'project/static'), ]`

- لتنفيذ الأمر نكتب في التيرمينال:
  - `python manage.py collectstatic`

- بمجرد خروجه يتم إضافة بداخله فولدر `admin` لإضافة بعض الميزات

- لربط ملفات `css` بالـ `base.html`, قبل الهيكل نكتب:

```html
{% load static %}
```

- لتحميل الـ `static`, ويجب كتابته بأول سطر

- لكتابة الرابط يجب كتابة `static` معها داخل `{%%}` بكتابة:

```html
<link rel="stylesheet" href = "{% static 'css/base.css' %}">
```

- ⚠️⚠️ في الملفات الوارثة يتم كتابة `load static` بعد `extends` وليس قبلها

- وفي البلوك يتم كتابة الرابط بنفس الطريقة بوضع ملفات `static` الخاصة بكل ملف وارث مثلا بملف `home.html` يكون الشكل هكذا:

```html
{% extends "base.html" %}
{% load static %}

{% block title %}
    Home bage
{% endblock %}

{% block extra_css %}
    <link rel="stylesheet" href = "{% static 'css/home.css' %}">
{% endblock %}

{% block content %}
    <p>{{ x }}</p>
{% endblock %}
```

- لإضافة ملفات أخرى في `static` كملفات الصور بفولدر الصور الذي ننشؤه يتم إضافتها في فولدر static الرئيسية القديمة التي بداخل المشروع ومن ثم إعادة تنفيذ بالتيرمينال  `python manage.py collectstatic` لحفظ التغيرات

- لوضع رابط الصورة في `html`:

```html
<img src = "{% static 'image\photo.png' %}" alt="photo">
```

- لكتابة تعليق متعدد الأسطر في `DTL` نضعه بين:

```html
{% comment %}
<p>هذا تعليق</p>
{% endcomment %}
```

- لكتابة تعليق بسطر واحد

```html
{# هذا تعليق #}
```

---

## MODELS

- نموذج داخل التطبيق به قواعد بيانات العنصر

- يتم تحديد نوع البيانات من خلال `SQL` لكن بما أننا نعمل في بايثون فجانغو قدمتها لنا جاهزة!

- أي تطبيق مثل (`pages`) يكون به ملف `models.py` لكن من أجل التنظيم نحتاج لعمل تطبيق آخر ليكون به قاعدة بيانات خاصة بالمنتجات:
  - إنشاء التطبيق: `python manage.py startapp products`
  - إنشاء بداخله ملف `urls.py`
  - الانتقال إلى `project\settings.py`:
ووضعه في `INSTALLED_APPS`
  - الانتقال إلى `project\urls` (تحت الـ `settings`) وونشئ المسار
  - من المهم أيضا كتابة البيانات داخل `urls` و `views` في `products` من أجل أن يعمل الموقع

### Table

داخل نموذج التطبيق:

إنشاء العنصر الذي ستكون له قاعدة بيانات يتم من خلال إنشاء جدول له من خلال البرمجة الكائنية (`OOP`) مثلا لإنشاء سيارة ننشئ جدولا لها:

```python
class Car(models.Model):
```

- `models`: الأداة المستوردة من مكتبة `django.db` لتحديد نوع البيانات من خلال خصائصها

### Columns

إنشاء الخصائص يتم من خلال إنشاء متغير لكل خاصية (كالاسم والسعر) تمثل أعمدة للجول مثل:

```python
SEDAN = 'SEDAN'
SUV = 'SUV'
HATCHBACK = 'HATCHBACK'
table = [
(SEDAN, 'Sedan'),
(SUV, 'Suv'),
(HATCHBACK, 'Hatchback'),
]
category = models.CharField(max_length=50, choices=table)
name = models.CharField(max_length=100, default="car", verbose_name='kind', unique=True)
price = models.DecimalField(max_digits=10, decimal_places=2, null=True,)
description = models.TextField(blank=True)
birth_date = models.DateField(null=True, blank=True)
```

- خصائص `models`:

  - `CharField`: للقيمة النصية
    - `max_length`: أقصى عدد حروف يمكن وضعها
    - `choices`: تحديد تصنيف للكائن وله قيمتين (يمكن أن تكونان نفس القيمة):
      - الأولى لقاعدة البيانات (يمكن كتابتها مباشرة أو وضعها بمتغير أولا لتجنب تغيير القيمة لاحقا وتعديلها في كل مكان موجودة فيه)
      - الثانية للوحة الإدارة (خاصة بصفحة المشرف)
    - `default`: إنشاء قيمة افتراضية داخل الحقل ويمكن تغييرها أو حفظها كما هي، مفيدة في تجنب فشل الحفظ إن لم يدخل أي قيمة للحقل فتكون هذه القيمة البديلة (يمكن اضافتها إلى أي خاصية)
    - `verbose_name`: تغيير اسم الحقل في لوحة الإدالرة
    - `unique`: قيمة الحقل بكل الكائنات فريدة لا يمكن تكرارها

  - `DecimalField`: للقيمة الرقمية العشرية
    - `max_digits`: أقصى عدد أرقام صحيحة
    - `decimal_places`: أقصى عدد أرقام عشرية
    - `null`: يحدد ما إذا كان الحقل يمكن أن يكون `NULL` في قاعدة البيانات (قيمة فارغة في `SQL`) لكنه مطلوب في النموذج، تستخدم للحقول التي تخزن بيانات رقمية (`IntegerField،` `DecimalField،` إلخ).
    - استخدم `default` مع `blank=True` لتجنب مشاكل القيم الفارغة: `default=0`

  - `IntegerField`: للقيمة الرقمية الصحيحة

  - `TextField()`: لقيمة نصية لانهائية
    - `blank`: يحدد ما إذا كان الحقل يمكن أن يكون فارغًا في النموذج (`Form`) أو لوحة الإدارة (مثل حقل نصي غير مطلوب) لكنه مطلوب في قاعدة البيانات، تستخدم للحقول النصية (`CharField،` `TextField`).
    - بدلا من استخدام `null` ننشئ قيمة فارغة `default=''`

  - `EmailField`: للإيميل

  - `DateField`: للتاريخ
    - يمكن تركه فارغًا في النموذج (بسبب `blank`) وفي قاعدة البيانات (بسبب `null`)

  - `TimeField`: للوقت

  - `DateTimeField`: للتاريخ والوقت

  - لإضافة وقت إنشاء الكائن تلقائيا من مكتبة خارجية:

    ```python
    from datetime import datetime

    class Car(models.Model):
      date_and_time = models.DateTimeField(default=datetime.now)
    ```

  - لإضافة وقت إنشاء الكائن تلقائيا بدون مكتبة خارجية:

    ```python
    date_and_time = models.DateTimeField(auto_now_add=True)
    ```

    - `auto_now_add`: تاريخ الإنشاء
    - `auto_now`: آخر تاريخ (في حالة حصول تعديل)

  - `ImageField()`: للصور ،تأخذ أكثر من قيمة، أهمها:
    - `upload_to='images/%y/%m/%d',`: توضع في مجلدات حسب تاريخ الإنشاء
    - `default="images/25/5/30/photo.jpg",`: إظهار صورة معينة كصورة افتراضية (تظهر بعد الحفظ)

  - `BooleanField(default=True),`:
    - `True`: رؤية الحقل
    - `False`: إلغاء الرؤية بحال حدوث مشاكل

  - `PositiveIntegerField`: للقيمة الرقمية الطبيعية:
    - `0`: ✔️
    - `-5`: ❌
    - `1/3`: ❌

- `ID`: حقل افتراضي يضاف لأي جدول ليحدد ترتيب اضافة الكائن

### Rows

- عملية إنشاء الكائن (العنصر أو المنتج) تتم من خلال لوحة الإدارة بصفحة المشرف

### Relationship Detabase

- يوجد ثلاث أنواع مختلفة من العلاقات:
  - واحد لواحد
  - واحد لمجموعة
  - مجموعة لمجموعة

- العلاقات لا تكون إلا مع الجداول السابقة لذا يتم وضعها في الجداول اللاحقة لتحدث العلاقة مع جدول موجود مسبقا

- لو حدثت علاقة مع جدول لاحق يجب وضعه بين علامات تنصيص

---

#### علاقة واحد لواحد

```python
class Male(models.Model):
  name = models.CharField(max_length=50,)
  relationship = models.OneToOneField('Female', on_delate=models.CASCADE)

class Female(models.Model):
  name = models.CharField(max_length=50,)
```

- `OneToOneField`: نوع العلاقة
- `Female`: اسم الجدول المتصل (نزيل العلامة `''` لو كان سابق)
- `CASCADE`: لو تم حذف الكائن يحذف الكائن المتصل به مباشرة
- `PROTECT`: الكائن المرتبط محمي فلو تم حذف الكائن الرابط يجب استبدال الكائن المربوط بكائن آخر أو كائن فارغ مضاف بهذا الشكل `(-------)`

#### علاقة واحد لمجموعة

```python
class Woman(models.Model):
  name = models.CharField(max_length=50,)

class Man(models.Model):
  name = models.CharField(max_length=50,)
  relationship = models.ForeignKey(Woman, related_name='marriage', on_delate=models.PROTECT)
```

- `ForeignKey`: نوع العلاقة
  - يمكن ربط عنصر من جدول `Man` بأكثر من عنصر من جدول `Woman`
- `Woman`: اسم الجدول المتصل (بدزن `''` لأنه سابق)
- `related_name`: اسم العلاقة

#### علاقة مجموعة لمجموعة

```python
class Human(models.Model):
  name = models.CharField(max_length=50,)

class Car(models.Model):
  name = models.CharField(max_length=50,)
  relationship = models.ManyToManyField(Human)
```

- `ManyToManyField`: نوع العلاقة
  - يمكن ربط عنصر من جدول `Human` بأكثر من عنصر من جدول `Car` ونفس العنصر من جدول `Car` يمكن ربطه لأكثر من عنصر من جدول `Human`
  - خاصية `on_delate` هنا غير مهمة لأن عنصر `Car` يربطه أكثر من علاقة

---

### class Meta

- لتغيير اسم الجدول بصفحة المشرف مثلا من `CAR` إلى `VEHICLE` ننتقل إلى داخل كتلة كود الكلاس ونكتب:

```python
class Meta:
    verbose_name = "matter"
```

- خصائص أخرى:

  - `ordering`: ترتيب السجلات على حسب الحقل:
    - `ordering ['name']`: ترتيب أبجدي تصاعدي حسب الاسم
    - `ordering ['-price']`: ترتيب تنازلي حسب السعر
    - `ordering = ['-price', 'name']`: تصاعدي حسب السعر ثم تنازلي حسب الاسم
  - `unique_together`: كائنات غير متشابهة بخصائص معينة
    - `unique_together = [['name', 'price']]`
    - تختلف عن `unique` في `models` في أنه لا يمنع أن تكون قيم كل خاصية في الكائنات متشابهة وأنما تكون متشابهة في مجموعة خصائص معا

- بدلا من `unique_together` نستخدم `UniqueConstraint` وهي أحدث منها:

- شرح `UniqueConstraint` في Django

`UniqueConstraint` هو طريقة متقدمة ومُفضلة في Django (منذ الإصدار 2.2) لفرض قيود التفريد (UNIQUE) على مجموعة من الحقول، وهي بديل أكثر مرونة لـ `unique_together`. سأشرحها لك بمفاهيم واضحة وأمثلة عملية.

- الفرق الأساسي بين `unique_together` و `UniqueConstraint`

| الميزة               | `unique_together` | `UniqueConstraint` |
|----------------------|-------------------|--------------------|
| الدعم           | جميع إصدارات Django | Django 2.2+ |
| المرونة         | محدود | يدعم شروط إضافية |
| التركيب        | `unique_together = [['field1', 'field2']]` | `constraints = [UniqueConstraint(...)]` |
| إمكانية التسمية | لا | نعم (مهم للتعرف على القيود) |

- كيف تستخدم `UniqueConstraint`؟

1- الشكل الأساسي

```python
from django.db import models

class Product(models.Model):
    store = models.ForeignKey(Store, on_delete=models.CASCADE)
    barcode = models.CharField(max_length=20)
    category = models.CharField(max_length=50)

    class Meta:
        constraints = [
            models.UniqueConstraint(
                fields=['store', 'barcode'],  # الحقول التي نريدها فريدة معًا
                name='unique_product_per_store'  # اسم واضح للقيد
            )
        ]
```

التفسير:

- هنا نمنع تكرار نفس الباركود في نفس المتجر
- لكن يمكن تكرار الباركود في متاجر مختلفة
- ويمكن تكرار متاجر مختلفة بنفس الباركود

2- استخدام شروط إضافية (Condition)

```python
class Discount(models.Model):
    product = models.ForeignKey(Product, on_delete=models.CASCADE)
    start_date = models.DateField()
    end_date = models.DateField()
    is_active = models.BooleanField(default=True)

    class Meta:
        constraints = [
            models.UniqueConstraint(
                fields=['product'],
                condition=models.Q(is_active=True),
                name='unique_active_discount'
            )
        ]
```

التفسير:

- هنا نسمح بخصم واحد فقط نشط (`is_active=True`) لكل منتج
- لكن يمكن أن يكون للمنتج عدة خصومات غير نشطة

3- استخدام مع الحقول التي يمكن أن تكون NULL

```python
class UserProfile(models.Model):
    user = models.OneToOneField(User, on_delete=models.CASCADE)
    phone = models.CharField(max_length=20, null=True)
    alt_phone = models.CharField(max_length=20, null=True)

    class Meta:
        constraints = [
            models.UniqueConstraint(
                fields=['phone', 'alt_phone'],
                name='unique_phones',
                nulls_distinct=True  # منذ Django 4.1
            )
        ]
```

- لماذا نستخدم `UniqueConstraint` بدلاً من `unique_together`؟

1. إمكانية التسمية: يمكنك إعطاء اسم وصفي للقيد
2. شروط إضافية: يمكنك إضافة شروط باستخدام `Q objects`
3. دعم أفضل: الطريقة الموصى بها في Django الحديثة
4. وضوح الكود: أكثر قابلية للقراءة والصيانة

- مثال عملي: نظام الجامعة

```python
class CourseRegistration(models.Model):
    student = models.ForeignKey(Student, on_delete=models.CASCADE)
    course = models.ForeignKey(Course, on_delete=models.CASCADE)
    semester = models.ForeignKey(Semester, on_delete=models.CASCADE)
    is_approved = models.BooleanField(default=False)

    class Meta:
        constraints = [
            # لا يمكن للطالب التسجيل في نفس المقرر في نفس الفصل أكثر من مرة
            models.UniqueConstraint(
                fields=['student', 'course', 'semester'],
                name='unique_student_course_semester'
            ),
            
            # لا يمكن الموافقة على أكثر من تسجيل واحد لنفس الطالب في المقرر
            models.UniqueConstraint(
                fields=['student', 'course'],
                condition=models.Q(is_approved=True),
                name='unique_approved_registration'
            )
        ]
```

- الأخطاء الشائعة

1. *نسيان إضافة الحقول إلى القيد*
2. *عدم إعطاء اسم فريد لكل قيد*
3. *استخدامه مع حقول قد تكون NULL بدون `nulls_distinct`*
4. *الخلط بين `fields` و `condition`*

`UniqueConstraint` يعطيك تحكمًا أدق في كيفية تطبيق قيود التفريد على نماذجك، وهو ما يجعله اختيارًا ممتازًا للتطبيقات المعقدة.

---

### __str__

- لتحديد كيفية عرض الكائن من خلال أحد خصائصه (مثلا اسمه) بدلا من `Car.objects` (قيمة العرض الافتراضية لسجلات الجدول، يأخذها من اسمه) ننتقل خارج كتلة الكود ونكتب:

```python
def __str__(self):
    return self.name
```

- لو كان الحقل الذي سيتم عرضه غير نصي (مثل السعر) فيجب تحويل نوعه لنصي

```python
def __str__(self):
    return str(self.price)
```

---

## Admin

- صفحة قاعدة البيانات التي من خلالها نعرض الكائنات التي ننشئها ( تتم بعد إنشاء قاعدة البيانات نفسها في `models.py`)

- لعرض العناصر بصفحة `html` نتبع هذه الخطوات

1. لانشاء حساب للمشرف نكتب بالتيرمينال:

    ```sh
    python manage.py createsuperuser
    ```

    - سيطلب إنشاء اسم المستخدم والحساب والباسوورد فندخل البيانات

2. تسجيل رابط الصفحة في `urls` المشروع (مسجلة افتراضيا)

3. نكتب في البروتوكول `admin` وندخل البيانات التي كتبناها ومن ثم ندخل على صفحة القاعدة

4. ننتقل إلى `products\admin.py` بالتطبيق لنتمكن من إظهار الجدول

5. استيراد قاعدة البيانات:

    ```python
    from .models import Car
    ```

6. تسجيلها في الصفحة من خلال أداة `admin` المستوردة:

    ```python
    admin.site.register(Car)
    ```

7. ترحيل القاعدة من خلال التيرمينال للتمكن من إضافة كائنات (صفوف) للجدول

    ```sh
    python manage.py makemigrations
    python manage.py migrate
    ```

    - يتم تكرار هذه العملية كلما أضفنا حقل جديد (حقل وليس صف)

8. الدخول لصفحة الجدول وإنشاء كائنات ندخل به بيانات كل حقل

9. إنشاء صفحة `html` لعرض الصفوف (الكائنات) التي أنشأناها

   1. الانتقال إلى `templates`

   2. إنشاء فولدر (مثلا: `cars`)

   3. داخله ننشئ ملف رئيسي ليتعامل مع جميع الكائنات بالجدول (مثل: `cars.html`)، وآخر فرعي لتفاصيل الكائن الواحد (مثل: `car.html`)

   4. كل ملف يقوم بوراثة الملف الأساسي:

      ```html
      {% extends 'base.html' %}
      {% block content %}
      {% endblock content %}
      ```

   5. الانتقال إلى `products\views.py` واستيراد الجدول وإنشاء دالة لكل ملف وإضافة الكائنات إلى قاموس البيانات في الدالة الرئيسية التي تعرض كل الكائنات وإضافة خصائص مميزة في الدالة

      ```python
      from django.shortcuts import render
      from .models import Car

      def cars(request):
        all_cars = Car.objects.all()
        get_mercedes = Car.objects.get(name='Mercedes-Benz G-Class')
        get_by_id = Car.objects.get(id=1)
        specific_price = Car.objects.all().filter(price=100)
        get_all_suv = Car.objects.filter(category ="SUV")
        get_all_sedan = Car.objects.filter(category =Car.SEDAN)

        return render(request, "products\products.html", {'cars_pass': all_cars})


      def car(request):

        return render(request, "products\car.html")
      ```

      - `all_cars`, `get_mercedes`, `get_by_id`, `specific_price`, `get_all_suv`, `get_all_sedan`: متغيرات للتنظيم، يمكن وضع القيمة بالقاموس مكان أي منهم مباشرة

      - لإضافة كل القواميس نحتاج لوضعها بمتغير وتمريره:

      ```python
      context = {
          'all_cars': all_cars,
          'get_mercedes': get_mercedes,
          'get_by_id': get_by_id,
          'specific_price': specific_price,
          'get_all_suv': suv_cars,
          'get_all_sedan': get_all_sedan,
      }

      return render(request, "products/cars.html", context)
      ```

      - `cars_pass`: المفتاح المرسل للقالب

      - `Car.objects`: الاسم الافتراضي المعروض للكائن بصفحة المشرف (حسب اسمه في الكلاس)
        - حتى لو تم تغييره لاسم أحد الخصائص من خلال `__str__` فيجب أن يكون بهذه الصيغة (`class_name.objects`)

      - `all()`: تمرير كل الكائنات
  
      - `get()`: يبحث عن كائن واحد فريد في قيمة الخاصية (مثل الاسم و `id` كما هو بالمثال) ويجب أن يكون موجودا ولا يستخدم معه اللوب
        - يشبه `get()` الخاص بالقاموس في جلب القيم لكن الخاص بـ (ORM) يعطي خطأ إن لم يجد الكائن
        - لو ليس هناك أي كائن بهذه القيمة أو يوجد أكثر من كائن نستخدم معه الاستثناء:

        ```python
        try:
            get_mercedes = Car.objects.get(name='Mercedes-Benz G-Class')
        except Car.DoesNotExist:
            print("لا توجد سيارة")
        except Car.MultipleObjectsReturned:
            print("يوجد أكثر من سيارة بهذا الاسم!")
        ```

      - `filter()`: يبحث عن عنصر أو عناصر متفلترة لخاصية معينة  باستخدام اللوب ويتعامل معها كقائمة ويمكن ألا يجد عنصر بتلك القيمة (يمكن إزالة `all()`)
        - يمكن استخدام `if` بحالة عدم وجود العنصر و `for` بحالة وجود أكثر من عنصر:

        ```python
        cars = Car.objects.filter(price=100)
        if not cars.exists():
            print("لا توجد سيارات بهذا السعر")
        else:
          for car in cars:  
            print(car.name)
        ```

        - يمكن استخدام `first` لجلب أول عنصر فقط إن وُجِد ولن نحتاج للوب كما في `get()` بل أفضل من `get()` لأنه يحل مشكلة الكائنات التي لها نفس القيمة بحقلها أو عدم وجود كائنات بتلك القيمة بحقلها:

        ```python
        cars = Car.objects.filter(price=100).first()
        ```

        - `category`: استخدمنا معه قيمة `choices` الأولى الخاصة بقاعدة البيانات مرة باستخدام القيمة ومرة باستخدام المتغير

   6. إضافة روابط الدالتين في `products\urls.py`:

      ```python
      from django.urls import path
      from .views import cars, car

      urlpatterns = [
          path('', cars, name='cars'),
          path('car/', car, name='car'),
      ]
      ```

      - يمكن التحكم في الرابط من خلال المسار باستقبال قيمة ديناميكية ممررة للدالة بمعنى مثلا إن أردنا إظهار قيمة في الصفحة من خلال البروتوكول نضع مسار ديناميكي في عناوين `url` ويتم تمريره لدالة `views` كمتغير وهذا المسار يتم إنشاؤه داخل `<>` مثلا في `urls` التطبيق:

      ```python
      path('car/<car_id>/', car, name='car')
      ```

      - هنا يمكن تحديد نوع بيانات `id` كرقم فنكتب: `<int:car_id>`

      - أو يمكن كتابة نوع آخر مثل `str` وهكذا

      - وفي `views` نقوم بتمريرها:

      ```python
      def car(request, car_id):
      ```

      - ويمكن وضعه كقيمة في بقاموس البيانات

      - ونضع المفتاح في `Templates` ولأن القيمة ديناميكية فيجب أن نضعها في البروتوكول وإلا لن يتمكن من التعرف على قيمة المفتاح
  
      ```sh
      http://127.0.0.1:8000/car/33/
      ```

      - رقم `33` هو قيمة `car_id` الموضوعة في `urls` ولأنها موضوعة في `dtl` فسيتم إظهارها في الواجهة

      - هذه الطريقة يمكن الاستفادة منها بجلب أي سيارة من خلال حقل `id` الافتراضي بجداول `models.py`:

      ```python
      car = Car.objects.get(id=car_id)
      ```

      - وتوضع بقاموس البيانات ليتم إضافة مفتاحها إلى `html`: `{"car": car}`

      - يتم عرض السيارة من خلال وضع `id` الخاص بها في البروتوكول لكن قد يتم `id` لعنصر غير موجود لذا يجب إضافة استثناء (يمكن تحديد أكثر من طريقة سيتم عرضها كتعليق):

      ```python
      from django.http import Http404, HttpResponse:
      from django.shortcuts import render, get_object_or_404
      from .models import Car

      def board_detail(request, board_id):
          try:
              car = Car.objects.get(id=car_id)
          except Car.DoesNotExist:
              # return HttpResponse("Car not found", status=404) # عرض صفحة تظهر الرسالة (يمكن عرض صفحة html)
              # raise Http404 # عرض نوع الخطأ
              # raise Http404("Car not found") # عرض نوع الخطأ محدد برسالة
          # car = get_object_or_404(Car, id=car_id) # بدون try و except
          return render(request, "products\cars.html", {"car": car})
      ```

   7. الانتقال إلى `cars.html` واستلام مفتاح الكائنات وعمل لوب عليه:

      ```html
      {% block content %}
        {% for car in cars_pass %}
          {{ car.name }}
          {{ car.price }}
        {% endfor %}
      {% endblock content %}
      ```

      - أو أي مفتاح أضيف من خلال متغير `context`

      ```html
      <p>{{ get_mercedes.name }} - {{ get_mercedes.price }}</p>
      ```

      - يمكن إضافة أي خصائص من حقول الجدول إلى اللوب (باستثناء الصور لأن لها إعدادات خاصة)
      - لو عرض الكائن تغير لأحد خصائصه (مثلا كالاسم) باستخدام دالة `__str__` في `models.py` فلن نحتاج لتحديد تلك الخاصية في اللوب:

      ```html
      {% block content %}
        {% for car in cars_pass %}
          {{ car }}
          {{ car.price }}
        {% endfor %}
      {% endblock content %}
      ```

      - `car` = `car.name`

      - أما لو لم يتم تحديد طريقة العرض في `models.py` ولا تحديد الخاصية في اللوب فيستعلم فقط عن مكان السجل: `Car object (1)`

---

## HTML IMG

- لإضافة حقل صورة الكائن في صفحة `html` يجب تفعيل `MEDIA_ROOT` و `MEDIA_URL` بالإعدادات للتمكن من إضافة وسم `img` مثل `STATIC_ROOT` التي أضفناها مع `STATIC_URL` لنقل ملفات `static` للخارج

- ننتقل إلى `settings.py`:

- نكتب أسفل `STATIC_URL`:

```python
MEDIA_ROOT = os.path.join(BADE_DIR, 'media')

MEDIA_URL = '/media/'
```

- ننتقل إلى `urls.py` بنفس مجلد المشروع لتسجيلهم

- نستورد ملف `settings` و `static`:

```python
from django.conf import settings
from django.conf.urls.static import static
```

- تسجيل `MEDIA_URL` و `MEDIA_ROOT` في `urlpatterns` فبعد `[ ]` نضيف:

```python
+ static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

- بمجرد أنشاء كائن جديد بالجدول الذي به حقل `ImageField()` وإضافة صورة له يظهر فولدر جديد باسم `media` يضيف فيه الصور

- نستخدم هذا الفولدر بعرض حقل صورة الكائن من خلال متغير الحلقة من خلال وسم `img` فننتقل إلى `html`:

```html
{% block content %}
  {% for car in cars_pass %}
    {{ car.name }}
    <img src="{{ car.image.url }}" alt="">
  {% endfor %}
{% endblock content %}
```

---

## FORM

- *الفورم هو نموذج يأخذ بيانات المستخدم ويضعها بقاعدة البيانات مثل بيانات الحساب عن طريق تسجيل الدخول*

### إنشاء قاعدة بيانات للنموذج

- إنشاء القاعدة في `models.py`:

```python
from django.db import models

class Contact(models.Model):
    name = models.CharField(max_length=100)
    email = models.EmailField()
    password = models.CharField()
    message = models.TextField()

    def __str__(self):
        return self.name
```

- تسجيل القاعدة في `admin.py`:

```python
from .models import Contact
admin.site.register(Contact)
```

- ترحيل القاعدة من خلال سطر الأوامر:

```sh
python manage.py makemigrations
python manage.py migrate
```

### يوجد 3 طرق لإنشاء FORM

#### 1. إنشاء النموذج بملف `html` في templates

- مثلا ملف `contact.html`:

```html
<form action="#" method="POST">
  {% csrf_token %}

  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required>

  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required>

  <label for="password">Password:</label>
  <input type="password" id="password" name="password" required>

  <label for="message">Message:</label>
  <input type="text" id="message" name="message" required>

  <button type="submit">Submit</button>
</form>
```

- خصائص `form`:

  - `action`: هو مسار `url` الذي يتم إرسال البيانات إليه عند الضغط على زر الإرسال فيمكن وضع مثلا:
    - `"#"`: لترسل لنفس عنوان `url` المسار الحالي الذي جاء منه مثل `https://example.com/contact/` (أي المسار الذي عرض الصفحة عن طريق `render`) فتكون الدالة التي استقبلت الصفحة لتشغيلها هي نفسها التي تعود إليها البيانات فتستقبل الدالة تلك البيانات لمعالجتها (مثل حفظها في قاعدة البيانات (مثل `db.sqlite3`) أو إرسالها إلى لوحة الإدارة أو عرض لرسالة نجاح للمستخدم) أو
      - الهاشتاج يضاف لنهاية `url` بالمتصفح فيمكن إزالته ليكون `action=""` كي يبقى `url` نظيفا
    - `"/contact/"` أو `"{% url 'contact' %}"` ليتم ارسالها إلى مسار آخر له دالة عرض (لو كان ليس هذا المسار أصلا الذي يشغل الصفحة) وهي من تستقبل البيانات لمعالجتها

  - `method`: التعامل مع الطلب
    - `POST`: للمعلومات الحساسة مثل بيانات الحساب فيوفر طبقة حماية من الثغرات من خلال `csrf_token` (يجب أن تكون بأول سطر من النموذج)

    - `GET`: للمعلومات الغير حساسة مثل البحث

  - `novalidate`: يمنع إظهار رسالة التحقق من المتصفح

- داخل الفورم يتم كتابة أوسمة مثل `label` و `input` لتخزين بيانات المستخدم:
  - `label`: عنوان الحقل
    - `for`: يأخذ قيمة `id` الخاصة بأي حقل ليفعله عند الضغط على قيمة `label` (`Name:` كما بالمثال)

  - `input`: حقل إدخال
    - `type`: نوع الحقل
    - `id`: المعرف الخاص بالحقل للتفاعل داخل الصفحات مثل `css`
    - `name`: الاسم الذي سيرسل قيمة أو بيانات الحقل للسيرفر (قاعدة البيانات (يعني قيمته هي نفس قيمة حقل قاعدة البيانات)) والذي يظهر بشريط البروتوكول
    - يعني `input` مثل القاموس مفتاحه `name` وقيمته هي بيانات المستخدم التي يتم إرسالها لحقل قاعدة البيانات
    - `required`: الحقل مطلوب

##### استلام البيانات من request في views مباشرة وإرسالها للوحة الإدارة عن طريق القاعدة

- الانتقال إلى `views.py`:

```python
from django.shortcuts import render
from .models import Contact

def contact_view(request):
    success_message = ""
    if request.method == "POST": 
        name = request.POST.get('name')
        email = request.POST.get('email')
        password = request.POST.get('password')
        message = request.POST.get('message')
        data = Contact(
          name=name,
          email=email,
          password=password,
          message=message,
        )
        data.save()
        success_message = "تم إرسال الرسالة بنجاح"
    return render( request, "contact.html", {"success_message": success_message,}
    )
```

- بالكود:

  - استدعاء القاعدة

  - التأكد من نوع الطلب مثلا لو `GET` نكتب:

    ```python
    if request.method == "GET": 
        name = request.GET.get('name')
    ```

  - `get()`: جلب قيمة كل حقل كالذي بالقواميس، يجب أن تكون القيمة هي قيمة الخاصية `name` في `html`

  - `data`: متغير لوضع بيانات كل حقل في حقلها في قاعدة البيانات
    - المتغير الأول هو حقل قاعدة البيانات
    - المتغير الثاني هو قيمة `name` في `html` الذي استقبل بيانات المستخدم
  - `data.save()`: حفظ البيانات بقاعدة البيانات
    - قاعدة البيانات تكون مسجلة بلوحة الإدارة عن طريق `Admin Site`

  - في النهاية نرجع الصفحة مصحوبة برسالة النجاح من خلال مفتاح `success_message` لكن يجب وضعها فقط بشرط إن ضغط المستخدم على زر الإرسال وإلا فستظهر الرسالة بمجرد الدخول للصفحة فنكتب في `html` خارج `form`:

  ```html
  <form>
  </form>
  {% if success_message %}
  {{ success_message }}
  {% endif %}
  ```

- في النماذج البسيطة التي لا تحتاج لمعالجة الكائن قبل حفظه يمكن حفظ الكائن مباشرة بمجرد إنشائه بدون عمل `save`:

```python
Contact.objects.create(
    name=name,
    email=email,
    password=password,
    message=message,
)
```

- يمكن إنشاء كائن غير محفوظ حتى يتم ادخال إليه بيانات الحقول:

```python
form = data.save(commit=False)
```

- في الدالة قمنا بعمل تهيئة لرسالة النجاح فتضمن أن المتغير موجود دائمًا في الذاكرة لأنه يتم طلب `GET` عند فتح الصفحة لأول مرة فبالتالي لن يدخل في شرط `if` لأنه ليس `POST` فيكون المتغير `success_message` غير مُعرَّف أصلًا فستظهر خطأ: `UnboundLocalError` لأنك تحاول استخدام متغير غير موجود لذا يجب تهيئة `success_message` لكي يكون له قيمة فارغة يظهر بها أثناء الدخول على الصفحة

---

#### 2. إنشاء النموذج بملف خارجي واستيراد وحدته لإنشائه

- داخل التطبيق ننشئ ملف `form.py`

- ندخل عليه ونقوم باستيراد وحدة إنشاء النموذج وننشئ منه نموذج ونضيف إليه الحقول:

```python
from django import forms
class LoginForm(forms.Form):
  name = forms.CharField(max_length=100, label="Name:", help_text="Enter your name")
  email = forms.EmailField(label="Email:", required=True)
  password = forms.CharField(label="Password:", widget=forms.PasswordInput)
  message = forms.CharField(widget=forms.Textarea, label="Message:", disabled=True)
```

- يجب أن يكون اسم الجدول في قاعدة البيانات (`Contact`) مختلف عن اسمه في `forms` (`LoginForm`)

- `Form`: خاصية لاستيراد حقول النموذج

- `label`: عنوان الحقل

- `help_text`: قيمة إرشادية تكتب تحت عنوان الحقل (تختلف عن `placeholder` لأنها تكتب داخل الحقل)

- `required`: الحقل مطلوب (`True` افتراضي)

- `PasswordInput`: خاصية للباسوورد لإخفاء النص لأن `password` غير موجود كحقل في `forms` كما في `html`

- `Textarea`: خاصية لتكبير المربع للرسائل لأن `TextField` غير موجود كحقل في `forms` كما في `models` أو `text` كما في `html` لأن `models` يحدد طريقة تخزينها أما `forms` يحدد طريقة إدخالها وعرضها لذا نستخدم `CharField` مع جعله مربعا كبيرا

- `disabled`: يمنع إدخال البيانات (`False` يسمح (افتراضي))

- في `forms` لا يوجد تحديد عرض الكائن كنص من خلال `__str__` لأن `forms` ليس كائن بيانات دائم مثل `models` بل أداة إدخال مؤقتة

- جداول `forms` لا يتم تسجيلها في `admin.py`

##### استلام البيانـات من request في views عن طريق forms.py وإرسالها للوحة الإدارة عن طريق القاعدة

- الانتقال إلى `views.py`:

```python
from django.shortcuts import render
from .models import Contact
from .forms import LoginForm

def contact_view(request):
    success_message = ""
    if request.method == "POST": 
        name = request.POST.get('name')
        email = request.POST.get('email')
        password = request.POST.get('password')
        message = request.POST.get('message')
        data = Contact(
          name=name,
          email=email,
          password=password,
          message=message,
        )
        data.save()
        success_message = "تم إرسال الرسالة بنجاح"
    return render(request, "contact.html", {
      "login": LoginForm(),
      "success_message": success_message,
      }
    )
```

- قيمة `get()` هي قيمة الخاصية `name` في `html` لكن بما أننا نعتمد على حقول الجدول فستنشئ `Django` ملف `html` افتراضي مطابقا لها فتأخذ القيمة من خاصية `name` المأخوذة من اسم الحقل في الجدول

- قمنا بإرسال `form` من قاموس البيانات إلى ملف `html` مصحوبا بـ `()` ليكون كائنا من الجدول وليس الجدول نفسه فننتقل إلى `html` لاستقباله:

```html
<form action="#" method="POST">
  {% csrf_token %}
  {{ login }}
  <button type="submit">Submit</button>
</form>
{% if success_message %}
  {{ success_message }}
{% endif %}
```

- لم ننشئ حقول للـ `form` ووضعنا مكانها كائن جدولها الذي أنشأناه

- يمكن تحديد حقل معين:

```html
{{ login.message }}
```

- يمكن عرض النموذج كفقرات من خلال وسم `p`:

```html
{{ login.as_p }}
```

- لعرض النموذج كقائمة غير مرتبة:

```html
{{ login.as_ul }}
```

---

#### 3. إنشاء النموذج بملف خارجي واستيراد جدوله من قاعدة البيانات

- الانتقال إلى `form.py`:

```python
from .models import Contact

class LoginModelForm(forms.ModelForm):
  class Meta:
    model = Contact
    fields = "__all__"
    widgets = {
                'password': forms.PasswordInput(),
                'message': forms.Textarea(attrs={'rows': 4, 'cols': 40}),
            }
            labels = {
                'name': 'Full Name',
                'email': 'Email Address',
                'password': 'Password',
                'message': 'Your Message',
            }

```

- `ModelForm`: خاصية لاستيراد حقول قاعدة البيانات

- `Meta`: لتحديد القاعدة (ليس كالموجود بقاعدة البيانات الذي يغير اسم القاعدة)

- `model`: تخزين قاعدة البيانات (لاستقبال البيانات من النموذج)

- `fields`: جلب الحقول
  - لجلبها كلها نستخدم: `__all__`
  - لجلب حقول محددة نستخدم القائمة: `['name', 'email']`

- `exclude`: استثناء حقول من الجلب:
  - `exclude = ['message']`

- ❌ لا يمكن استخدام `fields` و `exclude` معًا

- `widgets`: يحدد كيف سيظهر كل حقل في واجهة المستخدم (`HTML form`).

##### استلام البيانات من request عن طريق forms.py التي تلرسلها للوحة الإدارة

- الانتقال إلى `views.py`:

```python
from django.shortcuts import render
from .forms import LoginModelForm

def contact_view(request):
    success_message = ""
    if request.method == "POST":
        form = LoginModelForm(request.POST)
        if form.is_valid():
            form.save()
            success_message = "تم إرسال الرسالة بنجاح"
            form = LoginModelForm()  # إعادة تعيين النموذج بعد الحفظ
    else:
        form = LoginModelForm() # إعادة إرسال النموذج المعبأ عند وجود أخطاء
    return render(request, "contact.html", {
        "login": form,
        "success_message": success_message,
    })
```

- `LoginModelForm(request.POST)`: كائن من جدول النموذج يستقبل بيانات الحقول ويرسلها للقاعدة عن طريق `model`

- لم يتم جلب بيانات الحقول من النموذج عن طريق `get()` لوضعها في القاعدة لأن النموذج أصلا خزن القاعدة في `model` فيتم نقلها إليها مباشرة من خلال كائن جدول النموذج

- `is_valid()`: التحقق من صحة البيانات قبل الحفظ حتى لا يتم حفظ بيانات غير صالحة

- في النهاية يتم إرسال مفتاح النموذج إلى `html` ليستقبل البيانات ويعيدها من خلال `action` ليتم معالجتها وإرسالها للوحة الإدارة وتحقيق شرط رسالة النجاح (كما بالطريقة الثانية) فتكون هكذا في `html`:

```html
<form action="#" method="POST">
  {% csrf_token %}
  {{ login }}
  <button type="submit">Submit</button>
</form>
{% if success_message %}
  {{ success_message }}
{% endif %}
```

---

- يمكن إضافة رسالة النجاح من خلال نظام `message` في `Django`

- نظام *messages* في `Django` يسمح لك بعرض رسائل مؤقتة (نجاح، خطأ، تحذير...) للمستخدم بعد أي عملية (مثل الحفظ أو الحذف).

*مثال بسيط:*

*في `view`:*

```python
from django.contrib import messages
from django.shortcuts import render, redirect

def my_view(request):
    # بعد تنفيذ أي عملية
    messages.success(request, "تمت العملية بنجاح!")
    messages.error(request, "حدث خطأ ما!")
    return redirect('home')
```

*في القالب (`template`):*

```django
{% if messages %}
  {% for message in messages %}
    <div class="alert alert-{{ message.tags }}">
      {{ message }}
    </div>
  {% endfor %}
{% endif %}
```

---

*أنواع الرسائل:*

- `messages.success(request, "نجاح")`
- `messages.info(request, "معلومة")`
- `messages.warning(request, "تحذير")`
- `messages.error(request, "خطأ")`

---

*ملخص:*  

- أضف الرسالة في الـ `view`.
- اعرضها في القالب.
- تختفي تلقائيًا بعد عرضها مرة واحدة.

---

*الفرق بين `id` و `pk`*

1. *`id` (الأساسي)*:

- هو الحقل الفعلي في قاعدة البيانات
- دائماً يكون رقم (1, 2, 3, ...)

- ```python
  User.objects.get(id=5)  # بحث بالرقم 5 مباشرة
  ```

1. *`pk` (المرن)*:

- يعني "Primary Key" (المفتاح الأساسي)
- يشير إلى `id` تلقائياً

- ```python
  User.objects.get(pk=5)  # نفس النتيجة لكن بأسلوب أفضل
  ```

*متى تستخدم أياً منهما؟*:

استخدم `id` عندما:

- تريد الوصول المباشر للحقل

- ```python
  print(user.id)  # 5
  ```

استخدم `pk` عندما:

- تريد البحث في العلاقات بين الجداول
- تريد كود أكثر مرونة

- ```python
  # بحث في العلاقات
  Topic.objects.filter(board__pk=5)  # ✓ أفضل
  Topic.objects.filter(board__id=5)  # ✓ يعمل
  ```

*الخلاصة البسيطة*:

- `id` → للحقل المباشر
- `pk` → للبحث في العلاقات (أفضل)

مثال عملي:

```python
# هذه متشابهة وتعمل بنفس القوة:
user = User.objects.get(id=5)
user = User.objects.get(pk=5)

# ولكن في العلاقات، pk أفضل:
topics = Topic.objects.filter(board__pk=5)  # ✓ أحسن أسلوب
```

### الفرق بين الطرق الثلاثة

- `Forms`: يدويا باستخدام `HTML`:

- الميزات:
-> تحكم كامل في `HTML`
-> لا حاجة لتعريف كلاس `Form`

- العيوب:

> لا يوجد تحقق (`Validation`) تلقائي
> أكثر عرضة للأخطاء
> تكرار للكود

- `Django Forms` باستخدام -> `forms.Form`

- المميزات:

> التحقق التلقائي من البيانات
> سهولة التكرار وإعادة الاستخدام
> التنظيف والتحقق من الحقول باستخدام clean()

- العيوب:

> تحتاج كتابة `form` مرتين: في الكلاس وHTML (إلا إن استخدمت {{ form }})

- `ModelForm`: باستخدام `forms.ModelForm`

- المميزات:

> أقل تكرار للكود
> الفورم يتحدث تلقائيًا عند تعديل الموديل
> مثالي لعمليات الـ `CRUD`

- العيوب:

> أقل مرونة إن كنت تحتاج منطق مخصص جدًا

---

- لإضافة فورم للحساب جاهز في `views`:

```python
from django.contrib.auth.forms import AuthenticationForm, UserCreationForm

def login_view(request):
    form = AuthenticationForm() # تسجيل لمستخدم موجود
    return render(request, 'accounts/login.html', {'form': form})

def register_view(request):
    form = UserCreationForm() # تسجيل لمستخدم جديد
    return render(request, 'accounts/register.html', {'form': form})
```

- يمكن الاستعلام أن المستخدم مسجل من خلال `user.is_authenticated`

- لإضافة رابط مدمج (جاهز) لدالة تسجيل الخروج ودالة تسجيل الدخول لمستخدم موجود ودالة لتغيير الباسوورد ودالة للتأكيد في `urls`:

```python
# urls.py
from django.urls import path
from django.contrib.auth import views as auth_views
from . import views

urlpatterns = [
    path('accounts/login/', auth_views.LoginView.as_view(template_name='login.html'), name='login'),
    
    path('accounts/logout/', auth_views.LogoutView.as_view(), name='logout'),

    path('change_password/', auth_views.PasswordChangeView.as_view(template_name='change_password.html'), name='change_password')

    path('password-change/done/', auth_views.PasswordChangeDoneView.as_view(template_name='accounts/password_change_done.html'), name='password_change_done'),
    
    # الصفحات المحمية
    path('profile/', views.profile_view, name='profile'),
    
    path('dashboard/', views.dashboard_view, name='dashboard'),
    
    path('secret/', views.secret_page, name='secret'),
]
```

- ثم توجيههم لصفحة معينة من خلال `settings.py`:

```python
LOGOUT_REDIRECT_URL = '/accounts/login/' # الصفحة الافتراضية بعد تسجيل الخروج
LOGIN_REDIRECT_URL = '/profile/' # الصفحة الافتراضية بعد تسجيل الدخول
LOGIN_URL = '/accounts/login/' # URL صفحة تسجيل الدخول
```

- بهذه الطريقة لسنا بحاجة لإنشاء دوال عرض مخصصة لهم فقط ننشئ قالب `html` لكل صفحة

- لمنع المستخدمين غير المسجلين من الوصول إلى الصفحة وإعادة توجيههم لصفحة تسجيل الدخول نستخدم ديكوريتور يتم وضعه فوق دالة الصفحة:

```python
# views.py
from django.shortcuts import render
from django.contrib.auth.decorators import login_required

@login_required
def profile_view(request):
    return render(request, 'profile.html', {'user': request.user})

@login_required
def dashboard_view(request):
    return render(request, 'dashboard.html', {'user': request.user})

@login_required
def secret_page(request):
    return render(request, 'secret.html', {'user': request.user})
```

- والقوالب تكون هكذا مثلا:

```html
...
<h2>مرحباً {{ user.username }}!</h2>
    <p>هذه صفحتك الشخصية</p>
    
    <nav>
        <a href="{% url 'dashboard' %}">لوحة التحكم</a> | 
        <a href="{% url 'secret' %}">الصفحة السرية</a> | 
        <a href="{% url 'logout' %}">تسجيل الخروج</a>
    </nav>
...
```

- بعدها سيتم توجيههم لمسار `LOGIN_REDIRECT_URL` لذا إن أردنا إعادة توجيههم للصفحة القادمين منها علينا تمرير معامل `next` يالصفحة في طلب تسجيل الدخول من صفحة تسجيل الدخول فيكون الطلب بهذا الشكل:

```html
{% if user.is_authenticated %} <!-- للتحقق من المصادقة -->
    <!-- النموذج الحالي -->
{% else %}
    <div class="alert alert-info">
        <p>You need to <a href="{% url 'login' %}?next={{ request.path }}">login</a> to post.</p>
    </div>
{% endif %}
```

- ثم يتم إعادة التوجيه من صفحة تسجيل الدخول:

```html
<form method="post" novalidate>
    {% csrf_token %}
    
    <input type="hidden" name="next" value="{{ next }}">
    {# {{ next }} هي قيمة مدمجة وهي الصفحة التي وجهت المستخدم لصفحة تسجيل الدخول #}
    ...
    <button type="submit" class="btn btn-primary">Login</button>
</form>
```

- الدالة المدمجة `LoginView`:
  - تقوم تلقائيًا بمعالجة معامل `next`
  - بعد تسجيل الدخول الناجح، توجيه إلى الصفحة المحددة في `next`
  - إذا لم يكن هناك `next`، توجيه إلى `LOGIN_REDIRECT_URL`

- فمثلا الكود الداخلي لـ `LoginView` يكون بهذا الشكل:

```python
from django.utils.http import url_has_allowed_host_and_scheme # التحقق من أن الرابط لا يؤدي إلى توجيه خارج الموقع

def form_valid(self, form):
    login(self.request, form.get_user())
    
    # الحصول على معامل next من URL
    next_url = self.request.GET.get('next')
    
    if next_url and url_has_allowed_host_and_scheme(next_url, allowed_hosts=None):
        return redirect(next_url)
    else:
        return redirect(settings.LOGIN_REDIRECT_URL)
```

- فإن أردنا إنشاء دالة مخصصة لصفحة التسجيل (بدلا من استخدام الدالة المدمجة) يجب الحصول على `next` من المعامل أو استخدام الافتراضي:

```python
def login_view(request):
    if request.method == 'POST':
        username = request.POST['username']
        password = request.POST['password']
        user = authenticate(request, username=username, password=password)
        
        if user is not None:
            login(request, user)
            # الحصول على next من المعامل أو استخدام الافتراضي
            next_url = request.GET.get('next', 'profile')
            return redirect(next_url)
    
    return render(request, 'login.html')
```

- ويكون قالب تسجيل الدخول للدالة المخصصة:

```html
<!-- templates/login.html -->
...
    <form method="post">
        {% csrf_token %}
        ...
        <button type="submit">تسجيل الدخول</button>
    </form>

    {% if request.GET.next %}
        <p>سيتم توجيهك إلى: {{ request.GET.next }}</p>
    {% endif %}
...
```

- أو لو أردنا الدالة مخصصة لكن النموذج مدمج:

```python
def login_view(request):
    if request.method == 'POST':
        form = AuthenticationForm(request, data=request.POST)  # استخدام النموذج المدمج
        if form.is_valid():
            user = form.get_user()
            login(request, user)
            next_url = request.POST.get('next') or request.GET.get('next') or 'profile'
            return redirect(next_url)
    else:
        form = AuthenticationForm()
    
    return render(request, 'login.html', {'form': form})
```

- وفي القالب:

```html
<!-- تحسين النموذج ليعمل مع next -->
<form method="post">
    {% csrf_token %}
    <input type="hidden" name="next" value="{{ request.GET.next }}">
    {{ form.as_p }}
    <button type="submit">تسجيل الدخول</button>
</form>
```

- مثال آخر مع معامل مخصص:

```python
@login_required(login_url='/custom-login/')
def special_view(request):
    return render(request, 'special.html')
```

- في هذا المثال، عندما يحاول المستخدم الوصول إلى `/special/`:
  - يتم توجيهه إلى `/custom-login/?next=/special/`
  - بعد التسجيل، يعود إلى `/special/`

---

## Views Strategies

- *إنشاء دوال العرض يتم من خلال ثلاث طرق*

### FBV (Function-Based Views) - واجهات قائمة على الدوال

*FBV* هي الطريقة التقليدية لكتابة الواجهات في `Django` باستخدام دوال عادية.

مثال على `FBV`:

ملف `views.py`:

```python
from django.shortcuts import render, get_object_or_404, redirect
from django.http import HttpResponse
from .models import Article
from .forms import ArticleForm

def article_list(request):
    articles = Article.objects.all()
    return render(request, 'articles/article_list.html', {'articles': articles})

def article_detail(request, pk):
    article = get_object_or_404(Article, pk=pk)
    return render(request, 'articles/article_detail.html', {'article': article})

def article_create(request):
    if request.method == 'POST':
        form = ArticleForm(request.POST)
        if form.is_valid():
            article = form.save()
            return redirect('article_detail', pk=article.pk)
    else:
        form = ArticleForm()
    return render(request, 'articles/article_form.html', {'form': form})

def article_update(request, pk):
    article = get_object_or_404(Article, pk=pk)
    if request.method == 'POST':
        form = ArticleForm(request.POST, instance=article)
        if form.is_valid():
            form.save()
            return redirect('article_detail', pk=article.pk)
    else:
        form = ArticleForm(instance=article)
    return render(request, 'articles/article_form.html', {'form': form})

def article_delete(request, pk):
    article = get_object_or_404(Article, pk=pk)
    if request.method == 'POST':
        article.delete()
        return redirect('article_list')
    return render(request, 'articles/article_confirm_delete.html', {'article': article})
```

ملف `urls.py`:

```python
from django.urls import path
from . import views

urlpatterns = [
    path('articles/', views.article_list, name='article_list'),
    path('articles/<int:pk>/', views.article_detail, name='article_detail'),
    path('articles/create/', views.article_create, name='article_create'),
    path('articles/<int:pk>/update/', views.article_update, name='article_update'),
    path('articles/<int:pk>/delete/', views.article_delete, name='article_delete'),
]
```

مزايا `FBV`:

- *بسيطة وواضحة* للمبتدئين
- *مرنة* وسهلة التخصيص
- *سهلة التصحيح* (`debugging`)
- *تحكم كامل* في التدفق المنطقي

عيوب `FBV`:

- *تكرار الكود* في المشاريع الكبيرة
- *صعوبة إعادة الاستخدام* في بعض الحالات

### CBV (Class-Based Views) - واجهات قائمة على الفئات

*CBV* هي طريقة أكثر تقدمًا تستخدم الفئات بدلاً من الدوال.

مثال على `CBV`:

ملف `views.py`:

```python
from django.views import View
from django.shortcuts import render, get_object_or_404, redirect
from django.http import HttpResponse
from .models import Article
from .forms import ArticleForm

class ArticleListView(View):
    def get(self, request):
        articles = Article.objects.all()
        return render(request, 'articles/article_list.html', {'articles': articles})

class ArticleDetailView(View):
    def get(self, request, pk):
        article = get_object_or_404(Article, pk=pk)
        return render(request, 'articles/article_detail.html', {'article': article})

class ArticleCreateView(View):
    def get(self, request):
        form = ArticleForm()
        return render(request, 'articles/article_form.html', {'form': form})
    
    def post(self, request):
        form = ArticleForm(request.POST)
        if form.is_valid():
            article = form.save()
            return redirect('article_detail', pk=article.pk)
        return render(request, 'articles/article_form.html', {'form': form})

class ArticleUpdateView(View):
    def get(self, request, pk):
        article = get_object_or_404(Article, pk=pk)
        form = ArticleForm(instance=article)
        return render(request, 'articles/article_form.html', {'form': form})
    
    def post(self, request, pk):
        article = get_object_or_404(Article, pk=pk)
        form = ArticleForm(request.POST, instance=article)
        if form.is_valid():
            form.save()
            return redirect('article_detail', pk=article.pk)
        return render(request, 'articles/article_form.html', {'form': form})

class ArticleDeleteView(View):
    def get(self, request, pk):
        article = get_object_or_404(Article, pk=pk)
        return render(request, 'articles/article_confirm_delete.html', {'article': article})
    
    def post(self, request, pk):
        article = get_object_or_404(Article, pk=pk)
        article.delete()
        return redirect('article_list')
```

ملف `urls.py`:

```python
from django.urls import path
from . import views

urlpatterns = [
    path('articles/', views.ArticleListView.as_view(), name='article_list'),
    path('articles/<int:pk>/', views.ArticleDetailView.as_view(), name='article_detail'),
    path('articles/create/', views.ArticleCreateView.as_view(), name='article_create'),
    path('articles/<int:pk>/update/', views.ArticleUpdateView.as_view(), name='article_update'),
    path('articles/<int:pk>/delete/', views.ArticleDeleteView.as_view(), name='article_delete'),
]
```

مزايا `CBV`:

- *تنظيم أفضل* للكود
- *إعادة استخدام* أسهل
- *وراثة* وتوسيع الوظائف
- *فصل المسؤوليات* (كل طريقة في مكانها)

عيوب `CBV`:

- *منحنى تعلم* أعلى قليلاً
- *أكثر تعقيدًا* في التصحيح

### GCBV (Generic Class-Based Views) - واجهات عامة قائمة على الفئات

*GCBV* هي فئات مجهزة مسبقًا بميزات شائعة لتقليل تكرار الكود.

مثال على `GCBV`:

ملف `views.py`:

```python
from django.views.generic import ListView, DetailView, CreateView, UpdateView, DeleteView
from django.urls import reverse_lazy
from .models import Article
from .forms import ArticleForm

class ArticleListView(ListView):
    model = Article
    template_name = 'articles/article_list.html'
    context_object_name = 'articles' # الافتراضي object_list
    paginate_by = 10

class ArticleDetailView(DetailView):
    model = Article
    template_name = 'articles/article_detail.html'
    context_object_name = 'article'

class ArticleCreateView(CreateView):
    model = Article
    form_class = ArticleForm
    template_name = 'articles/article_form.html'
    success_url = reverse_lazy('article_list')

class ArticleUpdateView(UpdateView):
    model = Article
    form_class = ArticleForm
    template_name = 'articles/article_form.html'
    success_url = reverse_lazy('article_list')

class ArticleDeleteView(DeleteView):
    model = Article
    template_name = 'articles/article_confirm_delete.html'
    success_url = reverse_lazy('article_list')
```

- `ListView` - لعرض قائمة من العناصر
- `DetailView` - لعرض تفاصيل عنصر واحد
- `CreateView` - لإنشاء عنصر جديد
- `UpdateView` - لتحديث عنصر موجود
- `DeleteView` - لحذف عنصر

- يوجد خصائص إخرى مثل:
  - `fields`: للحقول (بحالة عدم وجود نموذج)
  - `pk_url_name`: للمعرف

ملف `urls.py`:

```python
from django.urls import path
from . import views

urlpatterns = [
    path('articles/', views.ArticleListView.as_view(), name='article_list'),
    path('articles/<int:pk>/', views.ArticleDetailView.as_view(), name='article_detail'),
    path('articles/create/', views.ArticleCreateView.as_view(), name='article_create'),
    path('articles/<int:pk>/update/', views.ArticleUpdateView.as_view(), name='article_update'),
    path('articles/<int:pk>/delete/', views.ArticleDeleteView.as_view(), name='article_delete'),
]
```

مزايا `GCBV`:

- *توفير الوقت* والجهد
- *أقل كود متكرر*
- *معايير قياسية* لمهام شائعة
- *سهولة الصيانة*

عيوب `GCBV`:

- *صعبة التخصيص* في بعض الحالات المعقدة
- *منحنى تعلم* أعلى
- *قد تكون بطيئة* في الفهم للوافدين الجدد

---

### reverse vs reverse_lazy vs redirect

#### reverse

*reverse* هي دالة ذكية في `Django` تعطيك *العنوان الكامل لصفحة* بمجرد معرفة *اسمها* في ملف `urls.py`.

مثل دليل الهاتف، فتخيل أنك تريد الاتصال بصديق:

- لديك *اسمه* (مثل "أحمد")
- تبحث في *دليل الهاتف* (`reverse`) لتحصل على *رقمه* (`URL`)

كيف تعمل؟

في ملف `urls.py`

```python
from django.urls import path
from . import views

urlpatterns = [
    path('home/', views.home, name='home_page'),
    path('about/', views.about, name='about_page'),
]
```

استخدام `reverse`:

```python
from django.urls import reverse

# الحصول على العنوان من الاسم
url = reverse('home_page')    # يعيد: '/home/'
url = reverse('about_page')   # يعيد: '/about/'
```

لماذا نستخدم `reverse؟`

1. تجنب الأخطاء في الروابط

   - بدون `reverse`:

   ```python
   return redirect('/home/')  # إذا غيرت المسار، سينكسر الكود
   ```

   - مع `reverse`:

   ```python
   return redirect(reverse('home_page'))  # يعمل دائمًا حتى لو تغير المسار
   ```

2. ديناميكية مع الباراميترات

  ```python
  # في urls.py
  path('user/<int:user_id>/', views.user_profile, name='user_profile')

  # في الكود
  url = reverse('user_profile', args=[5])  # يعيد: '/user/5/'
  url = reverse('user_profile', kwargs={'user_id': 5})  # نفس النتيجة
  ```

#### reverse_lazy

*reverse_lazy* هي نسخة مؤجلة (`lazy`) من الدالة `reverse` في `Django`، تُستخدم بشكل أساسي في تعريفات المستوى الأعلى (مثل تعريفات الفئات) حيث لا يمكن الوصول إلى `URLconf` أثناء التحميل.

استخدامات `reverse_lazy`:

```python
from django.urls import reverse_lazy
from django.views.generic import CreateView
from .models import Post

class PostCreateView(CreateView):
    model = Post
    fields = ['title', 'content']
    success_url = reverse_lazy('post_list')  # هنا لا يمكن استخدام reverse العادي
```

مميزات `reverse_lazy`:

- *تقيؤ مؤجل*: لا تحسب `URL` حتى تكون هناك حاجة فعلية لها
- *مناسبة للاستخدام في تعريفات الفئات* (`class attributes`)
- *تجنب أخطاء التحميل الدائري* في `URLs`

الفرق بين `reverse` و `reverse_lazy`

`reverse` - فورية

```python
def my_view(request):
    url = reverse('home_page')  # تحسب الآن!
    return redirect(url)
```

`reverse_lazy` - مؤجلة

```python
from django.urls import reverse_lazy

# تحسب فقط عندما تُستخدم لأول مرة
success_url = reverse_lazy('home_page')
```

أمثلة عملية:

مثال 1: في `template`

```html
<a href="{% url 'home_page' %}">الرئيسية</a>
<!-- يعادل: <a href="/home/">الرئيسية</a> -->
```

مثال 2: في `view`

```python
from django.urls import reverse
from django.shortcuts import redirect

def my_view(request):
    # إعادة توجيه إلى صفحة about
    return redirect(reverse('about_page'))
```

مثال 3: مع `parameters`

```python
def show_user(request, user_id):
    profile_url = reverse('user_profile', args=[user_id])
    return redirect(profile_url)
```

متى تستخدم `reverse`؟

1. *inside functions* - داخل الدوال
2. *when you need the URL now* - عندما تحتاج `URL` فورًا
3. *in views, models, or any function* - في أي مكان يعمل أثناء التنفيذ

الخلاصة

- *reverse* = "أعطني عنوان هذه الصفحة بمجرد معرفة اسمها"
- *تفيد في*:
  - الحفاظ على الكود نظيفًا
  - تجنب الأخطاء عند تغيير المسارات
  - العمل مع الروابط الديناميكية

```python
# بسيط جدًا!
from django.urls import reverse

url = reverse('page_name')  # أحصل على العنوان من الاسم
```

#### redirect

*redirect* هي دالة مساعدة تُستخدم في الدوال (`views`) لإعادة توجيه المستخدم إلى `URL` آخر.

استخدامات `redirect`:

```python
from django.shortcuts import redirect
from django.http import HttpResponse

def my_view(request):
    # إعادة توجيه باستخدام اسم URL
    return redirect('post_list')
    
    # أو إعادة توجيه باستخدام مسار URL
    return redirect('/posts/')
    
    # أو إعادة توجيه إلى كائن معين
    post = Post.objects.get(id=1)
    return redirect(post)
```

الفروق الرئيسية بين `reverse_lazy` و `redirect`

| reverse_lazy | redirect |
|-------------|----------|
| تُستخدم في تعريفات الفئات والمستوى الأعلى | تُستخدم داخل دوال الـ views |
| تُرجع كائنًا مؤجلًا | تُرجع HttpResponseRedirect مباشرة |
| للحصول على URL كسلسلة نصية | لإعادة التوجيه الفوري |
| مناسبة لـ class-based views | مناسبة لـ function-based views |

أمثلة عملية

مثال باستخدام `reverse_lazy`:

```python
from django.urls import reverse_lazy
from django.views.generic import DeleteView
from .models import Article

class ArticleDeleteView(DeleteView):
    model = Article
    success_url = reverse_lazy('article_list')
```

مثال باستخدام `redirect`:

```python
from django.shortcuts import redirect

def create_article(request):
    if request.method == 'POST':
        # معالجة البيانات
        return redirect('article_list')
```

خطأ شائع:

```python
from django.urls import reverse
from django.views.generic import CreateView

class MyView(CreateView):
    success_url = reverse('my_url')  # ❌ خطأ - reverse لا يعمل هنا
```

الخلاصة

- استخدم *reverse_lazy* عندما تحتاج إلى `URL` في تعريفات الفئات (`class attributes`)
- استخدم *redirect* عندما تريد إعادة توجيه المستخدم من داخل دالة `view`
- `reverse_lazy` للتقيؤ المؤجل، `redirect` للإعادة التوجيه الفوري

---

### تنظيم الروابط

*استخدام `include()` لتنظيم الروابط*

المشروع الرئيسي `urls.py`:

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('blog/', include('blog.urls')),  # تضمين روابط التطبيق
    path('', include('pages.urls')),  # روابط الصفحات الرئيسية
]
```

تطبيق `blog/urls.py`:

```python
from django.urls import path
from . import views

app_name = 'blog'  # اسم التطبيق للتمييز بين الروابط المتشابهة

urlpatterns = [
    path('', views.ArticleListView.as_view(), name='article_list'),
    path('<int:pk>/', views.ArticleDetailView.as_view(), name='article_detail'),
    path('create/', views.ArticleCreateView.as_view(), name='article_create'),
    path('<int:pk>/update/', views.ArticleUpdateView.as_view(), name='article_update'),
    path('<int:pk>/delete/', views.ArticleDeleteView.as_view(), name='article_delete'),
]
```

تطبيق `pages/urls.py`:

```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='home'),
    path('about/', views.about, name='about'),
    path('contact/', views.contact, name='contact'),
]
```

### كيفية استخدام أسماء الروابط في القوالب

في القوالب (Templates):

```html
<!-- رابط لقائمة المقالات -->
<a href="{% url 'article_list' %}">جميع المقالات</a>

<!-- رابط لتفاصيل مقال معين -->
<a href="{% url 'article_detail' pk=article.pk %}">{{ article.title }}</a>

<!-- رابط مع اسم التطبيق للتمييز -->
<a href="{% url 'blog:article_detail' pk=article.pk %}">{{ article.title }}</a>

<!-- رابط مع параметры إضافية -->
<a href="{% url 'article_update' pk=article.pk %}">تعديل المقال</a>

<!-- زر لحذف مقال -->
<form method="post" action="{% url 'article_delete' pk=article.pk %}">
    {% csrf_token %}
    <button type="submit">حذف</button>
</form>
```

في الكود (Python):

```python
from django.shortcuts import redirect
from django.urls import reverse

# إعادة توجيه إلى صفحة معينة
return redirect('article_list')

# إعادة توجيه مع параметر
return redirect('article_detail', pk=article.pk)

# الحصول على رابط كسلسلة نصية
url = reverse('article_detail', kwargs={'pk': article.pk})
```

### استخدام الروابط الديناميكية مع GCBV

نمط الروابط الأكثر مرونة::

```python
from django.urls import path, re_path
from . import views

urlpatterns = [
    # استخدام المسارات العادية
    path('articles/<int:pk>/', views.ArticleDetailView.as_view(), name='article_detail'),
    
    # استخدام التعبيرات المنتظمة
    re_path(r'^articles/(?P<slug>[\w-]+)/$', views.ArticleDetailView.as_view(), name='article_detail'),
    
    # استخدام عدة параметرات
    path('category/<int:category_id>/article/<int:pk>/', views.ArticleDetailView.as_view(), name='article_detail'),
]
```

### مقارنة بين الأنواع الثلاثة

| المعيار | `FBV` | `CBV` | `GCBV` |
|---------|-----|-----|------|
| *البساطة* | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ |
| *المرونة* | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| *إعادة الاستخدام* | ⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| *التخصيص* | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ |
| *كود أقل* | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| *منحنى التعلم* | منخفض | متوسط | عالي |

متى تستخدم كل نوع؟

1. *استخدم `FBV` عندما*:
   - الواجهة بسيطة ووظيفتها محددة
   - تحتاج إلى تحكم كامل في التدفق المنطقي
   - تتعلم `Django` للمرة الأولى

2. *استخدم `CBV` عندما*:
   - تريد تنظيمًا أفضل للكود
   - تحتاج إلى إعادة استخدام الوظائف
   - تريد فصل طرق `HTTP` (`GET`, `POST`, etc.)

3. *استخدم `GCBV` عندما*:
   - تقوم بمهام شائعة (عرض، إنشاء، تعديل، حذف)
   - تريد توفير الوقت وتقليل تكرار الكود
   - العمل على مشروع كبير به العديد من النماذج المتشابهة

### مثال عملي يوضح الفروقات

1. باستخدام `FBV`:

    ```python
    def article_list(request):
        articles = Article.objects.all()
        paginator = Paginator(articles, 10)
        page = request.GET.get('page')
        articles_page = paginator.get_page(page)
        return render(request, 'article_list.html', {'articles': articles_page})
    ```

2. باستخدام `CBV`:

    ```python
    class ArticleListView(View):
        def get(self, request):
            articles = Article.objects.all()
            paginator = Paginator(articles, 10)
            page = request.GET.get('page')
            articles_page = paginator.get_page(page)
            return render(request, 'article_list.html', {'articles': articles_page})
    ```

3. باستخدام `GCBV`:

    ```python
    class ArticleListView(ListView):
        model = Article
        paginate_by = 10
        template_name = 'article_list.html'
        context_object_name = 'articles'
    ```

الخلاصة:

- *FBV* مناسبة للمبتدئين والمهام البسيطة
- *CBV* توفر تنظيمًا أفضل وإعادة استخدام
- *GCBV* توفر حلولاً جاهزة للمهام الشائعة وتوفر الوقت

في المشاريع الحقيقية، غالبًا ما يتم استخدام مزيج من هذه الأنواع حسب احتياجات كل واجهة.

---

### ملخص تفصيلي سريع عن كيفية وصول البيانات إلى وحدة الإدارة

عندما يقوم المستخدم بإدخال بيانات عبر نموذج (`Form`) في `Django` وتُرسل إلى وحدة الإدارة (`Admin Interface`) أو إلى خادم الويب (`Server`)، تمر البيانات بعدة مراحل لمعالجتها وتخزينها. إليك *المراحل الرئيسية* بالتفصيل:

---

#### 1. *إدخال البيانات بواسطة المستخدم (User Input)*

- المستخدم يملأ النموذج (`Form`) في المتصفح (مثل صفحة تسجيل الدخول أو إضافة محتوى).

- مثال:

  ```html
  <form method="POST">
      <input type="text" name="username">
      <input type="password" name="password">
  </form>
  ```

---

#### 2. *إرسال البيانات إلى الخادم (HTTP Request)*

- عند الضغط على زر "إرسال"، تُرسل البيانات عبر *طلب HTTP* (عادةً `POST` أو `GET`).
- يتم إرفاق البيانات في `request.POST` (لنماذج POST) أو `request.GET` (لنماذج GET).

---

#### 3. *التحقق من صحة البيانات (Validation)*

- `Django` يفحص البيانات باستخدام *النموذج (`Form/ModelForm`)* المُرتبط:
  - إذا كان النموذج يرث من `forms.Form` أو `forms.ModelForm`.
  - يتم التحقق من:
    - الحقول الإجبارية (required fields).
    - نوع البيانات (مثل نص، رقم، إيميل صحيح).
    - الشروط المخصصة (إن وُجدت، مثل: كلمة سر طويلة بما يكفي).
- مثال:

  ```python
  form = LoginForm(request.POST)  # إنشاء نموذج مع البيانات المرسلة
  if form.is_valid():  # التحقق من الصحة
      # البيانات صالحة
  else:
      # عرض الأخطاء للمستخدم
  ```

---

#### 4. *معالجة البيانات (Processing)*

- إذا كانت البيانات صالحة (`is_valid() == True`):
  - تُنظف البيانات (Cleaning) عبر دالة `clean_<fieldname>()` إن وُجدت.
  - تُحول إلى نموذج Python (مثل قاموس `cleaned_data`).
  - مثال:

    ```python
    username = form.cleaned_data['username']  # جلب البيانات النظيفة
    ```

---

#### 5. *التفاعل مع قاعدة البيانات (Database Interaction)*

- إذا كان النموذج مرتبطًا بـ *Model* (مثل `ModelForm`):
  - تُحفظ البيانات تلقائيًا في قاعدة البيانات عبر `form.save()`.
  - مثال:

    ```python
    new_user = form.save()  # حفظ في قاعدة البيانات
    ```

- إذا كان النموذج عاديًا (`Form`)، يمكنك معالجة البيانات يدويًا:

  ```python
  User.objects.create(username=username, password=password)
  ```

---

#### 6. *الرد للمستخدم (HTTP Response)*

- بعد الحفظ، يُرسل رد للمستخدم، مثل:
  - إعادة توجيه (`redirect`) إلى صفحة أخرى.
  - عرض رسالة نجاح (`success message`).
  - عرض نفس النموذج مع أخطاء إذا فشل التحقق.
- مثال:

  ```python
  from django.shortcuts import redirect
  return redirect('success-page')  # توجيه بعد الحفظ
  ```

---

#### 7. *عرض البيانات في واجهة الإدارة (Admin Interface)*

- إذا كنت تستخدم *Admin Site* في Django:
  1. تسجيل الـ Model في `admin.py`:

      ```python
      from django.contrib import admin
      from .models import Contact
    
      admin.site.register(Contact)
      ```

  2. البيانات المحفوظة تظهر تلقائيًا في لوحة الإدارة (`/admin`).
  3. يمكن للمشرف (`Admin`) تعديلها أو حذفها يدويًا.

---

#### مخطط توضيحي

```sh
المستخدم → النموذج (HTML) → request.POST → Form Validation → cleaned_data → save() → Database → Response
```

---

#### أهم الدوال والطرق المستخدمة

| الوظيفة                  | الوصف                                                                 |
|--------------------------|----------------------------------------------------------------------|
| `form.is_valid()`        | تحقق من صحة البيانات.                                               |
| `form.cleaned_data`      | القاموس الذي يحتوي على البيانات النظيفة بعد التحقق.                 |
| `form.save()`            | يحفظ البيانات في قاعدة البيانات (لـ ModelForm).                    |
| `admin.site.register()`  | تسجيل Model في لوحة الإدارة.                                        |

---

#### مثال كامل (من النموذج إلى الإدارة)

```python
# views.py
from django.shortcuts import render, redirect
from .forms import LoginModelForm

def user_login(request):
    if request.method == 'POST':
        form = LoginModelForm(request.POST)
        if form.is_valid():
            form.save()  # حفظ في قاعدة البيانات
            return redirect('admin:index')  # توجيه إلى لوحة الإدارة
    else:
        form = LoginModelForm()
    return render(request, 'login.html', {'form': form})
```

---

باختصار، `Django` يُبسّط عملية استقبال البيانات من المستخدم وتحويلها إلى سجلات في قاعدة البيانات مع ضمان التحقق من صحتها تلقائيًا. 🛠️

---

## التحكم بشكل لوحة الإدارة

- الانتقال إلى `admin.py`:

لإلغاء قاعدة معينة من الصفحة مثلا `Group`:

```python
from django.contrib.auth.models import Group
admin.site.unregister(Group)
```

لتغيير اسم رأس الصفحة:

```python
admin.site.site_header = "Admin Panel"
```

لتغيير عنوان الصفحة الظاهر في شريط الموقع:

```python
admin.site.site_title = "Admin Panel"
```

هذه التعديلات سيتم إجراءها على باقي التطبيقات لأنها إعدادات عامة بالواجهة بالكامل إلا إن أردنا إنشاء `AdminSite` مخصص لتطبيق واحد دون التأثير على الباقي كالتالي:

الخطوات:

🔸 1. إنشاء `AdminSite` مخصص

- في ملف `admin.py` داخل الـ `app` المطلوب

```python
from django.contrib.admin import AdminSite
from django.contrib import admin
from .models import Contact # اسم قاعدة البيانات

class CustomAppAdminSite(AdminSite):
    site_header = "لوحة تحكم التطبيق X"
    site_title = "عنوان لوحة X"
    index_title = "مرحبًا بك في تطبيق X"

custom_admin_site = CustomAppAdminSite(name="custom_admin")
custom_admin_site.register(Contact) # تسجيل النماذج هنا فقط لهذا الـ admin

```

🔸 2. إعداد `URL` خاص بهذه اللوحة

- في `urls.py` للمشروع الرئيسي

```python
from django.urls import path
from products.admin import custom_admin_site # products اسم التطبيق

urlpatterns = [
    path("custom-admin/", custom_admin_site.urls),  # لوحة مخصصة
    path("admin/", admin.site.urls),               # لوحة Django الأصلية
]
```

✅ النتيجة:

- عند زيارة `/custom-admin/` سترى لوحة تحكم خاصة بالتطبيق المطلوب.

- عند زيارة `/admin/` ستبقى اللوحة الافتراضية كما هي.

يمكنك تخصيص كل لوحة على حدة.

🧠 ملاحظات مهمة:

- لا تأثير على باقي التطبيقات، كل لوحة مستقلة عن الأخرى.
- يمكنك تخصيص الـ `header` والـ `title` لكل لوحة.
- تحتاج تسجيل النماذج مرتين إذا أردت ظهورها في كل لوحتين ، يجب تسجيلها يدويًا لكل `AdminSite`.
- يمكنك إنشاء أكثر من لوحة، واحدة لكل `app` مثلًا.

---

## إضافة مظهر suit للوحة الإدارة

- الانتقال لسطر الأوامر لتنزيل المظهر

إما من `PyPl`:

```sh
pip install django-suit
```

لكنها نسخ مستقرة تفتقر بعض الميزات والإصلاحات لذا يتم تنزيلها من مستودع جيتهاب

إما من `GitHub`:

```sh
pip install https://github.com/darklow
```

ثم اضافتها في `settings.py` في `INSTALL_APPS` في أول القائمة ( المهم أن تكون فوق `django.contrib.abmin` ) بكتابة: `'suit'`

فقط في حالة عدم تحديد شكلها وإبقاء الشكل الافتراضي أما لتحديد شكلها ننتقل إلى صفحة `apps.py` من أي تطبيق لاستيرادها وإنشاء كلاس لها بأي اسم لتحديد شكلها:

```python
from suit.apps import DjangoSuitConfig

class SuitConfig(DjangoSuitConfig):
  layout = 'horizontal' 
```

- `layout`:
  - `horizontal`: أفقي (افتراضي)
  - `vertical`: رأسي

ثم نحذف `suit` طالما حددنا شكلها ونكتب:

```python
products.apps.SuitConfig
```

- `products`: اسم التطبيق
- `apps`: اسم الملف
- `SuitConfig`: اسم الكلاس

---

## إضافة مظهر grappelli للوحة الإدارة

- الانتقال لسطر الأوامر لتنزيل المظهر

```sh
pip install django.grappelli
```

- الانتقال إلى `settings.py` وحذف المظهر السابق واستبداله بـ: `'grappelli'`

- ثم تسجيلها في `urls` المشروع أسفلها:

```python
path('grappelli/', include('grappelli.urls'))
```

---

## تخصيص طريقة عرض النماذج

الانتقال إلى `admin.py` لإنشاء كلاس التخصيص يرث من `admin.ModelAdmin` وتسجيله مع الجدول:

```python
from django.contrib import admin
from .models import Contact

class LoginAdmin(admin.ModelAdmin):
    list_display = ['name', 'email']  # أسماء الحقول التي تريد عرضها
    search_fields = ['user__username', 'ip_address'] # إمكانية البحث حسب هذه الحقول
    list_filter = ['login_time'] # تصفية النتائج حسب حقل الوقت
    list_display_link = ('email',) # عناصر list_display التي توصلنا لسجل الكائن
    list_editable = ('name',) # حقول موجودة في list_display وغير موجودة في list_display_link قابلة لتعديل قيمتها (لا تستخدم علاقات ForeignKey أو ManyToManyField)
    fields = ('message',) # الحقول الظاهرة في السجل

    # لجمع حقلين او اكثر بحقل واحد يتم جمعهم عن طريق دالة:
    def combined_name_and_email(self, obj):
        return f"{obj.name} - {obj.email}"
    combined_topic_and_user.short_description = "Combined name and email" # تخصيص اسم الحقل (الافتراضي: اسم دالة (يعني نفس الاسم بالضبط))

# تسجيل النموذج مع الكلاس المخصص للإدارة
admin.site.register(Contact, LoginAdmin)
```

لاضافة قاعدة بداخل قاعدة ننشئ فئة مخصصة:

```python
class InlineTopic(admin.TabularInline): # أو (admin.StackedInline) لإظهارها بالطول
    model = Topic # اسم الجدول
    extra = 1 # عدد مرات ظهوره (الافتراضي: 3)، وهو قابل للزيادة في لوحة الإدارة

# يتم ادخال الجدول لجدول آخر من خلال خاصية `inline`
class BoardAdmin(admin.ModelAdmin):
    inlines = [InlineTopic]
```

- يمكن وضع العناصر داخل `()` أو `[]` أو `{}` أو بدون أقواس

- لو وضع عنصر واحد داخل `()` يجب إضافة كوما: `('name',)`

---

## تصدير النماذج لملف CSV من لوحة الإدارة

- تنزيل حزمة التصدير:

```sh
pip install django-import-export
```

- إضافة الحزمة إلى `INSTALLED_APPS`: `'import_export'`

- تحديد الجدول المراد تحويله من صفحة المشرف مثلا جدول المواضيع:

```python
from import_export.admin import ImportExportModelAdmin

@admin.register(Topic)
class TopicAdmin(ImportExportModelAdmin):
    pass
```

- طريقة التسجيل بالديكور هي نفسها الطريقة التقليدية الفرق:
  - الديكوريتر أبسط وأوضح إذا كان لديك كلاس واحد فقط للموديل.
  - الطريقة التقليدية مفيدة إذا كنت تريد تسجيل نفس الكلاس لأكثر من موديل (نادر).

- وبهذا سيتم إضافة `IMPORT`, `EXPORT`: لتصدير الجدول مع تحديد نوع الملف

---

## إنشاء مشروع تجريبي

- فكرة المشروع هو إنشاء موقع للمناقشة

- يمكن الوصول إلى المشروع كاملا من [هنا](git@github.com:AHMED-ELBADRYx/Discussion-Board.git)

- الانتقال لمكان المشروع في سطر الأوامر ثم إنشاء البيئة:

```sh
virtualenv venv
```

---

- تفعيل البيئة:

```sh
venv\Scripts\activate
```

---

- تنزيل جانغو:

```sh
pip install django
```

---

- إنشاء مشروع المناقشة:

```sh
django-admin startproject discussion_board
```

---

- الإنتقال للمشروع وإنشاء التطبيق:

```sh
cd discussion_board
python manage.py startapp boards
```

---

- الإنتقال إلى `settings.py` ثم تسجيله في `INSTALLED_APPS` بكتابة:

```python
boards.apps.BoardsConfig
```

---

- الإنتقال إلى `discussion_board\urls.py` واستيراد `include` من `django.urls` وإضافة الرابط في `urlpatterns`:

```python
path("", include("boards.urls"))
```

---

- الانتقال إلى `models.py` لإنشاء الجداول:

  - يتم وضع في القاعدة أربع جداول مهمة:
    - `Board`: لإنشاء الأقسام (خاصة بالأدمن فقط)
    - `Topic`: مواضيع تابعة لقسم معين
    - `Post`: للتفاعل والتعليقات
    - `User`: للمستخدمين

  - جدول `User` محمل جاهز في `INSTALLED_APPS` في `django.contrib.auth` يعني يمكن استيراده مباشرة دون الحاجة لإنشاء حقوله

- الحقول المضافة لكل كلاس:

  - `Board`:
    - `title`: --> `Char`
    - `content`: --> `Char`

    - يمكن إضافة دالة لحساب عدد المشاركات ودالة لتاريخ آخر مشاركة:

      ```python
      @property
      def posts_count(self):
          return sum(topic.posts.count() for topic in self.topics.all())

      @property
      def last_post_date(self):
          last_post = Post.objects.filter(
              topic__board=self
          ).order_by('-created_at').first()
          return last_post.created_at if last_post else None
      ```

  - `Topic`:
    - `title`: --> `Char`
    - `board`: --> `ForeignKey Board`
    - `created_by`: --> `ForeignKey User`
    - `created_at`: --> `DateTime`

  - `Post`:
    - `content`: --> `Text`
    - `topic`: --> `ForeignKey Topic`
    - `created_by`: --> `ForeignKey User`
    - `created_at`: --> `DateTime`

  - `User`:
    - تم استيرادها من `django.contrib.auth`

- العلاقات:

- `Board`: لا يوجد
- `Topic`: `ForeignKey` --> مع كلا من:
--> `Board`
--> `User`
- `Post`: `ForeignKey` --> مع كلا من -->
--> `Topic`
--> `User`
- `User`: لا يوجد

---

- الانتقال إلى سطلر الأوامر لحفظ التغييرات:

```sh
python manage.py makemigrations
python manage.py migrate
```

---

- إنشاء لوحة الإدارة فنكتب بسطر الأوامر:

```sh
python manage.py createsuperuser
```

---

- إضافة الجداول باللوحة في `admin.py`

---

- حفظ التغييرات:

```sh
python manage.py makemigrations
python manage.py migrate
```

---

- إنشاء مجلد `static`

---

- تحميل ملفات `CSS` و `JS` من [هنا](https://getbootstrap.com/docs/5.3/getting-started/download/) ووضعها بمجلد `static`
  - هذه الملفات تضيف تنسيقات جاهزة فيمكن تحديدها على العنصر من خلال اسم الكلاس الخاص بالتنسيق
  - طريقة لربطها بالملف الأساسي تكون بهذا الشكل:

    ```html
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    ```

---

- الانتقال إلى `settings.py` لإضافتها:

```python
STATIC_URL = '/static/'
STATICFILES_DIRS = [BASE_DIR / 'static']
STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
```

- الانتقال لسطر الأوامر لحفظ التغييرات:

```sh
python manage.py collectstatic
```

---

- الانتقال للتطبيق وإنشاء ملف `forms.py` لإنشاء النماذج:

```python
from django import forms
from django.contrib.auth.forms import UserCreationForm # نموذج للمستخدم مدمج في جانغو
from django.contrib.auth.models import User # جدول المستخدمين
from .models import Topic, Post

# نموذج المستخدم
class CustomUserCreationForm(UserCreationForm):
    # تخصيص الايميل
    email = forms.EmailField(
        required=True,
        widget=forms.EmailInput(attrs={
            'class': 'form-control', # للبوتستراب
            'placeholder': 'Enter your email'
        })
    )

    # تحديد الحقول
    class Meta:
        model = User
        fields = ('username', 'email', 'password1', 'password2')
        
        # تخصيص حقل username
        ...

    # تخصيص حقول كلمة المرور
    def __init__(self, *args, **kwargs):
      ...

    # حفظ البيانات
    def save(self, commit=True):
      ...

# نموذج الموضوع الجديد
class NewTopicForm(forms.ModelForm):
    # تحديد وتخصيص حقل العنوان
    class Meta:
        ...

    # التحقق من الصحة (عنوان غير فارغ اكثر من 3 حروف بدون مسافات زائدة)
    def clean_title(self):
        ...

# نموذج المشاركة الجديدة
class NewPostForm(forms.ModelForm):
    # تحديد وتخصيص حقل المحتوى
    class Meta:
        ...
    
    # التحقق من الصحة (محتوى غير فارغ اكثر من 5 حروف بدون مسافات زائدة)
    def clean_title(self):
        ...
```

### *الفرق بين UserCreationForm و User*

| Aspect | UserCreationForm | User |
|--------|------------------|------|
| *النوع* | Form | Model |
| *الغرض* | معالجة إدخال المستخدم | تمثيل البيانات في DB |
| *الاستخدام* | في القوالب والطلبات | في الاستعلامات والعمليات |
| *المحتوى* | حقول + تحقق صحة | حقول + علاقات |
| *التوريث* | يرث من `forms.Form` | يرث من `models.Model` |
| *طريقة الحفظ* | `form.save()` | `user.save()` أو `User.objects.create()` |

مثال يوضح العلاقة بينهما:

```python
from django.contrib.auth.forms import UserCreationForm
from django.contrib.auth.models import User

# استخدام النموذج لإنشاء مستخدم
form = UserCreationForm(data={
    'username': 'john',
    'password1': 'securepassword123',
    'password2': 'securepassword123'
})

if form.is_valid():
    user = form.save()  # هذا ينشئ كائن User في قاعدة البيانات
    print(user.username)  # 'john' - هذا كائن من نموذج User
```

*الخلاصة*:

- `UserCreationForm` هو *الواجهة* لإنشاء مستخدم
- `User` هو *نموذج البيانات* نفسه الذي يتم تخزينه في قاعدة البيانات

---

- الانتقال للتطبيق وإنشاء ملف الروابط `urls.py` لإضافة روابط دوال العرض

---

- إنشاء مجلد `templates` بالخارج لإنشاء ملفات `html`

---

- الانتقال إلى `settings.py` واستيراد نظام التشغيل:

```python
import os
```

- إضافة المجلد إلى `TEMPLATES\DIRS`:

```python
os.path.join(BASE_DIR, 'templates')
```

---

- الانتقال إلى `views` لإضافة دوال العرض

---

- إضافة قائمة اللوحة كصفحة رئيسية في `views`:

  - `board_list(request)` (`FBV`):

    - استعلام القاعدة:
      - `annotate()`: إضافة حقول محسوبة إلى النتائج
      - `total_posts=Count('topics__posts')`: حساب العدد الإجمالي للمشاركات في جميع مواضيع اللوحة
      - `total_topics=Count('topics')`: حساب عدد المواضيع في كل لوحة
      - `.all()`: جلب جميع اللوحات (يمكن حذفه لأنه افتراضي)
      - `.order_by('id')`: ترتيب اللوحات حسب الـ `ID` تصاعدياً

    - التقسيم إلى صفحات:
      - `Paginator(boards, 10)`: إنشاء كائن `Paginator` يعرض 10 لوحات لكل صفحة
      - `request.GET.get('page')`: الحصول على رقم الصفحة المطلوبة من `URL`

    - معالجة الصفحات:
      - `paginator.page(page)`: محاولة الحصول على الصفحة المطلوبة
      - `PageNotAnInteger`: إذا كان رقم الصفحة ليس رقماً (مثل نص)، يعرض الصفحة الأولى
      - `EmptyPage`: إذا كان رقم الصفحة أكبر من العدد الإجمالي، يعرض آخر صفحة

    - العرض

  - `BoardListView(ListView)` (`CBV`):
    - إضافة السمات: `model`, `context_object_name`, `template_name`, `paginate_by`, `ordering`
    - إضافة دالة لتخصيص استعلام قاعدة البيانات
    - إضافة دالة لتوفير هيكل قابل للتوسيع من خلال `Keyword Arguments`

### PAGINATION

- إنشاء ملف لتقسيم الصفحات *_pagination.html*:

    ```html
    {% if items.has_other_pages %}
        
        <!-- روابط الصفحات السابقة-->
        {% if items.has_previous %}
            <a href="?{% if request.GET.sort %}sort={{ request.GET.sort }}&{% endif %}page=1">« الأولى</a>
            <a href="?{% if request.GET.sort %}sort={{ request.GET.sort }}&{% endif %}page={{ items.previous_page_number }}">‹ السابق</a>
        {% endif %}

        <!-- أرقام الصفحات -->
        {% for num in items.paginator.page_range %}

            <!-- الصفحة الحالية (بدون رابط) -->
            {% if items.number == num %}
                {{ num }}
            
            <!-- الصفحات السابقة (مع رابط) -->
            {% elif num > items.number|add:'-3' and num < items.number|add:'3' %}
                <a href="?{% if request.GET.sort %}sort={{ request.GET.sort }}&{% endif %}page={{ num }}">{{ num }}</a>
            {% endif %}
        {% endfor %}

        <!-- الصفحات التالية (مع رابط) -->
        {% if items.has_next %}
            <a href="?{% if request.GET.sort %}sort={{ request.GET.sort }}&{% endif %}page={{ topics.next_page_number }}"></a>
            <a href="?{% if request.GET.sort %}sort={{ request.GET.sort }}&{% endif %}page={{ items.paginator.num_pages }}"></a>
        {% endif %}
    {% endif %}
    ```

- مثلا لنفترض أن لدينا 15 صفحة والصفحة الحالية هي 7 فتكون المخرجات:

```sh
« الأولى ‹ السابق 4 5 6 [7] 8 9 10 التالي › الأخيرة »
```

- *الصفحات المعروضة*: 4, 5, 6, 7, 8, 9, 10 (±3 من الصفحة 7)
- *الصفحة 7*: بدون رابط لأنها الصفحة الحالية
- *روابط التنقل*: الأولى، السابق، التالي، الأخيرة

- المتغيرات المستخدمة

| المتغير | الوصف |
|---------|-------|
| `is_paginated` | هل هناك تقسيم للصفحات؟ |
| `page_obj` | كائن الصفحة الحالية |
| `page_obj.has_previous` | هل توجد صفحة سابقة؟ |
| `page_obj.previous_page_number` | رقم الصفحة السابقة |
| `page_obj.has_next` | هل توجد صفحة تالية؟ |
| `page_obj.next_page_number` | رقم الصفحة التالية |
| `page_obj.number` | رقم الصفحة الحالية |
| `page_obj.paginator.page_range` | قائمة بأرقام جميع الصفحات |
| `page_obj.paginator.num_pages` | عدد الصفحات الإجمالي |

- عرض القائمة في هيكل القالب:

  - يمكن عرض عدد المواضيع والمشاركات الموجودة في `views` من خلال متغير حلقة قيمة قاموس البيانات:

  ```html
  {{ board.total_posts }}
  {{ board.total_topics }}
  ```

  - عرض تاريخ آخر بوست الموجود في دالة `models`:

  ```html
  {% if board.last_post_date %}
      {{ board.last_post_date|date:"Y-m-d H:i" }}
  ```

  - إضافة ملف `_pagination.html` لعرض روابط التصفح بين الصفحات (`pagination`)

    ```html
    {% include "boards/includes/_pagination.html" with items=page_obj %}
    ```

---

### كيفية إنشاء الكائن من خلال سطر الأوامر

- مثلا إنشاء موضوع من أحد عناصر اللوحة التي يتم إنشاءها بلوحة الإدارة مثل `Web programming`:

```sh
py manage.py shell
from boards.models import Board
board = Board(title='Web programming', content='This board will speak about all web programming')
board.save()
board.id  # الاستعلام عن معرف
board.title  # الاستعلام عن حقل عنوان الطائن
Board.objects.all()  # الاستعلام عن كل الكائنات
exit()  # خروج
```

---

### كيفية إنشاء عدد من الكائنات من خلال سطر الأوامر

- مثلا إنشاء 100 موضوع من خلال سطر الأوامر:

```sh
python manage.py shell
from django.contrib.auth.models import User
from boards.models import Board, Topic
import random
from django.utils import timezone

# الحصول على المستخدمين واللوحات المتاحة
users = User.objects.all()
boards = Board.objects.all()

if not users.exists():
    print("لا يوجد مستخدمين. يرجى إنشاء مستخدمين أولاً.")
elif not boards.exists():
    print("لا يوجد لوحات. يرجى إنشاء لوحات أولاً.")
else:
    # إنشاء 100 topic عشوائي
    for i in range(100):
        user = random.choice(users)
        board = random.choice(boards)
        
        topic = Topic.objects.create(
            title=f"Topic التجريبي {i+1} - {board.title}",
            board=board,
            created_by=user,
            created_at=timezone.now(),
            views=random.randint(0, 1000)
        )
        print(f"تم إنشاء topic: {topic.title}")
    
    print("تم إنشاء 100 topic بنجاح!")

# الخروج من shell بعد الانتهاء
exit()
```

---

- إضافة تفاصيل اللوحة في `views`:

  - `board_detail(request, board_id)` (`FBV`):

    - `get_object_or_404()`: جلب الكائن

    - `request.GET.get('sort', 'newest')`: جلب معامل الفرز من `URL` (الافتراضي `'newest'`)

    - تحسين أداء الجلب:
      - `select_related`: علاقة ManyToOne
      - `prefetch_related`: علاقة ManyToMany

    - تطبيق الفرز:
      - `newest`: `-created_at` (الأحدث أولاً)
      - `oldest`: `created_at` (الأقدم أولاً)

    - تقسيم ومعالجة الصفحات:

    - فتكون البيانات الممررة للقالب:

      - `board`: كائن اللوحة
      - `topics`: كائن الصفحة الحالية من المواضيع
      - `sort_param`: معامل الفرز الحالي للاستخدام في القالب

- عرض التفاصيل في هيكل القالب:

  - التحقق من المستخدم:

  ```html
  {% if user.is_authenticated %}
      
      <a href="{% url 'new_topic' board.id %}">New Topic</a> <!-- عرض رابط إنشاء موضوع جديد للمستخدمين المسجلين -->

  {% else %}
      
      <a href="{% url 'login' %}?next={{ request.path }}">Login to Post</a> <!-- عرض رابط تسجيل الدخول للزوار -->
      <!-- `?next={{ request.path }}`: يحفظ الصفحة الحالية لإعادة التوجيه بعد التسجيل -->

  {% endif %}
  ```

  - عرض محتوى وصف اللوحة إذا كان موجوداً:

  ```html
  {% if board.content %}
      {{ board.content|default:"No content available" }}
  {% endif %}
  ```

  - عرض العدد الإجمالي للمواضيع في اللوحة (ليس فقط في الصفحة الحالية):

  ```html
  Topics: {{ topics.paginator.count }}
  ```

  - خيارات الفرز:

  ```html
  <input type="radio" name="sort" id="newest" value="newest" autocomplete="off"
  {% if not request.GET.sort or request.GET.sort == 'newest' %}checked{% endif %}>
  <label for="newest">Newest</label>

  <input type="radio" name="sort" id="oldest" value="oldest" autocomplete="off"
  {% if request.GET.sort == 'oldest' %}checked{% endif %}>
  <label for="oldest">Oldest</label>
  ```

  - بحالة وجود مواضيع:

  ```html
  {% if topics %}

      <!-- أيقونات حسب حالة الموضوع -->
      {% if request.GET.sort == 'oldest' %}
          <i></i>
      {% else %}
          <i></i>
      {% endif %}

      <!-- عرض قائمة المواضيع -->
      {% for topic in topics %}
          <a href="{% url 'topic_detail' board.id topic.id %}"></a>
          
          <!-- أيقونات حسب شعبية الموضوع -->
          {% if topic.posts.count > 10 %}
              <i title="Hot topic"></i>
          {% elif topic.posts.count > 5 %}
              <i title="Popular topic"></i>
          {% else %}
              <i title="Normal topic"></i>
          {% endif %}

          <!-- الانتقال لصفحة تفاصيل الموضوع من خلال عنوانه -->
          <a href="{% url 'topic_detail' board.id topic.id %}">{{ topic.title }}</a>
          
          <!-- علامة "New" للمواضيع بدون مشاركات -->
          {% if topic.posts.count == 0 %}
            New
          {% endif %}
          
          <!-- إحصائيات الموضوع -->
          {{ topic.posts.count }}
          {{ topic.views }}
          {{ topic.created_by.username }}</
          
          <!-- تاريخ الإنشاء -->
          <small
          title="{{ topic.created_at }}">
              {{ topic.created_at|date:"M j, Y" }} <!-- التاريخ: Dec 15, 2023 -->
              <br>
              {{ topic.created_at|date:"g:i A" }} <!-- الوقت: 2:30 PM -->
          </small>
      {% endfor %}
  ```

  - إضافة ملف `_pagination.html` لتقسيم إلى صفحات (`Pagination`):

    ```html
    {% include "boards/includes/_pagination.html" with items=topics %}
    ```

  - بحالة عدم وجود مواضيع

  ```html
  {% else %}
      {% if user.is_authenticated %}
          
          <!-- عرض رسالة تشجيعية لإنشاء أول موضوع للمسجلين -->
          <a href="{% url 'new_topic' board.id %}">Create First Topic</a>
      
      {% else %}

          <!-- نقل الغير مسجلين لصفحة تسجيل الدخول -->
          <a href="{% url 'login' %}?next={{ request.path }}">Login to Create Topic</a>
      {% endif %}
  {% endif %}
  ```

---

- إضافة موضوع جديد في `views`:

  - `new_topic(request, board_id)` (`FBV`):

    - `@login_required`: تقييد الوصول إلى المستخدمين المسجلين فقط

    - جلب اللوحة

    - إنشاء نموذج مع البيانات المرسلة من نموذج الموضوع الجديد في `forms` (مع التأكد من أن الطلب `POST`)

      - التحقق من صحة النموذج

        - `try: with transaction.atomic()`: معاملة ذرية (`Atomic Transaction`) لمنع إنشاء موضوع غير مكتمل إذا فشلت بعض العمليات أما إذا كان مكتملا فيتم:
          - `form.save(commit=False)`: إنشاء كائن `Topic` من النموذج دون حفظه في قاعدة البيانات
          - `topic.board = board`: ربط الموضوع باللوحة الحالية
          - `topic.created_by = request.user`: تعيين المستخدم الحالي كمنشئ الموضوع
          - `topic.save()`: حفظ الموضوع النهائي في قاعدة البيانات

          - رسالة النجاع وإعادة التوجيه إلى صفحة تفاصيل الموضوع الجديد لإضافة التعليقات

        - معالجة الأخطاء لو كان الموضوع غير مكتمل

      - معالجة النموذج غير الصالح

    - معالجة طلب `GET` (عرض النموذج)

- إنشاء ملف لعرض الأخطاء وملف لعرض حقول النموذج

- الملف الأول: عرض *الأخطاء العامة (_form_errors.html)*

  - `form.non_field_errors` = الأخطاء التي لا تخص حقل معين، بل النموذج ككل.

  - إذا كانت هناك أخطاء:
    - يتم المرور على كل خطأ باستخدام `{% for error in form.non_field_errors %}` ويُعرض كنص عادي.

### WIDGET TWEAKS

- تنزيل حزمة `widget tweaks` لتجعل تخصيص شكل الحقول (`attributes`) في القوالب أسهل وأسرع وأكثر مرونة بإضافة الكلاسات الخاصة بـ `Bootstrap` مثل `form-control` فننتقل لسطر الأوامر (يجب أن تكون البيئة الافتراضية مفعلة):

```sh
pip3 install django-widget-tweaks
```

- إضافتها إلى `settings.py\INSTALLED_APPS`: `'widget_tweaks'`

- الملف الثاني: عرض *حقول النموذج مع التحقق (_form_fields.html)*

1. *تحميل مكتبة widget_tweaks*

2. *التكرار على الحقول*

3. *عرض الاسم (Label)*

   - يعرض اسم الحقل (`field.label`)
   - إذا الحقل مطلوب (`required`): يضع نجمة `*`

4. *التعامل مع الأخطاء*

   - إذا كان عند الحقل أخطاء:

     - يضاف له كلاس `Bootstrap` *`is-invalid`* (لون أحمر)
     - يعرض الأخطاء تحت الحقل داخل `invalid-feedback`

5. *لو الحقل صحيح أو فارغ*

   - إذا *النموذج تم إرساله (`is_bound`)* والحقل يحتوي قيمة صحيحة: يضاف كلاس *`is-valid`* (لون أخضر).
   - إذا الحقل لم يُملأ أو النموذج لسه ما أُرسل: يبقى بكلاس عادي *`form-control`*

6. *عرض المساعدة (help_text)*

   - إذا الحقل يحتوي *نص مساعدة* (`help_text`) ولم يكن فيه خطأ: يعرض المساعدة أسفل الحقل.

- عرض الموضوع بهيكل القالب:

  - عرض الحقول ومعالجة الأخطاء:

    ```html
    <form method="post" novalidate>
        {% csrf_token %}
        
        {% include "includes/_form_errors.html" %}
        {% include "includes/_form_fields.html" %}
        
        <button type="submit" >Add Topic</button>
    </form>
    ```

  - زر العودة لصفحة التفاصيل

    ```html
    <a href="{% url 'board_detail' board.id %}">Back to Board</a>
    ```

  - عرض عدد المواضيع:

    ```html
    Topics: {{ topics.paginator.count }}
    ```

  - بحالة وجود مواضيع:

    ```html
    {% if topics %}
        
    <!-- عرض قائمة المواضيع -->
        {% for topic in topics %}
            <a href="{% url 'topic_detail' board.id topic.id %}">{{ topic.title }}</a> <!-- الانتقال لصفحة تفاصيل الموضوع من خلال عنوانه -->

            <!-- إحصائيات الموضوع -->
            {{ topic.posts.count }}
            {{ topic.created_by.username }}
            {{ topic.created_at|date:"M j, Y" }}
            {{ topic.views }}
    ```

    - إضافة ملف `_pagination.html` لتقسيم الصفحات (`Pagination`):

    ```html
    {% include "boards/includes/_pagination.html" with items=topics %}
    ```

---

- إضافة تفاصيل الموضوع لإضافة التعليقات في `views`:
  
  - `topic_detail(request, board_id, topic_id)` (`FBV`):

    - جلب الموضوع مع التحسينات:
      - `get_object_or_404()`: التأكد من وجود الموضوع أو إرجاع 404
        - `select_related('board', 'created_by')`: تحسين الأداء بجذب البيانات المرتبطة (لوحة الموضوع ومنشئه)
        - `board__pk=board_id`: التأكد أن الموضوع ينتمي للوحة الصحيحة

    - زيادة عداد المشاهدات ومنع تكرار عد المشاهدات من نفس المستخدم في نفس الجلسة:
      - `F('views') + 1`: زيادة آمنة بدون مشاكل التزامن
      - `refresh_from_db()`: تحديث البيانات من قاعدة البيانات
      - `request.session[session_key] = True`: تأكيد أن المستخدم قد شاهد الموضوع

    - جلب المشاركات مع التحسين

    - التقسيم إلى صفحات (`Pagination`)

    - معالجة إنشاء مشاركة جديدة (`POST Request`):
      - التحقق من تسجيل الدخول
      - التحقق من صحة النموذج
      - حفظ المشاركة بشكل آمن (معاملة ذرية)
      - إعادة التوجيه مع رسائل نجاح/خطأ

    - معالجة طلب `GET` (عرض النموذج)

    - العرض النهائي

- عرض تفاصيل الموضوع بهيكل القالب:

  - عرض صاحب الموضوع وتاريخ الإنشاء:

  ```html
  {{ topic.created_by.username }}
  {{ topic.created_at|date:"Y-m-d H:i" }}
  ```

  - عرض نموذج المشاركة للمستخدمين المسجلين

  ```html
  {% if user.is_authenticated %}
      <form method="post" novalidate>
          {% csrf_token %}
          
          {% include "includes/_form_errors.html" %}
          {% include "includes/_form_fields.html" %}
          
          <button type="submit">Add Post</button>
      </form>
  ```
  
  - عرض رابط التسجيل للغير مسجلين مع حفظ الصفحة للعودة إليها بعد التسجيل

  ```html
  {% else %}
      <a href="{% url 'login' %}?next={{ request.path }}">Login to Post</a>
  {% endif %}
  ```

  - زر العودة لصفحة المواضيع

  ```html
  <a href="{% url 'board_detail' topic.board.pk %}">Back to Board</a>
  ```

  - عرض المشاركات للمستخدمين المسجلين

  ```html
  {% if user.is_authenticated %}
      {% for post in posts %}
          {{ post.created_by.username }}
          {{ post.created_at|date:"Y-m-d H:i" }}
          
          <!-- عرض تاريخ التعديل -->
          {% if post.updated_by %}
            (edited at {{ post.updated_at|date:"Y-m-d H:i" }})
          {% endif %}

          <!-- عرض زر التعديل لصاحب المشاركة -->
          {% if user == post.created_by %}
              <a href="{% url 'post_edit' post.pk %}">Edit</a>
          {% endif %}

          <!-- عرض محتوى المشاركة -->
          {{ post.content }}
  ```

  - إضافة ملف تقسيم الصفحة:

  ```html
  {% include "boards/includes/_pagination.html" with items=posts %}
  ```

  - عرض زر التسجيل لغير المسجلين

  ```html
  {% else %}
      <a href="{% url 'login' %}?next={{ request.path }}">login</a>
  {% endif %}
  ```

---

- إضافة تعديل التعليق في `views`

  - `PostUpdateView(LoginRequiredMixin, UserPassesTestMixin, UpdateView)` (`CBV`):

    - الوراثة:
      - `LoginRequiredMixin`: يتطلب تسجيل الدخول
      - `UserPassesTestMixin`: يتحقق من صلاحيات المستخدم
      - `UpdateView`: عرض مخصص للتعديل

    - إضافة السمات (`Attributes`): `model`, `form_class`, `template_name`, `context_object_name`

    - التحقق إذا كان المستخدم الحالي هو منشئ المشاركة

    - معالجة عدم وجود الصلاحية بإضافة رسالة خطأ إذا لم يكن لدى المستخدم الصلاحية

    - تحديد رابط النجاح

    - معالجة النموذج الصالح
      - `form.instance.updated_by = self.request.user`: تعيين المستخدم الحالي كمعدل المشاركة
      - `messages.success()`: إضافة رسالة نجاح
      - `super().form_valid(form)`: الاستمرار في المعالجة الافتراضية

- عرض تعديل التعليق بهيكل القالب:

  - عرض عنوان المشاركة الأساسي كرابط:

  ```html
  <a href="{% url 'topic_detail' post.topic.board.id post.topic.id %}">{{ post.topic.title }}</a>
  ```

  - إضافة نموذج الحقل لتعديله:

  ```html
  <form method="post" novalidate>
      {% csrf_token %}
      
      {% include "includes/_form_errors.html" %}
      {% include "includes/_form_fields.html" %}
      
      <button type="submit">Update Post</button>
      
      <a href="{% url 'topic_detail' post.topic.board.id post.topic.id %}">Cancel</a>
  </form>
  ```

---

- إنشاء تطبيق للحساب:

```sh
django-admin startapp accounts
```

---

- تعريفه في `settings.py\INSTALLED_APPS`:

```sh
'accounts.apps.AccountsConfig'
```

---

- إضافته إلى `discusssion_board\urls.py`:

```python
path("accounts/", include("accounts.urls"))
```

---

- الانتقال للتطبيق وإنشاء ملف الروابط `urls.py` والانتقال إليه لإضافة روابط دوال العرض

---

- إنشاء `forms.py` لوضع كلاسين:
  - `CustomUserCreationForm`
  - `UserUpdateForm`

---

- الانتقال إلى `views` لإنشاء دوال العرض:

---

- إنشاء دالة تسجيل الدخول لمستخدم سابق:

  - `login_view(request)` (`FBV`):
  
    - `@never_cache`: يمنع المتصفح من التخزين فيضمن أن المستخدم سيحصل دائمًا على صفحة تسجيل دخول جديدة عند الزيارة

    - تعريف الدالة والتحقق من المصادقة

      - إذا كان المستخدم مسجلاً دخوله بالفعل، يعرض رسالة ويوجهه مباشرة إلى لوحة القوائم

      - تحديد الصفحة التالية من خلال الحصول على معامل `next` من `URL` أو بيانات النموذج أو يستخدم `'board_list'` كصفحة افتراضية إذا لم يكن موجودًا

      - معالجة طلب `POST` (تسجيل الدخول)
        - إذا كان النموذج صالحًا، يسجل دخول المستخدم
        - `update_session_auth_hash` يحافظ على جلسة المستخدم عند تغيير كلمة المرور
        - يعرض رسالة ترحيب ويوجه إلى الصفحة المطلوبة
        - معالجة الأخطاء بإعادة عرض النموذج مع رسالة خطأ

      - معالجة طلب `GET` (عرض صفحة التسجيل)

- إنشاء هيكل القالب

```html
<form method="post" novalidate>
    {% csrf_token %}
    
    <!-- حمل قيمة الصفحة التي يجب توجيه المستخدم إليها بعد تسجيل الدخول الناجح بدلا من الصفحة الافتراضية -->
    <input type="hidden" name="next" value="{{ next }}">

    {% include "includes/_form_errors.html" %}
    {% include "includes/_form_fields.html" %}

    <button type="submit">Login</button>
</form>

<!-- إضافة خيار رابط صفحة التسجيل لمستخدم جديد -->
<a href="{% url 'register' %}">Register here</a>
```

---

- إنشاء دالة التسجيل لمستخدم جديد:

  - `register_view(request)` (`FBV`):

    - إضافة ديكوريتور `@never_cache`

    - تعريف الدالة والتحقق من المصادقة

    - معالجة طلب `POST` (تسجيل جديد) باستخدام نموذج `CustomUserCreationForm` المخصص

      - معالجة بعد التسجيل الناجح
        - إذا كان الحساب نشطًا: يسجل دخول المستخدم تلقائيًا ويعرض رسالة ترحيب
        - إذا كان الحساب غير نشط: يعرض رسالة تفيد بانتظار التفعيل (مفيد لنظام الموافقة على الحسابات)
        - في كلا الحالتين، يتم التوجيه إلى `board_list`

      - معالجة الأخطاء

    - معالجة طلب `GET` (عرض صفحة التسجيل)

- إنشاء هيكل القالب:

```html
<form method="post" novalidate>
    {% csrf_token %}
    
    {% include "includes/_form_errors.html" %}
    {% include "includes/_form_fields.html" %}
    
    <button type="submit">Create Account</button>
</form>

<!-- إضافة خيار رابط صفحة تسجيل الدخول لمستخدم موجود -->
<a href="{% url 'login' %}">Login here</a>
```

---

- إنشاء دالة تسجيل الخروج:

  - `logout_view(request)` (`FBV`):
  
    - الديكورات (`Decorators`):
      - `@login_required`: تطلب أن يكون المستخدم مسجلاً دخولاً للوصول إلى هذه الصفحة
      - `@require_http_methods(["GET", "POST"])`: تقصر الطرق المسموحة على `GET` و `POST` فقط
      - `@never_cache`: تمنع المتصفح من تخزين هذه الصفحة في الكاش

    - منطق التسجيل الخروج:
      - يتم تنفيذ تسجيل الخروج فقط عند استلام طلب `POST`
      - حفظ اسم المستخدم: يتم حفظ الاسم قبل تسجيل الخروج لأن `request.user` يصبح مجهولاً بعد `logout()`
      - إضافة رسالة تأكيد للمستخدم
      - إعادة توجيه المستخدم إلى صفحة تسجيل الدخول

    - عند طلب `GET`، يتم عرض قالب تأكيد تسجيل الخروج (`logout.html`)

- عرض زر تسجيل الخروج بأي مكان مثلا في `NAVBAR`:

```html
<a href="{% url 'logout' %}">Logout</a>
```

- إنشاء هيكل القالب:

```html
<form method="post" action="{% url 'logout' %}">
    {% csrf_token %}
    <button type="submit">Yes, Logout</button>
</form>

<a href="{% url 'board_list' %}">Cancel</a>
```

---

- إضافة رابط تغيير لتغيير الباسوورد ورابط التأكيد المدمجين بصفحة الروابط

- عرض زر تغيير الباسوورد بأي مكان مثلا في `NAVBAR`:

```html
<a href="{% url 'password_change' %}">Change Password</a>
```

- إنشاء هيكل القالب لصفحة تغببر الباسوورد:

```html
<form method="post" novalidate>
    {% csrf_token %}
    
    {% include "includes/_form_errors.html" %}
    {% include "includes/_form_fields.html" %}

    <button type="submit" >Change Password</button>

    <a href="{% url 'board_list' %}">Cancel</a>
```

- إنشاء هيكل القالب لصفحة التأكيد:

```html
<h5>Password Changed Successfully!</h5>
<a href="{% url 'board_list' %}">Go to Home</a>
```

---

- إنشاء كلاس عرض تغيير اسم المستخدم والإيميل:

  - `UserUpdateView(LoginRequiredMixin, SuccessMessageMixin, UpdateView)` (`CBV`):

    - الوراثة (`Inheritance`):
      - `LoginRequiredMixin`: يضمن أن المستخدم يجب أن يكون مسجلاً دخولاً للوصول إلى هذه الصفحة
      - `SuccessMessageMixin`: يضيف إمكانية عرض رسائل نجاح بعد العملية
      - `UpdateView`: View مخصصة لعرض وتحديث بيانات نموذج معين (Model)

    - السمات (`Attributes`): `model`, `form_class`, `template_name`, `success_message`, `success_url`

    - الدالة المخصصة (`get_object`):
      - تجاوز الدالة الافتراضية: بدلاً من الحصول على الكائن من خلال المعامل في `URL`
      - إرجاع المستخدم الحالي: تُرجع كائن المستخدم المسجل دخوله حالياً
      - الأمان: يضمن أن كل مستخدم يمكنه فقط تحديث بياناته الشخصية

- عرض زر تغيير البروفايل بأي مكان مثلا في `NAVBAR`:

```html
<a href="{% url 'profile_update' %}">Edit Profile</a>
```

- إنشاء هيكل القالب:

```html
<form method="post" novalidate>
    {% csrf_token %}
    
    {% include "includes/_form_errors.html" %}
    {% include "includes/_form_fields.html" %}

    <button type="submit">Update Profile</button>
    <a href="{% url 'board_list' %}">Cancel</a>
</form>
```

---

## API

- ما هي واجهة برمجة التطبيقات (`API`)؟

  - `API` هو اختصار لـ `Application Programming Interface`، أي: واجهة برمجة التطبيقات.
  - بعبارة بسيطة: هو باب أو وسيط يسمح لتطبيقٍ ما أو موقعٍ ما أن يتواصل مع تطبيق أو موقع آخر، للحصول على بيانات أو تنفيذ وظائف محددة، دون الحاجة لمعرفة كيف بُني ذلك التطبيق من الداخل.

- الفرق بين واجهة `HTML` وواجهة `API`

  - عندما نزور موقعًا عاديًا، السيرفر يرسل لنا صفحة `HTML` ليراها المستخدم في المتصفح.

  - أما عند زيارة رابط `API`، السيرفر لا يعطينا صفحة، بل يعطينا بيانات خام (عادةً بصيغة `JSON`) يمكن لأي برنامج أو تطبيق استهلاكها وإعادة عرضها بالشكل الذي يريده.

- مثلا

  - إذا كان عندك موقع يعرض مقالات:

    - صفحة الموقع: تعرض المقالات بشكل مرتب (`HTML` + `CSS`).

    - رابط الـ `API`: يرجع نفس المقالات لكن في صيغة بيانات منظمة مثل:

    ```json
    [
    {"id": 1, "title": "أول مقالة", "content": "هذا نص تجريبي"},
    {"id": 2, "title": "ثاني مقالة", "content": "مقال آخر"}
    ]
    ```

    - بهذه الطريقة، يمكن لتطبيق موبايل أو موقع آخر أن يستهلك نفس البيانات ويعرضها بتصميمه الخاص.

- الفرق بين الـ `API` والاستضافة

  - الاستضافة: مكان تخزن فيه موقعك أو تطبيقك ليكون متاحًا على الإنترنت (مثل الشقة التي فيها كل ملفاتك).

  - الـ `API`: واجهة أو خدمة داخل الموقع المستضاف، تسمح لتطبيقات أخرى أن تأخذ بياناتك أو تستعمل وظائفك بطريقة منظمة (مثل باب خدمة خاص للمطعم يسمح لتطبيقات الدليفري بطلب الطعام).

- لماذا نستخدم `API`؟

  1. إعادة استخدام البيانات: بدل أن يكرر كل تطبيق نفس الجهد، يستعمل البيانات من مصدر واحد.

  2. التكامل بين الأنظمة: مثل ربط موقعك مع خدمة دفع إلكتروني أو خدمة طقس.

  3. تعدد الواجهات: يمكن لموقعك أن يُستهلك من متصفح، أو من تطبيق موبايل، أو حتى من برامج أخرى، وكلها تعتمد على نفس الـ `API`.

- الخلاصة

  - الـ `API` ليس استضافة، وليس مجرد تضمين (`Embedding`) لصفحة أو فيديو.
هو أشبه بـ جسر للتواصل بين التطبيقات:

  - بدلاً من أن تعرض صفحة `HTML` عادية للمستخدم، تعرض بيانات خام (مثل `JSON`).

  - هذه البيانات يمكن لمواقع أو تطبيقات أخرى أن تستهلكها وتعيد عرضها أو تبني عليها خدمات جديدة.

---

## تطبيق API على المشروع

- المشروع سيلعب دور `BACK-END` الذي ينشئ البيانات ويستقبلها `FORNT-END` لمشروع آخر

---

- تنزيل `REST FRAMEWORK`:

```sh
pip3 install djangorestframework
```

---

- إضافتها إلى `INSTALLED_APPS` في الإعدادات

```python
'rest_framework`
```

---

- بدلا من إرجاع البيانات على شكل `TEMPLATE` يتم إرجاعها على شكل `JSON` مثلا لإرجاع بيانات دالة `boatd_list`:

```python
from django.http import JsonResponse

def board_list(request):
    ...
    data = {
        "Results": [
            {
                "pk": board.pk,
                "title": board.title,
                "content": board.content,
                "total_posts": board.total_posts,
                "total_topics": board.total_topics,
            }
            for board in boards
        ],
        "num_pages": boards.paginator.num_pages,
        "current_page": boards.number,
    }
    return JsonResponse(data)
```

---

- يمكن عرض البيانات إما من خلال الواجهة أو سطر الأوامر (يجب أن يكون السيرفر مفعل لذا نستخدم تيرمينال جديد):

```sh
curl http://127.0.0.1:8000
```

---

- استقبال البيانات من خلال مشروع `FORNT-END`

---

- تنزيل حزمة استقبال البيانات:

```sh
pip3 install requests
```

---

- استقبال البيانات من خلال دالة العرض:

```python
from django.shortcuts import render
import requests

def board_list(request):
    
    # تخزين رابط البيانات
    backend_url = "http://127.0.0.1:8000"

    # تخصيص نوع البيانات (اختياري)
    headers = {"Context-Type": "application/json"}

    # استقبال البيانات
    response = requests.get(backend_url, headers=headers)

    # تحديد شكل البيانات
    boards = response.json()

    # عرض الصفحة
    return render(request, "boards/board_list.html", {"boards": boards["Results"]})
```

---

- تفعيل السيرفر على منفذ مختلف:

```sh
python manage.py runserver 5000
```

---

## عرض حالة الطقس من خلال API

---

- إنشاء التطبيق:

```sh
py manage.py startapp weather_api
```

---

- إضافته لإعدادات التطبيق

```python
'weather_api.apps.WeatherApiConfig'
```

---

- البحث عن احداثيات الدولة من خلال `OPEN-METEO` مثلا للبحث عن إحداثيات البرازيل:

```sh
https://geocoding-api.open-meteo.com/v1/search?name=Brazil
```

---

- نسخ قيمة خط الطول ودائرة العرض: `latitude`, `longitiot` وإضافتها لرابط `API`:

```sh
https://api.open-meteo.com/v1/forecast?latitude=-10.0&longitude=-55.0&current_weather=true
```

---

- إنشاء دالة العرض:

```python
def weather(request):

    # تحديد رابط API لجلب الطقس الحالي لطوكيو
    api_url = "https://api.open-meteo.com/v1/forecast?latitude=35.6895&longitude=139.6917&current_weather=true"
    
    context = {}

    # إرسال طلب GET للرابط باستخدام مكتبة requests
    response = requests.get(api_url)

    # إذا نجح الطلب
    if response.status_code == 200:
        
        # يحول الاستجابة إلى JSON
        data = response.json()

        # يأخذ بيانات الطقس الحالية من المفتاح current_weather
        weather = data.get('current_weather', {})
        if weather:  # نتأكد أن فيه بيانات
            # تحويل weathercode إلى وصف نصي
            weathercode_map = {
                0: "Clear sky",
                1: "Mainly clear",
                2: "Partly cloudy",
                3: "Overcast",
                45: "Fog",
                48: "Depositing rime fog",
                51: "Light drizzle",
                53: "Moderate drizzle",
                55: "Dense drizzle",
                61: "Slight rain",
                63: "Moderate rain",
                65: "Heavy rain",
                80: "Rain showers",
                95: "Thunderstorm",
            }

            # يحصل على قيمة الكود من البيانات، ثم يضيف الوصف النصي إلى القاموس تحت المفتاح "condition"
            code = weather.get("weathercode")

            # يضيف بيانات الطقس إلى السياق (context)
            weather["condition"] = weathercode_map.get(code, "Unknown")
            context['weather'] = weather
    return render(request, 'weather_api/weather.html', context)
```

- إنشاء القالب:

```html
{% if weather %}
    Temperature: {{ weather.temperature }} °C
    Windspeed: {{ weather.windspeed }} km/h
    Wind Direction: {{ weather.winddirection }}°
    Condition: {{ weather.condition }}
    Time: {{ weather.time }}
{% else %}
     Weather data is currently unavailable.
{% endif %}
```

---

- أو يمكن استخدام رابط `API` آخر لتحديد اسم أي دولة مباشرة بدون الإحداثيات:

```python
def weather(request):
    api_url = "http://api.openweathermap.org./data/2.5/weather?appid=0c42f7f6b53b244c78a418f4f181282a&q="
    
    # تحديد دولة الكويت وإضافتها لنهاية الرابط
    city_name = "Kuwait"
    url = api_url + city_name

    response = requests.get(url)
    content = response.json()

    # نقل بيانات الطقس الخام من الرابط الأصلي
    city_weather = {
        'city': city_name,
        'temperature': content['main']['temp'],
        'description': content['weather'][0]['description'],
        'icon': content['weather'][0]['icon']
    }

    return render(request, 'weather_api/weather.html', city_weather)
```

- عرض البيانات في القالب:

```html
<img src="http://openweathermap.org/img/w/{{ icon }}.png" alt="Image">
{{ city }}
{{ temperature }}° F
{{description }}
```

---

- لجعل المستخدم يحدد الدولة بنفسه:
  - ننشئ جدول في `models` به حقل لإسم الدولة وتنفيذ أوامر الترحيل
  - ننشئ نموذج في `forms` نخزن من خلاله بيانات المستخدم في جدول `models`
  - معالجة البيانات بدالة العرض فتصبح بهذا الشكل:

  ```python
  from django.shortcuts import render
  import requests
  from .models import City
  from .forms import CityForm


  def weather(request):
      url = 'http://api.openweathermap.org./data/2.5/weather?appid=0c42f7f6b53b244c78a418f4f181282a&q='

      if request.method == 'POST':
          form = CityForm(request.POST)
          form.save()

      form = CityForm()
      cities = City.objects.all()
      weather_data = []
      
      if cities:
          for city in cities:
              data_url = url + str(city)
              response = requests.get(data_url).json()
              city_weather = {
                  'city': city.name,
                  'temperature': response['main']['temp'],
                  'description': response['weather'][0]['description'],
                  'icon': response['weather'][0]['icon'],
              }
              weather_data.append(city_weather)

      return render(request, 'weather_api/weather.html', {'weather_data': weather_data, 'form': form})
  ```

  - عرض القالب:
  
  ```html
  <form method="POST">
      {% csrf_token %}
      {{ form.name }}
      <button type="submit">Add City</button>
  </form>

  {% for city_weather in weather_data %}
      <img src="http://openweathermap.org/img/w/{{ city_weather.icon }}.png" alt="Image">
      {{ city_weather.city }}
      {{ city_weather.temperature }}° F
      {{ city_weather.description }}
  {% endfor %}
  ```

---

## نهاية الملف
