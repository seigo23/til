## 代入先の変数は同じだけど条件によって代入値を変えたい時
- rubocopで怒られるやつ
- 対象警告文：`Use the return of the conditional for variable assignment and comparison.`
- 参考：http://chamao.hatenablog.com/entry/2018/07/21/153545

```ruby
#悪い例 ------

if a == 1
  val = 'いち'
else
  val = 'そのた'
end

#良い例 ------
val = if a == 1
        'いち'
      else
        'そのた'
      end
```
