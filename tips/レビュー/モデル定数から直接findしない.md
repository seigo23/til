## モデル定数から直接findしない
- 前qiitaにも書いてたけどやっぱり正しい
```ruby
company = Company.first
# この時、名前が田中のユーザを検索する時は以下のようにするべき
company.users.find_by(name: "田中")

# 下記のようにすると何かの拍子にその会社以外のユーザが出てしまうので特に意図がないならやらない
User.find_by(name: "田中") 
 
```

