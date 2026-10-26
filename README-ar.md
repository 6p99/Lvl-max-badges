# دليل تشغيل أداة تزوير ساعات وألعاب ديسكورد

---

### **متطلبات التشغيل:**
1. يجب أن يكون لديك **Python** مثبت على جهازك.
2. يجب إعداد ملفات الأداة (بما في ذلك ملف `script.py`) في مجلد العمل الخاص بك.

---

### **خطوات التشغيل خطوة بخطوة:**

1. **فتح أدوات المطورين في ديسكورد:**
   * افتح تطبيق ديسكورد لسطح المكتب أو استخدم ديسكورد من متصفح الويب.
   * افتح نافذة المطورين (**Developer Tools / Console**) بالضغط على `Ctrl + Shift + I` ثم الانتقال إلى تبويب **Console**.

2. **الحصول على الكوكي (Cookie):**
   * انسخ الكود التالي، الصقه في الـ **Console**، واضغط `Enter` لنسخ الكوكي مباشرة إلى الحافظة لديك:
     ```javascript
     copy(document.cookie)
     ```

3. **الحصول على التوكن (Token):**
   * انسخ كود الجافا سكريبت المحدث أدناه، الصقه في الـ **Console**، واضغط `Enter`:
     ```javascript
     window.webpackChunkdiscord_app.push([
       [Math.random()],
       {},
       (e) => {
         for (let c of Object.values(e.c)) {
           try {
             let t = c.exports && c.exports.default && (c.exports.default.getToken || c.exports.default.m);
             if (t) {
               let token = typeof t === 'function' ? t() : t;
               if (token && typeof token === 'string' && token.length > 50) {
                 copy(token);
                 console.log('%cSuccess! Token copied to clipboard.', 'font-size: 16px; color: green;');
                 return;
               }
             }
             if (c.exports && c.exports.getToken) {
               let token = c.exports.getToken();
               if (token && typeof token === 'string' && token.length > 50) {
                 copy(token);
                 console.log('%cSuccess! Token copied to clipboard.', 'font-size: 16px; color: green;');
                 return;
               }
             }
           } catch (err) {}
         }
         console.log('%cCould not find token automatically. Please use the Network tab method.', 'color: red;');
       }
     ]);
     ```
   * بعد تشغيل هذا الكود وفي حال نجاحه، ستظهر لك رسالة نجاح باللون الأخضر وسيتم نسخ **التوكن** الخاص بك تلقائياً إلى الحافظة.

4. **تشغيل السكريبت عبر البايثون:**
   * افتح موجه الأوامر (`CMD` أو `PowerShell`) داخل مجلد الأداة.
   * شغّل السكريبت باستخدام الأمر التالي:
     ```bash
     python script.py
     ```
   * عند بدء التشغيل وعندما يُطلب منك، الصق **التوكن** ثم **الكوكي** الذي قمت بنسخهما في الخطوات السابقة.

5. **استخدام القائمة:**
   * بمجرد التحقق من بيانات الاعتماد الخاصة بك وتحميل الألعاب، ستظهر لك القائمة الرئيسية بالخيارات التالية:
     * **1** · المطالبة بالألعاب (`claim games`)
     * **2** · تحديث المصادقة (`refresh auth`)
     * **3** · تعيين بصمة ملف التشغيل (`set fingerprint`) (حيث تضع مسار أي ملف `.exe` للعبة أو رقم العملية PID الخاص بها لتوليد البصمة الصحيحة).
     * **4** · الخروج (`Exit`)
