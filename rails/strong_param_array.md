## ストロングパラメータで配列を入れるとき
- 下記みたいな感じ

```ruby
def hoge_params
  params.permit(:name, :pref, :text, hobbies: [], hoges: [])
end
``` 

### requireとpermitの違い
- requireがキーを指定してて、permitがその中の要素を指定してるイメージ（参考参照）
- パラメータで渡されても上記2つで許可していないと使えない。
- permitすると、permitted: trueが入る

---

参考_配列の許可：https://qiita.com/sayama0402/items/576345a1f7d37571f5a6
参考_requireとpermitの違い：http://techblog.kyamanak.com/entry/2017/08/29/012909
