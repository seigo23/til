## ホワイトリストに使えるpresence_in
- こんな感じで、ホワイトリストチェックできる
- 引数の中にあれば、レシーバを返して、なかったらnilを返してくれる
```ruby

'admin'.presence_in %w(admin staff viewer)
# => "admin"

'invalid'.presence_in %w(admin staff viewer)
#=> nil

```
- 参考：https://thr3a.hatenablog.com/entry/20181206/1544099172
