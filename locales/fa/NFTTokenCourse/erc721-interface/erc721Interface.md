ERC721 استانداردی برای قراردادهای توکن است که توکن‌های غیرقابل تعویض (NFT) را در بلاکچین اتریوم مدیریت می‌کند.

هر توکن غیرقابل تعویض منحصر به فرد است و قابل تعویض نیست. NFTها می‌توانند ویژگی‌ها، رفتار یا حقوق متفاوتی داشته باشند. توکن‌های غیرقابل تعویض برای نشان دادن مالکیت دارایی‌های دیجیتال و فیزیکی منحصر به فرد مانند آثار هنری، اشیاء کلکسیونی یا املاک و مستغلات استفاده می‌شوند.

اگر می‌خواهید درباره استاندارد توکن ERC721 بیشتر بدانید، به مشخصات موجود در <a href="https://eips.ethereum.org/EIPS/eip-721" target="_blank">پیشنهاد بهبود اتریوم</a> آن نگاهی بیندازید.

## رابط

استاندارد ERC721 پیچیده‌تر از استاندارد ERC20 است و دارای افزونه‌های اختیاری می‌باشد. قراردادهای سازگار با ERC721 حداقل باید رابط‌های ERC721 و ERC165 را پیاده‌سازی کنند که در این بخش به آنها خواهیم پرداخت.

این رابط (خط ۱۱) بخشی از کتابخانه قرارداد متن‌باز ارائه شده توسط <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/IERC721.sol" target="_blank">OpenZeppelin</a> است.

## توابع پایه IERC721

قراردادهایی که با استاندارد ERC721 مطابقت دارند باید عملکردهای زیر را پیاده‌سازی کنند:

### تعادل از

تابع `balanceOf` (خط 30) تعداد توکن‌های متعلق به حسابی با آدرس `owner` را برمی‌گرداند.

### صاحب

تابع `ownerOf` (خط ۳۹) آدرس `owner` حسابی را که توکن با شناسه `tokenId` را در اختیار دارد، برمی‌گرداند.

### safeTransferFrom

تابع `safeTransferFrom` (خط ۵۵) مالکیت یک توکن با شناسه `tokenId` را از حسابی با آدرس `from` به حسابی با آدرس `to` منتقل می‌کند.

تابع `safeTransferFrom` (خط ۱۳۷) تقریباً مشابه تابع `safeTransferFrom` (خط ۵۵) است. تنها تفاوت این است که این تابع دارای یک payload غیر خالی به نام `data` است.

یک قرارداد هوشمند برای دریافت یک انتقال باید رابط ERC721TokenReceiver را پیاده‌سازی کند. این تضمین می‌کند که قرارداد می‌تواند انتقال توکن‌های ERC721 را مدیریت کند و از قفل شدن توکن‌ها در قراردادی که نمی‌تواند این کار را انجام دهد، جلوگیری می‌کند.

### انتقال از

تابع `transferFrom` (خط ۵۵) مالکیت یک توکن با شناسه `tokenId` را از حسابی با آدرس `from` به حسابی با آدرس `to` منتقل می‌کند.

**توصیه می‌شود در صورت امکان از safeTransferFrom به جای transferFrom استفاده کنید.**
تابع `transferFrom` امن نیست زیرا بررسی نمی‌کند که آیا قرارداد هوشمندی که گیرنده انتقال است، رابط ERC721TokenReceiver را پیاده‌سازی کرده است و قادر به مدیریت توکن‌های ERC721 است یا خیر.

## توابع پیشرفته IERC721

### تایید کند

تابع `approve` (خط ۹۴) به حسابی که آدرس `to` دارد، اجازه می‌دهد تا توکنی با شناسه `tokenId` را از طرف حسابی که تابع را فراخوانی می‌کند، مدیریت کند.

### دریافت تایید

تابع `getApproved` (خط ۱۰۳) آدرس حسابی (متغیر return `operator`) را که برای مدیریت توکن با شناسه `tokenId` تأیید شده است، برمی‌گرداند.

### تاییدیه برای همه

تابع `setApprovalForAll` (خط 115) مجوز (`_approved`) را برای حسابی با آدرس مشخص شده (پارامتر ورودی - `operator`) تنظیم می‌کند تا تمام توکن‌های حسابی که تابع را فراخوانی می‌کند، مدیریت کند.

### تایید شده برای همه

تابع `getApproved` (خط ۱۰۳) در صورتی که حساب کاربری با آدرس `operator` برای مدیریت تمام توکن‌های حساب کاربری با آدرس `owner` تأیید شده باشد، مقدار بولی true را برمی‌گرداند.

## رویدادهای IERC721

قراردادهای ERC721 همچنین باید رویدادهای زیر را منتشر کنند:

### تراکنش ها

رویداد `Transfer` (خط ۱۵) باید زمانی صادر شود که توکن با شناسه `tokenId` از حسابی با آدرس `from` به حسابی با آدرس `to` منتقل شود.

### تایید

رویداد `Approval` (خط 20) باید زمانی صادر شود که حسابی با آدرس `owner`، حسابی با آدرس `spender` را برای مدیریت توکن با شناسه `tokenId` از طرف خود تأیید کند.

### تأیید برای همه

رویداد `ApprovalForAll` (خط ۲۵) باید زمانی صادر شود که حساب کاربری با آدرس `owner` به حساب کاربری با آدرس `operator` مجوز (`_approved`) برای مدیریت تمام توکن‌هایش را بدهد یا آن را لغو کند.

## IERC165

علاوه بر رابط ERC721، قراردادهای سازگار با ERC721 باید رابط ERC165 را نیز پیاده‌سازی کنند.

با پیاده‌سازی رابط ERC165، قراردادها می‌توانند پشتیبانی از رابط‌های خاص را اعلام کنند. قراردادی که می‌خواهد با قرارداد دیگری تعامل داشته باشد، می‌تواند قبل از انجام تراکنش، مثلاً ارسال توکن‌هایی که ممکن است از آنها پشتیبانی نکند، بررسی کند که آیا قرارداد دیگر از این رابط پشتیبانی می‌کند یا خیر.

Our IERC721 interface here imports (line 6) and inherits (line 11) from the IERC165 interface.

This is how <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/introspection/IERC165.sol" target="_blank">OpenZeppelins implementation</a> of the ERC165 interface looks like:

```
interface IERC165 {
    function supportsInterface(bytes4 interfaceId) external view returns (bool);
}
```

For example, the ERC165 identifier for the ERC721 interface as specified in the EIP721 is “0x80ac58cd”. Learn how to calculate an interface identifier and more about the ERC165 in its <a href="https://eips.ethereum.org/EIPS/eip-165" target="_blank">improvement proposal</a>.

## Other interfaces

The <a href="https://eips.ethereum.org/EIPS/eip-721#specification" target="_blank">IERC721TokenReceiver</a> interface must be implemented to accept safe transfers.

There are two optional extensions for ERC721 contracts specified in the EIP721:

IERC721Enumerable enables a contract to publish its full list of tokens and make them discoverable.

IERC721Metadata enables a contract to associate additional information to a token. We will have a more detailed look into this in the next section.
