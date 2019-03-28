## Form_forの引数とルーティング
- form_forのあとの引数にはモデルオブジェクトを入れる
- 例えば@userを入れた場合、submitしてコントローラにパラメータが渡った時、`params[:user]`以下に全てのuserのattributesが入る
- `url:`オプションでPOST先を指定できる。
- ただし自分でurlを指定しなくてもform_forの後に入れたモデルオブジェクトが新規ならcreateで、既存ならupdateに飛ばしてくれる
- ネストしたルーティングにform_forを使う時は`form_for([@user, @mail]....)`みたいに配列で二つ渡す
---
参考:
https://qiita.com/shunsuke227ono/items/7accec12eef6d89b0aa9
