## dependent: :destroyするときは注意
- 特にhas_oneの時は注意する。てか基本的に使ったらあかんと思う。（関連先が削除されちゃうから）
- だから、`dependent: :destroy`じゃなくて、削除時にuserのidがnullになるように `dependent: :nullify`を使う
- 例えばanother_userとuserモデルがあったとして、
- another_userとuser1対1の時にdependent: :destroyすると、
- another_userを削除した時にuserが削除されてしまうことになる。
- 参考：https://www.stacky-health.work/2018/08/17/ruby_on_rails_dependent/#dependent_nullify

