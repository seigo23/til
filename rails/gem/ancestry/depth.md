#  階層の深さを取得する方法
- 下記のようにancestryを入れてるモデルにcache_depthオプションを入れる
- `has_ancestry cache_depth: true`
- そして、階層のながさを持つカラムを追加するマイグレーションファイルを作る（下記みたいに）
-  `add_column :models, :ancestry_depth, :integer, defaul: 0`

- 値は階層登録時に設定される。
- 後から未設定の階層に登録する場合は、コンソールで `Model.rebuild_depth_cache!` を実行すると、depthが登録される。

例： `Model.find(60).depth` で深さが取得できる
