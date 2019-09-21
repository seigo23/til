## punditの基礎
- authorizeメソッドは渡したオブジェクトのクラス名から該当のPolicyファイルを見つけて、current_userとrecordを渡す。
- 現在のユーザがそのrecordに対して権限を持ってるか調べるイメージ
- pundit側で勝手に現在ユーザを判定するのでこっちが何かを触る必要はない。
- 参考：https://qiita.com/senou/items/e28ff548e93ad0eeed3f
