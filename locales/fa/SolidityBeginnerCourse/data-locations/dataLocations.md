مقدار متغیرها در سالیدیتی می‌تواند در مکان‌های داده مختلف ذخیره شود: _حافظه_، _ذخیره‌سازی_ و _کال‌داده_.

همانطور که قبلاً بحث کردیم، متغیرهای نوع مقدار یک نسخه مستقل از یک مقدار را ذخیره می‌کنند، در حالی که متغیرهای نوع مرجع (آرایه، ساختار، نگاشتن) تنها موقعیت (ارجاع) مقدار را ذخیره می‌کنند.

اگر ما از یک نوع مرجع در یک عملکرد استفاده کنیم، باید تعیین کنیم که مقادیر آنها در کدام مکان داده ذخیره شده‌اند. قیمت اجرای تابع تحت تأثیر محل داده‌هاست؛ ایجاد کپی از انواع مرجع هزینه گاز می‌برد.

### ذخیره‌سازی

مقدارهای ذخیره شده در _ذخیره‌سازی_ به‌صورت دائمی در بلاکچین ذخیره می‌شوند و به همین دلیل، استفاده از آن‌ها هزینه‌بر است.

در این قرارداد، متغیرهای دولتی `arr`، `map` و `myStructs` (خطوط ۵، ۶ و ۱۰) در حافظه ذخیره می‌شوند. متغیرهای حالت همیشه در حافظه ذخیره می‌شوند.

### حافظه

مقادیر ذخیره شده در _حافظه_ تنها به صورت موقتی ذخیره می‌شوند و در بلاک‌چین نیستند. آنها تنها در طول اجرای یک تابع خارجی وجود دارند و بعد از آن کنار گذاشته می‌شوند. استفاده از آنها ارزان‌تر از مقادیری است که در _ذخیره‌سازی_ نگهداری می‌شوند.

در این قرارداد، متغیر محلی `myMemstruct` (خط 19) و همچنین پارامتر `_arr` (خط 31) در حافظه ذخیره می‌شوند. پارامترهای تابع باید محل داده _حافظه_ یا _کال دیتا_ داشته باشند.

### کال دیتا

_کال دیتا_ آرگومان‌های تابع را ذخیره می‌کند. مانند _حافظه_، _کالldata_ تنها در طول اجرای یک تابع خارجی به طور موقت ذخیره می‌شود. In contrast to values stored in _memory_, values stored in _calldata_ can not be changed. Calldata is the cheapest data location to use.

In this contract, the parameter `_arr` (line 35) has the data location _calldata_. If we wanted to assign a new value to the first element of the array `_arr`, we could do that in the `function g` (line 31) but not in the `function h` (line 35). This is because `_arr` in `function g `has the data location _memory_ and _function h_ has the data location `calldata`.

## Assignments

### Memory to memory

Assignments from _memory_ to _memory_ create references instead of copies. If you change the value in one variable, the value of all other variables that reference the same data will be changed.

If we were to create a new struct `myMemStruct2` with the data location _memory_ inside the `function f` (line 12) and assign it the value of `myMemStruct` (line 19), any change to `myMemStruct2` would also change the value of `myMemStruct`.

### Storage to local storage

Assignments from _storage_ to _local storage_ also create references, not copies.

If we change the value of the local variable `myStruct` (line 17), the value of our state variable `myStructs` (line 10) changes as well.

## Storage and memory/calldata

Assignments between _storage_ and _memory_ (or _calldata_) create independent copies, not references.

If we were to create a new struct `myMemStruct3` with the data location _memory_ inside the `function f` (line 12) and assign it the value of `myStruct`, changes in `myMemStruct3` would not affect the values stored in the mapping `myStructs` (line 10).

As we said in the beginning, when creating contracts we have to be mindful of gas costs. Therefore, we need to use data locations that require the lowest amount of gas possible.

## ⭐️ Assignment

1. Change the value of the `myStruct` member `foo`, inside the `function f`, to 4.
2. Create a new struct `myMemStruct2` with the data location _memory_ inside the `function f` and assign it the value of `myMemStruct`. Change the value of the `myMemStruct2` member `foo` to 1.
3. Create a new struct `myMemStruct3` with the data location _memory_ inside the `function f` and assign it the value of `myStruct`. Change the value of the `myMemStruct3` member `foo` to 3.
4. Let the function f return `myStruct`, `myMemStruct2`, and `myMemStruct3`.

Tip: Make sure to create the correct return types for the function `f`.