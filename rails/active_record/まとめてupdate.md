## まとめてupdate
- updateとupdate_attributesはただのエイリアス
- updateにはハッシュオブジェクトかparameterオブジェクトを入れられる。
```ruby

params = {
  name: "aaa",
  email: "aaa@aaa.com",
  saraly: 200000,
}

# 上記の場合、こうできる
user = User.fisrt

user.update(params)

# いちいちこんなんしなくていい
 user.update(
 name: params[:name],
 email: params[:email],
 saraly: params[:saraly],
 )
```
- ただ、paramsのなかにuserにはないカラムが含まれてた場合は`unknown attribute '存在しないカラム名' for 対象モデル.`となるので注意
- だからコントローラーでparamsを受け取るときはupdateとかで使う単位で階層を分けてる方が楽
