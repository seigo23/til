# APサーバを再起動しないとダメなとき
```
# 下記以外のファイルはサーバ再起動が必要
app/*
db/*
config/routes.rb
```
- moduleを触っててapp内にあると思ってたけどなくて、全然変更が反映されなくてハマった。
- 変更反映されてない感があったらまずこのディレクトリ以外のファイルか確認する
- てかもうちょっとでもおかしいと思ったら再起動するべき。そんな時間かからんし。
- 参考：https://keruuweb.com/rails-%E3%81%A9%E3%82%93%E3%81%AA%E3%81%A8%E3%81%8D%E3%81%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E3%81%AE%E5%86%8D%E8%B5%B7%E5%8B%95%E3%81%8C%E5%BF%85%E8%A6%81/
