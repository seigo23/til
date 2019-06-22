# Rails側のコントローラとJsのメソッド名がリンクしてる時
- JSがうまく呼べてないときはまず該当のRailsコントローラのメソッドを全部確認する。
- editページで更新ボタン押してupdateを呼んだ時に、バリデーションに引っかかったら、
元の編集ページに戻るけど、そのページはupdateとして呼ばれてるので、editのJSではなくupdateのJSが呼ばれる点に注意

- 基本的にクリック→リクエスト走る→Railsのコントローラ→RailsのView→該当のJSって感じやから、ここの処理順序よく注意する。
- editページでクリックした後もeditのJSが走ると勘違いしててハマった。