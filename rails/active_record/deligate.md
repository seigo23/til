## RailsBestPracticeのLaw of Demeter対応
※User belongs to Teamの時
- ダメなパターン
  - User.team.name

- OKなパターン（例）
  - User.team_name
   
### deligateを使うべき
- メソッドチェーン的につなげていくと依存度が無駄に高くなる

- Userモデルに下記を追加するべき（User.team_nameで呼べる）

`delegate :name, to: :team, prefix: true, allow_nil: true`

`belongs_to :team, optional: true`の時に`allow_nil: true`が必要
