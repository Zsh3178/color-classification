Color classification
این پروژه شامل آموزش یک شبکه عصبی برای دسته‌بندی تصاویر تک‌رنگ از رنگ‌های مختلف مانند آبی، سبز، قرمز، زرد، سیاه، سفید و ... است که شامل کدهای پایتونی مختلفی برای ساخت مجموعه داده، مدل، آموزش، ارزیابی و تست است. 
سپس مقداری نویز دلخواه به تصاویر اضافه کرده و تغییر نتایج را بررسی و گزارش میکنیم.
 در مرحله آخر مقدار نویز را اضافه و اضافه کرده  و بررسی می کنیم تا چه حد نویز برای شبکه قابل تحمل است. 
در زیر توضیحی از هر مرحله اصلی آمده است:

 .1  آماده سازی مجموعه داده (Dataset prepagation):

-	وارد کردن کتابخانه‌ها و پکیج‌های لازم از جمله TensorFlow، Keras، NumPy، Matplotlib و PIL 
-	استفاده از API  Kaggleبرای دانلود مجموعه داده دسته‌بندی رنگ.
-	استخراج فایل ZIP دانلود شده 
-	دایرکتوری‌های غیرموردنیاز از مجموعه داده حذف شد تا داده‌ها پاک‌تر شوند.

2.	بررسی مجموعه داده ها (Dataset Exploration):
 -  شمارش تعداد تصاویر فایل دانلودی و نمایش نمونه‌هایی از رنگ‌های مختلف 

3  . پیش پردازش داده ها (Data Preprocessing):
-	تقسیم بندی داده ها به train , validation با استفاده از تابع image_dataset_from_directory
-	افزایش تعداد داده ها با کمک Data augmentation

4.	 ساخت مدل (Model Building):
-	ساخت مدل با شبکه CNN  و استفاده از لایه های  rescaling , Dropout, dataagumentation ,maxpool, flatten, dense
-	کامپایل کردن مدل با کمک 
-	Adam optimizer, sparse categorical cross-entropy loss, and accuracy metric.

5    . آموزش مدل (Model Training):
-	آموزش مدل با استفاده از تابع fit  و مجموعه داده های training , validation 
-	Training History ذخیره میشود که شامل accuracy و loss است 

6    . ارزیابی مدل (Model Evaluation): 
-	رسم نمودار loss  و accuracy  با کمک Matplotlib برای مشاهده عملکرد

7    . تست (Testing):
-	تهیه مجموعه تست برای تست دقت مدل روی داده های جدید 
-	ذخیره دقت مدل بر روی مجموعه تست در یک متغیر 
8. افزودن نویز (Adding Noise):
-	تعریف عامل نویز و اضافه کردن ان به تصاویر
-	یک تابع تعریف add_noise تا نویز را به تصاویر در یک دسته اضافه کند.
-	تغییر مجموعه داده آزمون با استفاده از عامل نویز تعریف‌ شده.
9. ارزیابی مجموعه داده نویزی(Noisy Dataset Evaluation):
-	ارزیابی دقت مدل بر روی مجموعه داده تست  نویزی 
-	پرینت accuracy مدل با داده تست نویزی

10. تحمل شبکه (Network Tolerance) :
-	اعمال نویز به مجموعه داده تست و ارزیابی دقت مدل
-	توقف حلقه اموزش اگر دقت تا اندازه مشخص رفت
11. تست نهایی با تحمل شبکه(Final Testing with Network Tolerance):

-	انتخاب عامل نویزی که منجر به کاهش دقت مدل زیردقت انتخاب شده است 
-	مجموعه داده آزمون با عامل نویز انتخاب‌شده تغییر می‌کند.  
-	دقت نهایی مدل بررسی و بر روی تصاویر تست  نویزی رسم می‌شود. 

به طور کلی، این کد پایتون فرآیند آموزش یک شبکه عصبی برای دسته‌بندی رنگ را، ارزیابی و عملکرد آن بر روی داده‌های نویزی را بررسی تحمل شبکه نسبت به نویز را نشان می‌دهد. 

