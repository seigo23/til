## Capybaraのドライバ
- Capybaraでsystem_specというかsenario_spec書くときにテストケース毎になんとなく
`js:true`とかつけてたけど
あれはどのドライバを使ってテストを実行するかを決めてる。

- `spec/support/capybara.rb`にて詳細が定義されてる。

- `js:true`をつけたら`Selenium`を使うし、つけなかったらデフォルトの`Racktest`をドライバとして使う

- 特にJSの動作が必要ない文言のテストとかは`Racktest`を使うこと。（`Racktest`の方が速い）

