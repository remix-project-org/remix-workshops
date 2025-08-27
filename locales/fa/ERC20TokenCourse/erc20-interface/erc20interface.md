ERC20 (درخواست نظرات اتریوم ۲۰) استانداردی برای قراردادهای توکن است که توکن‌های قابل تعویض را در بلاکچین اتریوم مدیریت می‌کند.

توکن‌های قابل تعویض همگی با یکدیگر برابر هستند و ارزش، رفتار و حقوق یکسانی دارند. توکن‌های قابل تعویض اغلب به عنوان واسطه مبادله، مانند ارزهای ETH یا BTC، استفاده می‌شوند. با این حال، آنها می‌توانند موارد استفاده دیگری مانند حق رأی یا اعتبار نیز داشته باشند.

اگر می‌خواهید درباره استاندارد توکن ERC20 بیشتر بدانید، به مشخصات موجود در <a href="https://eips.ethereum.org/EIPS/eip-20" target="_blank">پیشنهاد بهبود اتریوم</a> آن نگاهی بیندازید.

## رابط

برای اینکه مروری بر قابلیت‌های مورد نیاز یک قرارداد توکن ERC20 داشته باشیم، به رابطی که با یک قرارداد ERC20 تعامل دارد، نگاهی خواهیم انداخت.
این رابط (خط 9) بخشی از کتابخانه قرارداد متن‌باز ارائه شده توسط <a href="https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v4.4.0/contracts/token/ERC20/IERC20.sol" target="_blank">OpenZeppelin</a> است.

## توابع ERC20

قراردادهایی که با استاندارد ERC20 مطابقت دارند باید شش عملکرد زیر را پیاده‌سازی کنند:

### تامین کل

تابع `totalSupply` (خط ۱۳) کل تعداد توکن‌های موجود را برمی‌گرداند.

### تعادل از

تابع `balanceOf` (خط ۱۸) تعداد توکن‌های متعلق به حسابی با آدرس `account` را برمی‌گرداند.

### تراکنش ها

تابع `transfer` (خط ۲۷) `مقدار` توکن‌ها را به آدرس `recipient` منتقل می‌کند.
این تابع **باید** یک رویداد `Transfer` (به پایین مراجعه کنید) را منتشر (تولید) کند و **باید** زمانی که فرستنده توکن‌های کافی برای انجام انتقال ندارد، یک استثنا صادر کند.

### approve

تابع `approv` (خط ۵۲) به آدرس `spender` اجازه می‌دهد تا `amount` توکن‌ها را از طرف حسابی که تابع را فراخوانی می‌کند، منتقل کند.

### کمک هزینه

تابع `allowance` (خط ۳۶) مقدار توکن‌هایی را که آدرس `spender` مجاز است از طرف حسابی با آدرس `owner` خرج کند، برمی‌گرداند.

### انتقال از

تابع `transferFrom` (خط ۶۳) `مقداری` از توکن‌ها را از طرف آدرس `sender` به آدرس `recipient` منتقل می‌کند.
این تابع **باید** یک رویداد `Transfer` منتشر کند.

## ERC20 Events

ERC20 contracts must also emit two events:

### Transfer

The `Transfer` (line 71) event must be emitted when `value` amount of tokens are transferred from the account with the address `indexed from` to `indexed to`. The parameters `from` and `to` are `indexed` allowing us to search for these events using the indexed parameters as filters.

### Approval

The `Approval` (line 77)  event must be emitted when the account `indexed owner` approves the account `indexed spender` to transfer `value` amount of tokens on its behalf.

## ERC20 Optional functions

In addition to the mandatory functions and events, there are also three optional functions specified in the ERC20 standard that are not implemented in this interface:

### name

`function name() external view returns (string);`

Returns the name of the token.

### symbol

`function symbol() external view returns (string);`

Returns the symbol of the token.

### decimals

`function decimals() external view returns (uint8);`

Returns the number of decimal places the token uses.

You may want to use decimals to make your token divisible into arbitrary amounts like 1.5 ETH when displayed. The EVM (Ethereum virtual machine) only supports integer numbers. That's why the ERC20 standard suggests to implement the decimal functionality that specifies how many decimal places a token has. 18 decimal places is the industry standard.
