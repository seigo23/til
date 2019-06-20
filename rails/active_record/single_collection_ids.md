## has_manyで追加されるsingle_collection_idsメソッド
- こんな感じ
```ruby
User has_many :guests, through: :user_guest
Guest has_many :users, through: :user_guest


# 上記の時、下記のようにidsが使える（カラム名は適当）
User.create!(name: "名前", guest_ids: [1,2,3])
User.create!(name: "名前", guest_ids: 1)

#=> UserとUserGuestが両方作られる
# そしてややこしいのが、guest_idじゃだめっぽい 

Guest.create!(name:"名前", user_ids: [1,2,3])
Guest.create!(name:"名前", user_ids: 1)
#=> GuestとUserGuestが両方作られる

```

- 大体`単数系モデル_ids`ってなってたらこれ
- 参考：https://railsguides.jp/association_basics.html#has-many%E3%81%A7%E8%BF%BD%E5%8A%A0%E3%81%95%E3%82%8C%E3%82%8B%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89
