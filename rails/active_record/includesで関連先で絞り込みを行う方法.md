### includesで関連先で絞り込みを行う方法
- includesはpreloadかeager_loadのええ方をやってくれて、N+1の解決にしか使わんと思ってたけど、必要な時は関連先のテーブルも保持してくれる。
- つまり、テーブルの保持が必要な時はeager_loadで、キャッシュだけでいい時はpreloadしてくれるっぽい。
- なので、includesさえしとけば、そのさきで関連先で絞り込みを行える。
- 無駄にSQLを2回叩いて別のSQLで関連先を取りに行くみたいなことをしなくていい。
- 下記の通り
```ruby
 # Userをpostsの内容で絞りたい時 
 User.includes(:posts).where(posts: { name: 'example' })
 
 # 注意なのはこれ。where句はuser_sub_postsじゃないとダメ。
 # Userモデルで下記みたいに指定してる場合、includesの引数には省略された名前を書くけど、where句にはモデルの正式名称を書かないと反応しないので注意 
 # has_many :sub_posts, class_name: "UserSubPost", dependent: :destroy 
 User.includes(:sub_posts).where(user_sub_posts: {id: 1}) 

```

参考：https://web-camp.io/magazine/archives/17707
