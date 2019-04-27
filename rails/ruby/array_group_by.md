## 配列とかハッシュに対して使えるgroup by
- 配列とかハッシュの要素ごとにブロックを回して、戻り値が同じものをグループ分けしてハッシュで返す
- よくgroupbyした後にselectとかで抽出したりする
- 参考：https://ref.xaio.jp/ruby/classes/enumerable/group_by
- 下みたいな使い方ができる

```ruby
hash = {} #ほんまはここに諸々入ってる
group = hash.group_by { |element| element['id'] }.select { |_k, v| v.size > 1 }
```
