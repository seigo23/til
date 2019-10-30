## 中身がある場合にそれをいれるパターン（presence）
- presenceを使えば三項演算子で微妙な書き方しなくてよくなる。
- presenceはレシーバに対してpresent?をかけて、trueならレシーバ自身を返して、falseやったらnilを返す
```ruby
# 微妙な例
name = params[:name].present? ? params[:name] : 'no_name'

# 良い例
name = params[:name].presence || 'no_name'

```
- 参考：https://qiita.com/yu-croco/items/d2dff0be438a451fd9d0#presence
