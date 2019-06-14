## params[:q]のストロングパラメータについて
- 確実な違いはわかってないけど下記みたいなパターンがある。
```ruby
# permitしなくてもいけるパターン
Model.ransack(params[:q]) 

some_params = {id_eq: 2, name_not_null: true}

# permitしないとダメなパターン
Model.ransack(g: [pramas[:q], some_params])


# permitしてからハッシュにしないとダメなので下記みたいにする
params[:q].permit!.to_h 

```
- シンプルモードのransackやと裏でパラメータに対してpermitしてくれてるのかも
- permit!がいい方法かは微妙やけど実務既存ソースに入ってたしまあ論外とかではなさそう。
- permitとかしなかったときは下記エラーがでる
- `undefined method with_indifferent_access' for パラメータのインスタンス的な`
