## each_with_objectとinjectの違い
- `rails/ruby/inject_return_final_val.md`でも書いたけど、injectだとループの最後に評価されたものが次に繰り越されるけど
each_with_indexやと、最後に評価されたとかじゃなくて第二引数に渡した奴が次に回される。

- だから、injectを使ってて、最後に無駄に返したい奴を置くような処理はeach_with_indexの方がいい

- 方がいいと言うか、rubocop入ってたら弾かれるのでそうする。

- 参考：https://qiita.com/Kta-M/items/c9781e09d96601687767
