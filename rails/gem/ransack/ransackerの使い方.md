## ransackerの使い方
- 簡単に言うと存在しないカラムでも加工して使えるようにできる
- 一番簡単な例が下記
```ruby
# Userモデル内
ransacker :created_on, callable: proc { Arel.sql("DATE(users.created_at)") }

# 上記のようにransacker登録しておくことで、下記が使える 
 
# usersコントローラー
 # 下記で、user作成"日時"ではなく作成"日"で検索できる 
 User.ransack(created_on: Time.zone.today)  
```

- 参考: https://qiita.com/ishidamakot/items/3002f9d6f71424a8aafb
