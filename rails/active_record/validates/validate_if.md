# バリデーションで条件分岐して、かつselfをレシーバとして使いたい時
- 下記みたいな感じでいける
- ifのあとは本来は`Proc.new`って書くのが公式やけど省略して下記みたいに単に`proc`だけ書いても動いた。
- procのブロック変数`r`はモデルインスタンス自身をさしてる（Bookモデルならbook）
```ruby
validates :some_id, presence: true, if: proc { |r| r.book.name.present? }
```
- 参考：https://railsguides.jp/active_record_validations.html#if%E3%82%84-unless%E3%81%A7proc%E3%82%92%E4%BD%BF%E3%81%86 
