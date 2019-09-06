## booleanのカラム名に?を使いたい時
- カラム名に?は使えない。
- でも例えばPostテーブルに`is_deleted`をbooleanでカラム設定した場合、
- `Post.first.is_deleted`でも`Post.first.is_deleted?`みたいに?をつけてもどっちでも使える
- ?が付いてたらbooleanって確定するので便利
- 参考：https://qiita.com/ironsand/items/7d97d950736c6afcb27b
