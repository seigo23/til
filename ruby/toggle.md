## toggle
- t/fを入れ替えることができる
- 意図しないときにその処理通った時とか怖いから扱うときは注意した方が良さそう。
```ruby
p @user.is_manager
# => true
@user.toggle(:is_manager)
p @user.is_manager
# => false
```
- 参考：https://qiita.com/ysk_1031/items/5d1fa1321abf2f432674#activerecordpersistencetoggle

