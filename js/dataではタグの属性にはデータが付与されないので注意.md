## dataではタグの属性にはデータが付与されないので注意
```js
// これはhtmlのdata属性に実際にデータがはいる
$("body").attr('data-flg', 'active')

// これだと一旦jqueryにキャッシュされるだけらしくて、htmlのdata属性には反映されない
$("body").data('data-flg', 'active')

// だからデータをその場で直接設定したい場合はattrを使う
```
 
