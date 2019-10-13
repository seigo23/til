## indexで何番目の要素がクリックされたか確認する
- 参考のソースを使ったら意図通り動いたので、これを編集して使えばとりあえずいける

```html
<ul>
  <li class="some-item">hoge</li>
  <li class="some-item">foo</li>
  <li class="some-item">bar</li>
</ul>
```

```js

$('li.some-item').on('click', function(){
  var index = $('li.some-item').index(this);

  console.log(index + 'th item clicked!');
});
```
- 参考：https://qiita.com/otoyo/items/04e12fe478b7f76ce545
