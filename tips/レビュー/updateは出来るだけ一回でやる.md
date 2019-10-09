## updateは出来るだけ一回でやる
- DBのカラムとかやったら一括でやるけど、update時にaccessorが混じってる場合、DBカラムとは別やから下記みたいにやりがち
- accessorやからって別枠で設定する必要ないので注意
```ruby
attr_accessor :is_updatable
# before_updateとかで、update時にis_updatableが設定されてないと更新させないみたいなのがあったとする

# 下記のやり方は微妙
# @user.update_user(permit_params, true)と呼び出す前提 
def update_user(args, is_updatable)
  self.is_updatable = is_updatable
  self.update({ name: args[:name], mail: args[:mail] })
end

# 下記の方がいい。
# @user.update_user(permit_params.merge(is_updatable: true))と呼び出す前提 
def update_user(args)
  self.update({ name: args[:name], mail: args[:mail], updatable: args[:is_updatable] })
end

```
