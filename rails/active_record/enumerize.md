## enumerizeくそ便利
- 参考が全て
- enumerizeを設定したいモデルに`extend Enumerize`て書く
- 数字だけじゃなくて文字も使える
- localファイルにenumerize用の記述をしておけば、値と表示名のセットの配列を取得でき、selectにそのまま使える
- selectに使うときはしたみたいな感じ
- `User.sex`にはこの場合、Enumerizeオブジェクトが入ってる
```ruby

# 定義の仕方
# 配列のパターン 
enumerize :sex, :in => [:male, :female] 

# ハッシュのパターン
enumerize :status, :in => { active: 1, blocked: 2 }

# viewで使うとき
<%= form_for @user do |f| %>
  <%= f.select :sex, User.sex.options %>
<% end %>
```
- 参考：https://morizyun.github.io/blog/enumerize-i18n-enum-rails-ruby/index.html
