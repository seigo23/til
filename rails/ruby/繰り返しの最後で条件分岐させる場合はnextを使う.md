# 繰り返しの最後で条件分岐させる場合はnextを使う
- rubocopで怒られる
- こんな感じ
```ruby

# ダメな例
[1,2,3].each do |i|
  p "数値は#{i}です。"
  if i.even?
    p "奇数です"
  end
end

# 良い例
[1,2,3].each do |i|
  p "数値は#{i}です。"
  next unless i.even?
  p "奇数です"  
end

```
