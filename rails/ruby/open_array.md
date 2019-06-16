# 配列展開とflatten
- 配列を配列の中に入れたりするときに使える。
- またnilも考慮されてるので基本こっちの方がいい。
```ruby
#例えばa〜dまで入った配列を作りたいとき

array =  ["a", "b", "c"]

new_array = [array, "d"]

# このままだと平準化されてない
p new_array
# => [["a","b","c"], "d"]

# こうするとflattenと同じになる
new_array = [*array, "d"]
p new_array
# => ["a","b","c","d"]
```

- つまり下記のようになる
```ruby
[*array] == [array].flatten!
# => true
```

- nilについては下記のようになる
```ruby
a = nil 

p *a
#=> nil

p a.flatten!
#=> NoMethodError: undefined method `flatten!' for nil:NilClass

p a.flatten
#=> NoMethodError: undefined method `flatten' for nil:NilClass
```
- 記号を1つ増やすだけでいいので便利
- こういう時は出来るだけレシーバの値を考慮しなくてもいいメソッドじゃない方を選択する方が良さそう。
- 参考：http://yamakichi.hatenablog.com/entry/2016/10/18/232253
