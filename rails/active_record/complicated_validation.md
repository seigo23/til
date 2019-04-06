## 複数条件つきvalidation

下記のような場合のレビュー箇所
- まずコメントはideやyardで見やすいようにメソッドの上に書く（そもそも処理と全く同じ内容なので書かなくていい）
- blankでi18nに登録してるならerros.addしなくてもuser_idにpresence:trueすれば勝手にそこが呼ばれる
- つまり今回の場合は複数条件つきバリデーションが使えるのでメソッドを定義する必要がない
- 複数条件を設定する場合はラムダ式を使う
- 例1のようにするべき

例1
```ruby
validates :user_id, presence: true, if: ->{ finished? || completed? }

```


該当のメソッド
```ruby
def method
  # ステータスが「終了済み」もしくは「完了済み」で、user_idが存在しない場合のみエラー
  return true if finished? || completed?
  return true if user_id.present?
  errors.add(:client_id, :blank)
  false
end
```

参考：https://qiita.com/tmzkysk/items/a0c874715ba38eb23350
