## enum_helperによるenumのi18n化（_i18n）
-  `enum gender: { male: 0, female: 1 }`みたいにしてる時
- かつ、`config/locales/ja.yml`に下記みたいに記述している時
```yaml
ja:
  enums:
    user:
      gender:
        male: 男性
        female: 女性
```

- こんな感じになる
```ruby
# genderに0を設定している場合でuserにユーザ情報が入ってる場合
user.gender_i18n
=> "男性"
```


- invertメソッドを使うとそのenumの情報をハッシュで返してくれる（セレクトに入れる時とか便利） 
```ruby
# 設定しているenumをハッシュで展開
user.genders_i18n.invert
=> {"男性"=>"male", "女性"=>"female"}
```

参考：https://kimuraysp.hatenablog.com/entry/2016/05/19/233144
