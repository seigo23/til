## Capybaraでのlocatorとselectorの違い
  - 参考見たらわかるけどクラス名(`.user_form`とか)はlocatorになりえない
  - id名はlocatorになりうるけど、その時にIDを表す`#`は付けちゃダメ
  - idを使うとき、selectorの時は`#id_name`ってするけどlocatorの時は`id_name`（`#`付けない）ってしないとだめなのがハマったとこ
https://qiita.com/morrr/items/0e24251c049180218db4
