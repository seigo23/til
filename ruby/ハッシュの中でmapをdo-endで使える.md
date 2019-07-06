## ハッシュの中でdo-endを使える
- 以下のようなことが可能
- 最終的に返す値が不正でないならOK
- この場合、`posts:`にハッシュの配列が入る
```ruby
user = User.first

hash =
    { 
     id: user.id,
     name: user.name,
     posts: user.posts.map do |p|
                      {
                          id: p.id,
                          name: p.name,
                      }
                    end, # ←この書き方無理やと思ってた。
    created_at: today,
    }

return hash
      
```
