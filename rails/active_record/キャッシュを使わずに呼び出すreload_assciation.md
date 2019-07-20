## reload_association
- belongs_toで追加される
- DB読み込み時にキャッシュがあってもそれを使わず新規で呼び出しにいく
- UserモデルとRoleモデルがある時
- `@user.role`だとキャッシュがある時にキャッシュを使ってしまう。
- `@user.reload_role`だとキャッシュがあってもキャッシュを使わない。
- 参考： https://railsguides.jp/association_basics.html#belongs-to%E3%81%A7%E8%BF%BD%E5%8A%A0%E3%81%95%E3%82%8C%E3%82%8B%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89
