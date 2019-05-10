# activerecordのserialize
- 本来ハッシュとかをDBに直接保存しようとするとDBにはstringとして保存されちゃう（保存時に勝手にstringと言うかvarcharになってるぽい）
- なので、ハッシュを保存して、それを次呼び出しても文字列扱いになるので、ハッシュ関連のメソッドが使えなくなる
- そんな時にハッシュとか配列とかをいれたいカラムにserialize指定をしておけば元のオブジェクトのまま保存できる
- serializeは該当モデルクラスの中にかく。
- まあ参考見たらわかる
- 参考:https://easyramble.com/rails-active-record-serialize.html

---

- けどserializeは保守とかメンテがめんどいっぽいので積極的には使わないほうがよさそう
- 参考：https://qiita.com/jnchito/items/68e91e9bf46f960a79e4
