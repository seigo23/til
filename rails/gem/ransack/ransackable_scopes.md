## ransackable_scopes
- 下記の感じにすれば`User.ransack(hoge: true).result(distinct: true)`でscopeで定義した絞り込みが使える
- デフォルトのransackだけでは厳しい時に便利
- 引数を渡すことも可能（参考を参照）
- 参考：http://utwang.io/2015/05/24/ransack-advanced-tips/
- `result(distinct: true)`しないと結果が重複することがあるので注意

- ↓ソースの例
```ruby
#Userモデルだとして

scope :hoge, -> { where(some_search_info) }

def self.ransackable_scopes(auth_object = nil)
  %i(hoge)
end
```

```ruby
# 参考先のソースを一応こっちにも保存
# モデル
class Post < ActiveRecord::Base
  belongs_to :blog

  scope :of_visible_blog, -> { includes(:blog).references(:blogs).merge(Blog.visible) }
  scope :title_of, ->(title) { where(title: title) }

  def self.ransackable_scopes(auth_object = nil)
    %i(of_visible_blog title_of)
  end
end 

# 実行
Post.ransack(of_visible_blog: true).result
Post.ransack(title_of: "It's a beautiful day").result
Post.ransack(of_visible_blog: true, title_of: "It's a beautiful day").result
  
```
