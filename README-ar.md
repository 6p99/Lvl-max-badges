# شرح تشغيل أداة تزوير ساعات وألعاب ديسكورد

---

### **متطلبات التشغيل:**
1. يجب أن يكون لديك **Python** مثبت على جهازك.
2. يجب إعداد ملفات الأداة في مجلد العمل (بما في ذلك ملف `script.py`).

---

### **خطوات التشغيل:**

1. **فتح أداة ديسكورد (Discord):**
   * افتح تطبيق ديسكورد على سطح المكتب أو عبر متصفح الويب.
   * افتح نافذة المطورين (**Developer Tools / Console**) في المتصفح أو تطبيق ديسكورد بالضغط على `Ctrl + Shift + I` ثم الانتقال إلى تبويب **Console**.

2. **الحصول على الكوكي (Cookie):**
   * انسخ الكود التالي وضعه في الـ **Console** واضغط `Enter` لنسخ الكوكي مباشرة إلى الحافظة لديك:
     ```javascript
     copy(document.cookie)
     ```

3. **الحصول على التوكن (Token):**
   * انسخ كود الجافا سكريبت الخاص باستخراج التوكن وضعه في الـ **Console** واضغط `Enter`:
     ```javascript
     window.webpackChunkdiscord_app.push([
       [Math.random()],
       {},
       req => {
         if (!req.c) return;
         for (const m of Object.keys(req.c)
           .map(x => req.c[x].exports)
           .filter(x => x)) {
           if (m.default && m.default.getToken !== undefined) {
             return copy(m.default.getToken());
           }
           if (m.getToken !== undefined) {
             return copy(m.getToken());
           }
         }
       },
     ]);
     console.log('%cWorked!', 'font-size: 50px');
     console.log(`%cYou now have your token in the clipboard!`, 'font-size: 16px');
     ```
   * بعد تنفيذ هذا الكود، سيتم نسخ **التوكن** الخاص بك إلى الحافظة تلقائياً.

4. **تشغيل الأداة عبر البايثون:**
   * افتح موجه الأوامر (`CMD` أو `PowerShell`) في مجلد الأداة.
   * قم بتشغيل السكريبت بالأمر التالي:
     ```bash
     python script.py
     ```
   * عند بدء التشغيل، ستطلب منك الأداة إدخال **التوكن** ثم **الكوكي** الذي قمت بنسخهما في الخطوات السابقة.

5. **استخدام القائمة:**
   * بعد إدخال البيانات بنجاح وتحميل الألعاب، ستظهر لك القائمة الرئيسية لاختيار:
     * **1** · لاختيار عدد الألعاب والساعات المراد تزويرها (`claim games`).
     * **2** · لتحديث المصادقة (`refresh auth`).
     * **3** · لتعيين البصمة `fingerprint`.
     * **4** · للخروج.
