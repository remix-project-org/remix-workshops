در این بخش، ما ابرداده‌های خود را ایجاد کرده و آنها را به صورت غیرمتمرکز ذخیره خواهیم کرد.

IPFS (سیستم فایل بین سیاره‌ای) یک شبکه نظیر به نظیر برای ذخیره فایل‌ها به صورت توزیع‌شده است. Pinata.cloud یک سرویس پین کردن است که به کاربران امکان می‌دهد به راحتی فایل‌ها را در شبکه IPFS میزبانی کنند.

ما می‌خواهیم تصاویر و فایل‌های JSON خود را به همراه متادیتای آنها در IPFS میزبانی کنیم.

### ایجاد پوشه تصویر

در این مثال، ما برای سه توکن، متادیتا ایجاد خواهیم کرد. همانطور که در زیر می‌بینید، ما سه تصویر ایجاد می‌کنیم که آنها را در یک پوشه ذخیره کرده‌ایم.

```
geo-img
├── geo_1.png
├── geo_2.png
├── geo_3.png
```

### در پیناتا ثبت نام کنید

حالا می‌خواهیم این تصاویر را در جایی میزبانی کنیم تا بتوانیم در متادیتای توکن‌هایمان به آنها اشاره کنیم. بیایید این کار را به صورت غیرمتمرکز انجام دهیم و از پیناتا برای میزبانی آنها در IPFS استفاده کنیم.

ابتدا به یک حساب کاربری در پیناتا نیاز دارید. به <a href="https://app.pinata.cloud/register" target="_blank">Pinata.cloud</a> بروید و یک حساب کاربری ایجاد کنید. در پیناتا می‌توانید تا ۱ گیگابایت داده را به صورت رایگان آپلود کنید.

پس از ثبت نام، باید در نمای مدیریت پین Pin Managerباشید.

<img src="https://i.imgur.com/yKpD65m.png" alt="Pin Manager Pinata" width="300"/>

### آپلود تصاویر در IPFS

روی دکمه آپلود کلیک کنید و پوشه حاوی تصاویر خود را آپلود کنید.
پس از آپلود پوشه، باید نام پوشه و CID (شناسه محتوا) مرتبط با آن را مشاهده کنید. اگر محتوای پوشه تغییر کند، CID نیز تغییر خواهد کرد.

برای دسترسی به پوشه خود در IPFS، آدرس "https://ipfs.io/ipfs/" را وارد کنید و CID خود را اضافه کنید. برای مثال فعلی ما، می‌توانید با استفاده از این آدرس به پوشه خود دسترسی پیدا کنید: <a href="https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P" target="_blank">
https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P </a>

شما می‌توانید با استفاده از موارد زیر به یک تصویر خاص دسترسی پیدا کنید: <a href="https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_1.png" target="_blank">
https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_1.png </a>

### فایل های JSON ایجاد کنید

ما یک پوشه دیگر ایجاد می‌کنیم که در آن سه فایل JSON ذخیره می‌کنیم.

```
geo-json
├── 0
├── 1
├── 2
```

درون فایل‌های JSON، متادیتاهای مربوط به توکن‌ها، مانند نام، توضیحات و تصویر را ایجاد کنید.
برای آدرس تصویر، ما از آدرس تصاویر خود در IPFS استفاده خواهیم کرد. در صورت تمایل می‌توانید داده‌های اضافی اضافه کنید؛ در این مثال، ما برای هر توکن چند ویژگی منحصر به فرد اضافه کردیم.

JSON مربوط به اولین توکن می‌تواند به این شکل باشد:

```
{
"name": "Geometry#0",
"description": "Geometry یک مجموعه NFT برای اهداف آموزشی است.",
"image": "https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_1.png
",
"attributes": [
{ "trait_type": "background", "value": "cyan" },
{ "trait_type": "color", "value": "red" },
{ "trait_type": "shape", "value": "circle" }
]
}
```

JSON مربوط به توکن دوم می‌تواند به این شکل باشد:

```
{
    "name": "Geometry#1",
    "description": "Geometry is an NFT collection for educational purposes.",
    "image": "https://ipfs.io/ipfs/QmTJok2tju9zstjtAqESdZxTiUiFCBAyApHiDVj4maV75P/geo_2.png",
    "attributes": [
        { "trait_type": "background", "value": "magenta" },
        { "trait_type": "color", "value": "green" },
        { "trait_type": "shape", "value": "square" }
    ]
}
```

همانطور که در بالا نشان داده شده است، پوشه در این مثال "geo-json" نام دارد. درون این پوشه، سه فایل JSON داریم.
اولین فایل JSON با نام "0"، دومین فایل JSON با نام "1" و سومین فایل JSON با نام "2" شناخته می‌شود.

مطمئن شوید که فایل‌های JSON شما پسوند file نداشته باشند و مانند tokenId های مربوط نامگذاری شوند.
در قسمت مدیریت پین در pinata.cloud، روی دکمه آپلود کلیک کنید و پوشه حاوی فایل‌های JSON خود را آپلود کنید.

برای دسترسی به پوشه خود در IPFS، آدرس "https://ipfs.io/ipfs/" را وارد کنید و CID خود را اضافه کنید.
برای مثال فعلی ما، می‌توانید با استفاده از موارد زیر به پوشه خود دسترسی پیدا کنید: <a href="https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp" target="_blank">
https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp </a>
این آدرس، آدرس پایه ما خواهد بود.

شما می‌توانید با اضافه کردن یک اسلش و شناسه توکن tokenId با استفاده از دستور زیر به یک فایل JSON خاص دسترسی پیدا کنید: <a href="https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/0" target="_blank">
https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/0 </a>

در قرارداد، baseURI را با baseURI خودتان جایگزین کنید. در این مثال، baseURI شامل URL است.

اکنون با اضافه کردن tokenId به baseURI، برای هر توکن یک tokenURI مجزا ایجاد می‌شود - دقیقاً همان کاری که ما در مثال بالا برای دسترسی به فایل JSON به صورت دستی انجام دادیم.
