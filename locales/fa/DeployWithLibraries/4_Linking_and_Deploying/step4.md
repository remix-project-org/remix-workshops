به ماژول `استقرار و اجرا` بروید![اجرای تراکنش](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/4_Linking_and_Deploying/images/remix_runtransaction.png "اجرای تراکنش")

- محیط Remix VM را انتخاب کنید و قرارداد `sampleContract` را در لیست قراردادهای کامپایل شده انتخاب کنید.

- بر روی `Deploy` کلیک کنید

ترمینال باید چیزی شبیه به `ایجاد نمونه با خطا مواجه شد: <address> یک آدرس معتبر نیست.` را خروجی دهد. لطفاً بررسی کنید که آدرس ارائه شده معتبر است. این انتظار می‌رود: **ما `autoDeployLib` را به false تنظیم کرده‌ایم، بنابراین Remix انتظار دارد که آدرس داشته باشد و فقط `<address>` نباشد**

بنابراین ما نیاز داریم که کتابخانه را مستقر کنیم تا آدرس آن را بدست آوریم.

- کتابخانه `aLib` را در لیست قراردادهای کامپایل شده انتخاب کنید و روی `deploy` کلیک کنید

  ![انتخاب aLib](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/4_Linking_and_Deploying/images/contract_alib.png "انتخاب aLib")

- بر روی آیکون کلیپ بورد کلیک کنید تا آدرس کتابخانه را کپی کنید.

  ![](https://github.com/ethereum/remix-workshops/raw/master/DeployWithLibraries/4_Linking_and_Deploying/images/alib_copy.png "کپی")

- آن را در **متادیتای نمونه قرارداد** جای‌گذاری کنید.

- قرارداد `sampleContract` را در ماژول `اجرا تراکنش` دوباره انتخاب کنید و روی deploy کلیک کنید.

- اکنون باید استقرار موفقیت‌آمیز باشد.

