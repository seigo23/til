## active_decorateがno_method_errorになる
- 参考が全て
- has_manyとかのアソシエーションを使ってる && Viewでそれを呼んでる場合はdecorateされないのでメソッドがない状態になる
- コントローラで@tweets = @user.tweetsとかしてれば、view内でtweetのdecorateメソッド使える 

参考）https://qiita.com/aiyu427/items/6360c39e696d8908e533
