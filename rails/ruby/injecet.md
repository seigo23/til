## injectの使い方

- 配列をループさせて新しく配列を作ったりハッシュを作ったりする時に便利

```ruby
array = ['user1','user2','user3']

# 例えば新しい配列作るときにこんなんしてた
new_array = []
array.each do |a|
  new_array << "#{a}_name" 
end


# injectならこれでいけるので無駄な宣言をしなくて済む
new_array = array.inject([]) do |array, user|
  array << "#{user}_name"
end
 

```

- ブロックの第一引数にループごとの戻り値が入る
- injectメソッドに何も渡さなかったらレシーバの配列の最初の要素が入るので配列内の合計値を出したりする時に使える
- 参考：https://www.sejuku.net/blog/19219#hash

