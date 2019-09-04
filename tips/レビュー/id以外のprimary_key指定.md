## 外部キーと主キーをid以外に設定できる 
- has_one :user, foreign_key: :another_id, primary_key: :another_id
- こうすれば主キーと外部キーの扱いをidじゃなくて指定したカラムに変更できる。
- 参考：https://morizyun.github.io/ruby/active-record-belongs-to-has-one-has-many.html#%E8%87%AA%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB%E3%81%8C%E5%AF%BE%E8%B1%A1%E3%81%AB%E6%89%80%E5%B1%9E%EF%BC%9Abelongs-to
