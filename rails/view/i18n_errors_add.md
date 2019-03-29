## i18nを使ったエラー表示のやり方

```yaml
animal:
  attributes:
    zoo_id:
      taken: "同じ%{attribute}を設定することはできません。"
```

- animalモデル内とかで
`オブジェクト.errors.add(:zoo_id, :taken)`見たいにかく

- てか、複雑な状況じゃないなら、普通にzoo_idのvalidationにuniqueつけといたら、zoo_idが重複した時に:takenが呼ばれて
`"同じ%{attribute}を設定することはできません。"`がちゃんと呼ばれてくれる

