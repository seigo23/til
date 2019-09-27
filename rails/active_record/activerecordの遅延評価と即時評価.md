## activerecordの遅延評価と即時評価
- クエリがすぐ発行されたりされなかったり謎やったけどようやくわかった
- ActiverecordのActiveRecord::FinderMethodsに定義されてるメソッドはそれを読み込んだ瞬間にDBにアクセスする。（遅延評価ではない）
- ActiveRecord::FinderMethodsの例：`find, find_by, take, first, last, exists?`
- それ以外のメソッドは遅延評価されて、実際に値が必要になるまで取りに行かないので、特定の条件の時だけwhereを入れたいみたいな時に便利
- 具体例：where, limitなど
- 参考：https://qiita.com/ykamez/items/0c81a33ec1b90219d541
- 特定の条件の時だけwhereを入れたい時はこんな感じ
```ruby
user = User.where(food_id: 1)
user = user.where(kind: 2) if some_params.present?
user = user.order(id: :desc)
```
