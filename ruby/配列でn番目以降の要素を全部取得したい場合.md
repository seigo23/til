## 配列でn番目以降の要素を全部取得したい場合
- `p [1,2,3,4][2..-1]`
- ` #=> [3,4]`となる
- ただし、後半の指定が不正な場合はnilが返されるので基本的には下記のように使う
- `models = Model.where(some_condition: true)[3..-1] || []`
- 参考に乗ってる`from`とかはactiverelationでは使えなかったので注意
- 参考：https://qiita.com/yoshiori/items/6d58cc54f2eef6c01a14
