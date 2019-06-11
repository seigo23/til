## 配列に対するsortで使うUFO演算子
- `array.sort! {|fst, scd| fst.id <=> scd.id`
- これでidの昇順に並び替えれる
- activerecordリレーションじゃなくて単純な配列にしか使えない
- 参考：https://www.javadrive.jp/ruby/array_class/index14.html
