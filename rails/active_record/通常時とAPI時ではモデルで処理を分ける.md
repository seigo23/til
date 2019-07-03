## APIと通常でモデルを分ける
- DBのテーブルは分けないけど、モデル内の処理は下記みたいにする
  - APIで使うUserの処理`model/api/user.rb`で`class Api::User`みたいにする
  - 通常時で使うUserの処理`model/user.rb`で`class User`みたいにする

- 基本的にapiと通常時で処理を分けてみやすくするため（routingもそのために分けてる）
