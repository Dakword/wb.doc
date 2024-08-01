Определение адреса в зависимости от артикула

```js
volHostV2(25696931);        // >> '//basket-02.wbbasket.ru/vol256/part25696/25696931'
volFeedbackHost(25696931);  // >> '//feedback01.wbbasket.ru/vol256/part25696/25696931'

function volHostV2(nmId) {
    const nm = parseInt(nmId, 10),
          vol = ~~(nm / 1e5),
          part = ~~(nm / 1e3);
	  
    const host =
		vol <= 143 ? "//basket-01.wbbasket.ru" 
		: vol <= 287 ? "//basket-02.wbbasket.ru" 
		: vol <= 431 ? "//basket-03.wbbasket.ru" 
		: vol <= 719 ? "//basket-04.wbbasket.ru" 
		: vol <= 1007 ? "//basket-05.wbbasket.ru"
		: vol <= 1061 ? "//basket-06.wbbasket.ru"
		: vol <= 1115 ? "//basket-07.wbbasket.ru"
		: vol <= 1169 ? "//basket-08.wbbasket.ru"
		: vol <= 1313 ? "//basket-09.wbbasket.ru"
		: vol <= 1601 ? "//basket-10.wbbasket.ru"
		: vol <= 1655 ? "//basket-11.wbbasket.ru"
		: vol <= 1919 ? "//basket-12.wbbasket.ru"
		: vol <= 2045 ? "//basket-13.wbbasket.ru"
		: vol <= 2189 ? "//basket-14.wbbasket.ru"
		: vol <= 2405 ? "//basket-15.wbbasket.ru"
		: vol <= 2621 ? "//basket-16.wbbasket.ru"
		: vol <= 2837 ? "//basket-17.wbbasket.ru"
		: "//basket-18.wbbasket.ru";
		
    return `${host}/vol${vol}/part${part}/${nm}`;
}

function volFeedbackHost(nmId) {
    const nm = parseInt(nmId, 10),
          vol = ~~(nm / 1e5),
          part = ~~(nm / 1e3);
    const host =
		vol >= 0 && vol <= 431 ? "//feedback01.wbbasket.ru" 
		: vol >= 432 && vol <= 863 ? "//feedback02.wbbasket.ru" 
		: vol >= 864 && vol <= 1119 ? "//feedback03.wbbasket.ru" 
		: vol >= 1200 && vol <= 1535 ? "//feedback04.wbbasket.ru" 
		: vol >= 1536 && vol <= 1919 ? "//feedback05.wbbasket.ru" 
		: "//feedback06.wbbasket.ru";
		
    return `${host}/vol${vol}/part${part}/${nm}`;
}
```
