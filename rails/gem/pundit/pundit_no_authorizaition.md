## Punditの対象メソッド+?の使い方（show?みたいなやつ）
- postsコントローラーでupdateを行う
- updateの処理の中で`authorize @posts`する
- その場合、post_policy内の`update?`メソッドが呼ばれる
- update?メソッドは最終的にbooleanを返す。
- trueの場合は何もしないが、falseの場合は`Pundit::NotAuthorizedError`を発生させる
- このままだと権限がなかった時（falseの時）に落ちてしまう。
- なのでapplication_controllerとかで`rescue_from Pundit::NotAuthorizedError, with: some_method`みたいなのを書いとく
- すると権限エラーが発生した時に呼び出し元（ここではpostsコントローラー）のsome_methodが呼ばれる
- some_methodのなかに権限が無い旨のフラッシュメッセージとリダイレクトさせる処理を入れるのが一般的っぽい。
