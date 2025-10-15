# نظام إدارة المطعم المتكامل
## Laravel + MySQL + Frontend

---

## 🌟 نظرة عامة

نظام إدارة مطاعم احترافي ومتكامل تم تطويره باستخدام:
- **Backend**: Laravel 10 (PHP)
- **Database**: MySQL
- **Frontend**: HTML5 + CSS3 + JavaScript (Vanilla)
- **Architecture**: RESTful API

---

## ✨ المميزات الرئيسية

### 📦 إدارة المخزون
- إضافة وتعديل وحذف الأصناف
- تتبع الكميات والأسعار
- حساب هامش الربح تلقائياً
- تنبيهات المخزون المنخفض
- تتبع تاريخ الصلاحية
- سجل حركة المخزون (وارد/صادر)

### 👥 إدارة الموظفين
- سجلات الموظفين الكاملة
- المناصب والرواتب والأقسام
- حساب تكلفة الساعة
- حالة الموظف (نشط/غير نشط)
- بيانات الاتصال والهوية

### 🚚 إدارة الموردين
- قاعدة بيانات شاملة للموردين
- تصنيف حسب نوع المنتجات
- نظام تقييم الموردين
- بيانات الاتصال والعنوان

### 💰 النظام المالي
- تسجيل الإيرادات والمصروفات
- حساب صافي الربح تلقائياً
- تقارير مالية مفصلة
- تصنيف حسب النوع والتاريخ

### 🧾 نقاط البيع (POS)
- كاشير الأقسام
- سجل الطلبات اليومية
- إحصائيات المبيعات

### 📊 لوحة التحكم
- إحصائيات شاملة فورية
- تنبيهات المخزون المنخفض
- المنتجات قريبة الانتهاء
- ملخص مالي

### 🔔 نظام التنبيهات
- تنبيهات في الوقت الفعلي
- تصنيف حسب النوع
- علامات القراءة

### 🎨 الواجهة
- تصميم عربي كامل (RTL)
- واجهة احترافية وحديثة
- Dark/Light Mode
- تصميم متجاوب (Responsive)
- ألوان احترافية للمؤسسات

---

## 🏗 البنية التقنية

### Backend (Laravel)

```
backend/
├── app/
│   ├── Http/Controllers/     # 7 متحكمات رئيسية
│   │   ├── DashboardController
│   │   ├── InventoryController
│   │   ├── EmployeeController
│   │   ├── SupplierController
│   │   ├── FinanceController
│   │   ├── PosController
│   │   └── NotificationController
│   └── Models/               # 9 نماذج
│       ├── InventoryItem
│       ├── InventoryMovement
│       ├── Employee
│       ├── Supplier
│       ├── Revenue
│       ├── Expense
│       ├── PosOrder
│       ├── EmployeeMeal
│       └── Notification
├── database/migrations/      # 9 ملفات migration
├── routes/api.php           # مسارات RESTful API
└── config/                  # إعدادات النظام
```

### Database Schema

**الجداول الرئيسية:**
1. `inventory_items` - أصناف المخزون
2. `inventory_movements` - حركة المخزون
3. `employees` - الموظفين
4. `suppliers` - الموردين
5. `revenues` - الإيرادات
6. `expenses` - المصروفات
7. `pos_orders` - طلبات POS
8. `employee_meals` - وجبات الموظفين
9. `notifications` - التنبيهات

### Frontend

```
frontend/
├── index.html               # الصفحة الرئيسية
├── styles.css              # التصميم الشامل
└── js/
    ├── api.js              # طبقة الاتصال بـ API
    ├── db_laravel.js       # مدير قاعدة البيانات
    ├── utils.js            # وظائف مساعدة
    ├── app.js              # التطبيق الرئيسي
    └── modules/            # 9 وحدات
        ├── dashboard.js
        ├── inventory.js
        ├── pos.js
        ├── employees.js
        ├── employee_cashier.js
        ├── suppliers.js
        ├── finance.js
        ├── reports.js
        └── settings.js
```

---

## 🚀 التثبيت السريع

### المتطلبات:
- PHP 8.1+
- Composer
- MySQL 5.7+
- Apache/Nginx

### الخطوات:

```bash
# 1. إنشاء قاعدة البيانات
mysql -u root -p
CREATE DATABASE restaurant_db;
EXIT;

# 2. إعداد Backend
cd backend
composer install
cp .env.example .env
# عدل .env بإعدادات قاعدة البيانات
php artisan key:generate
php artisan migrate

# 3. تشغيل الخادم
php artisan serve

# 4. فتح Frontend
# افتح index.html في المتصفح
```

**لمزيد من التفاصيل، راجع [دليل النشر الكامل](DEPLOYMENT_GUIDE.md)**

---

## 📡 API Endpoints

### Dashboard
- `GET /api/v1/dashboard/stats` - إحصائيات عامة

### Inventory
- `GET /api/v1/inventory` - جميع الأصناف
- `POST /api/v1/inventory` - إضافة صنف
- `PUT /api/v1/inventory/{id}` - تحديث صنف
- `DELETE /api/v1/inventory/{id}` - حذف صنف
- `POST /api/v1/inventory/movements` - إضافة حركة

### Employees
- `GET /api/v1/employees` - جميع الموظفين
- `POST /api/v1/employees` - إضافة موظف
- `PUT /api/v1/employees/{id}` - تحديث موظف
- `DELETE /api/v1/employees/{id}` - حذف موظف

### Suppliers
- `GET /api/v1/suppliers` - جميع الموردين
- `POST /api/v1/suppliers` - إضافة مورد
- `PUT /api/v1/suppliers/{id}` - تحديث مورد
- `DELETE /api/v1/suppliers/{id}` - حذف مورد

### Finance
- `GET /api/v1/finance/revenues` - الإيرادات
- `GET /api/v1/finance/expenses` - المصروفات
- `POST /api/v1/finance/revenues` - إضافة إيراد
- `POST /api/v1/finance/expenses` - إضافة مصروف
- `GET /api/v1/finance/summary` - ملخص مالي

### POS
- `GET /api/v1/pos/orders` - جميع الطلبات
- `POST /api/v1/pos/orders` - إضافة طلب
- `GET /api/v1/pos/orders/today` - طلبات اليوم

### Notifications
- `GET /api/v1/notifications` - جميع التنبيهات
- `GET /api/v1/notifications/unread` - التنبيهات غير المقروءة
- `PUT /api/v1/notifications/{id}/read` - تحديد كمقروء

---

## 🔧 الإعدادات

### ملف .env (Backend)

```env
APP_NAME="Restaurant Management System"
APP_ENV=production
APP_DEBUG=false
APP_URL=http://localhost:8000

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=restaurant_db
DB_USERNAME=root
DB_PASSWORD=your_password
```

### ملف api.js (Frontend)

```javascript
const API_BASE_URL = 'http://localhost:8000/api/v1';
```

---

## 🛡 الأمان

- ✅ Validation على جميع المدخلات
- ✅ CSRF Protection
- ✅ SQL Injection Prevention (Eloquent ORM)
- ✅ XSS Protection
- ✅ Environment Variables للمعلومات الحساسة
- ✅ HTTPS Support (موصى به للإنتاج)

---

## 📊 الأداء

- استخدام Eloquent ORM لتحسين الاستعلامات
- Response Caching للبيانات المتكررة
- Lazy Loading للعلاقات
- Database Indexing على الأعمدة المهمة

---

## 🧪 الاختبار

### اختبار API:

```bash
# استخدم cURL أو Postman
curl http://localhost:8000/api/v1/dashboard/stats

# أو استخدم PHP Artisan
php artisan route:list
```

---

## 📱 التوافق

- **المتصفحات:**
  - Chrome 87+
  - Firefox 78+
  - Safari 14+
  - Edge 88+

- **الأجهزة:**
  - Desktop
  - Tablet
  - Mobile (Responsive)

---

## 🔄 التحديثات المستقبلية

- [ ] نظام تسجيل الدخول والصلاحيات
- [ ] تقارير PDF قابلة للطباعة
- [ ] تصدير البيانات إلى Excel
- [ ] نظام الفواتير المتقدم
- [ ] لوحة تحكم تحليلية متقدمة
- [ ] API Documentation (Swagger)
- [ ] Unit Tests
- [ ] Multi-language Support

---

## 📝 الترخيص

هذا المشروع مفتوح المصدر ومتاح للاستخدام الشخصي والتجاري.

---

## 👨‍💻 المطور

تم التطوير باستخدام أفضل الممارسات في تطوير تطبيقات Laravel.

---

## 📞 الدعم

للمشاكل التقنية أو الاستفسارات:
- راجع [دليل النشر](DEPLOYMENT_GUIDE.md)
- راجع [دليل حل المشاكل](DEPLOYMENT_GUIDE.md#-حل-المشاكل-الشائعة)

---

## 🙏 شكر خاص

- Laravel Framework
- MySQL Database
- مجتمع المطورين العرب

---

**نظام متكامل، احترافي، وجاهز للإنتاج**
