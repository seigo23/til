## Promiseをループの中でやる場合
- `var myPromise = Promise.resolve();`して、
- 下記みたいにするとループ内でもきちんと待ってくれる

```js

// OKパターン
var myPromise = Promise.resolve();

[1,2,3].forEach(function (r,index) {
 myPromise = myPromise
  .then()
  .then()
  .then()
  .then()
})
 
 
 // NGパターン（これだとループの中で待たない）
 [1,2,3].forEach(function (r,index) {
  Promise.resolve()
   .then()
   .then()
   .then()
   .then()
 })
  
  
```
参考：https://qiita.com/saka212/items/ff61a6de9c3e19810c5d
参考：https://qiita.com/boukichi_numloc/items/81e2e2668de9a455165c
