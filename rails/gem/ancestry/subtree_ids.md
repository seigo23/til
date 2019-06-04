# ancesteryのメソッド「subtree_ids」
- `has_ancestry`したモデルに対して、`モデル.subtree_ids.flatten`すると、自分と自分の子孫のidが取れる
- 上記を使えば子孫関係のあるカテゴリーで、親ならみれるとかの表示の切り分けが可能
- やっぱり新しいgem使うときは公式ドキュメント見て、便利なメソッドがすでに用意されてないか確認するべき
参考：https://github.com/stefankroes/ancestry#user-content-navigating-your-tree
