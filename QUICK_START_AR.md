# البدء السريع - نظام إدارة المطعم

## 🚀 خطوات سريعة للبدء (5 دقائق)

### 1️⃣ قاعدة البيانات (دقيقة واحدة)

افتح MySQL وأنشئ القاعدة:

```sql
CREATE DATABASE restaurant_db;
```

### 2️⃣ إعداد Laravel (دقيقتان)

```bash
cd backend
composer install
cp .env.example .env
```

عدل ملف `.env`:

```env
DB_DATABASE=restaurant_db
DB_USERNAME=root
DB_PASSWORD=كلمة_المرور_هنا
```

ثم:

```bash
php artisan key:generate
php artisan migrate
```

### 3️⃣ تشغيل النظام (دقيقة واحدة)

```bash
php artisan serve
```

سيعمل على: `http://localhost:8000`

### 4️⃣ فتح الواجهة (دقيقة واحدة)

افتح ملف `index.html` في المتصفح

**أو استخدم خادم بسيط:**

```bash
python3 -m http.server 5000
```

ثم افتح: `http://localhost:5000`

---

## ✅ جاهز!

الآن يمكنك:
- إضافة أصناف للمخزون
- إدارة الموظفين
- تسجيل الموردين
- تتبع الإيرادات والمصروفات
- استخدام نقطة البيع

---

## ⚠️ مشكلة؟

### لا يتصل Frontend بـ Backend؟

تأكد من أن `js/api.js` يحتوي على:

```javascript
const API_BASE_URL = 'http://localhost:8000/api/v1';
```

### خطأ في الاتصال بقاعدة البيانات؟

- تحقق من ملف `.env`
- تأكد من تشغيل MySQL
- تأكد من اسم المستخدم وكلمة المرور

### CORS Error؟

ثبت حزمة CORS:

```bash
composer require fruitcake/laravel-cors
```

---

## 📚 مزيد من المعلومات

راجع [دليل النشر الكامل](DEPLOYMENT_GUIDE.md) للتفاصيل
