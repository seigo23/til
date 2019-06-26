##  has_many :through と has_and_belongs_to_many
- 参考見たら全て分かるが、両方とも3つのモデルが必要
- 中間モデルに何かバリデーションを仕込みたいとかならthrough
- 何も複雑性のないただの多対多ならhas_and_belongs_to_manyでも良い
- でも現場のソースでhas_and_belongs_to_manyはあんま見たことないし、いつバリデーション足すかもわからんからとりあえずthroughで良さそう。
- 参考：https://railsguides.jp/association_basics.html#has-many-through%E3%81%A8has-and-belongs-to-many%E3%81%AE%E3%81%A9%E3%81%A1%E3%82%89%E3%82%92%E9%81%B8%E3%81%B6%E3%81%8B
