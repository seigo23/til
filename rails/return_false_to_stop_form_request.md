##  form_forの代わりにAjaxでAPI叩くとき
form_forで特定のルートに対してリクエスト送ってるように見えるのに

それ自体はリクエスト送ってなくて、
下記みたいな感じでcoffee（jquery)でAPI叩いてる時がある


↓ ruby（slim）
```ruby
= f.submit '作成', id: 'js-task'

```


↓ coffeescript
```coffeescript
$('#js-task').submit(function(){
  # API叩く処理がこの辺に入ってる 
  return false;
});
```

formのsubmitにidをつけておいて、
それがsubmitされたときに上記の処理が走って、
formのsubmitはreturn falseによって中止されて、
APIを叩く処理だけ走らせることができる。

※API叩いて、submitに対してfalseが返されるとsubmit自体を中止する。


