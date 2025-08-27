در این قرارداد، ما از پیاده‌سازی قرارداد توکن ERC721 از OpenZeppelin (خط 4) استفاده می‌کنیم.

نگاهی به پیاده‌سازی آنها از قرارداد <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/ERC721.sol" target="_blank">ERC721</a> بیندازید. جدا از قابلیت‌های مشخص‌شده در استاندارد ERC721، این قرارداد قابلیت‌های اضافی دیگری را نیز ارائه می‌دهد که در ادامه به آن‌ها خواهیم پرداخت.

## myToken

ما قرارداد خودمان به نام MyToken (خط 7) را ایجاد می‌کنیم که عملکرد آن (خط 7) از پیاده‌سازی قرارداد توکن OpenZepplin `ERC721` و `Ownable` که وارد کردیم (خط 4) به ارث می‌رسد. اگر ماژول قرارداد Ownable را به خاطر ندارید، به بخش افزونه‌های ERC20 نگاهی بیندازید.

این پیاده‌سازی ERC721 از افزونه‌ی IERC721Metadata که در EIP مشخص شده است، استفاده می‌کند. قرارداد ما توابع `name()` و `symbol()` را به ارث می‌برد و دارای یک سازنده است که امکان تنظیم مقادیر آنها را در طول استقرار قرارداد فراهم می‌کند (خط 8).
در این حالت، ما از مقادیر پیش‌فرض استفاده خواهیم کرد. ما توکن خود را با نام قرارداد «MyToken» نامگذاری می‌کنیم و نماد آن را «MTK» قرار می‌دهیم.

### URI پایه

با یک قرارداد ERC721، ما قادر به ضرب توکن‌های مختلف هستیم که هر کدام tokenId مخصوص به خود را دارند. همانطور که در رابط IERC721Metadata دیدیم، هر توکن می‌تواند `tokenURI` مخصوص به خود را داشته باشد که معمولاً به یک فایل JSON برای ذخیره ابرداده‌هایی مانند نام، توضیحات و لینک تصویر اشاره می‌کند.
اگر یک قرارداد چندین توکن ضرب کند، پیاده‌سازی‌های ERC721 اغلب از یک URI یکسان به عنوان پایه (`baseURI`) برای همه توکن‌ها استفاده می‌کنند و فقط با اضافه کردن `tokenId` منحصر به فردشان در انتها از طریق الحاق، آنها را از هم متمایز می‌کنند. در بخش بعدی، خواهیم دید که این در عمل چگونه به نظر می‌رسد.

در این مثال، ما داده‌های خود را در IPFS ذخیره می‌کنیم - در بخش بعدی بیشتر در این مورد صحبت خواهیم کرد. آدرس پایه ما <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/</a> است (خط 11).
از طریق الحاق، tokenURI برای توکنی با شناسه 0 به صورت <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/0</a> خواهد بود، tokenURI برای توکنی با شناسه 1 به صورت <a href="https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1" target="_blank">https://ipfs.io/ipfs/QmUYLUKwqX6CaZxeiYGwmAYeEkeTsV4cHNZJmCesuu3xKy/1</a> خواهد بود، و به همین ترتیب ادامه می‌یابد.

هنگام استفاده از IPFS و مواجهه با خطاهای "504 Gateway Time-out"، ممکن است مجبور شوید صبر کنید و دوباره امتحان کنید تا داده‌ها در دسترس قرار گیرند.

### امن نعناع

با تابع safeMint (خط ۱۴) به مالک این امکان را می‌دهیم که پس از استقرار قرارداد، توکن‌های جدیدی با شناسه توکن اختصاصی ایجاد کند.
تابع safeMint بخشی از پیاده‌سازی ERC721 از OpenZeppelin است و به ما امکان می‌دهد با خیال راحت یک توکن با شناسه `tokenId` را برای حسابی با آدرس `to` ضرب کنیم. برای کنترل دسترسی، از اصلاح‌کننده‌ی `onlyOwner` از ماژول قرارداد کنترل دسترسی Ownable که وارد کرده‌ایم (خط ۵) استفاده می‌کنیم.

در بخش بعدی، خواهیم دید که چگونه می‌توانیم فراداده‌های مربوط به NFTهای خود را ایجاد و میزبانی کنیم.

## ⭐️ تکلیف

1. نام قرارداد خود را به «هندسه» تغییر دهید.
2. نام توکن خود را به «Geometry» تغییر دهید.
3. نماد توکن خود را به «GEO» تغییر دهید.
4. `_baseURI` را به <a href="https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/" target="_blank">https://ipfs.io/ipfs/QmVrsYxXh5PzTfkKZr1MfUN6PotJj8VQkGQ3kGyBNVKtqp/</a> تغییر دهید.
