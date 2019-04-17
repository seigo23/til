## rspec（特にmodel spec）でprivateメソッドを呼ぶ方法
- `send()`を使う
- `Object#send(:private_method)`みたいにすれば呼べる（Objectはインスタンス）
参考：https://morizyun.github.io/blog/rspec-private-method-ruby-rails/index.html
