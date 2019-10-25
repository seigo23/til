## is_a?の使い所
- 例えば変数の中がuserなのかauthorなのか分からないかつ、
- userならidでauthorならauthor.user.idとしたい時、
- こんな感じでかける
```ruby
if @param.is_a?(Author)
  @param.user.id
else
  @param.id
end
```
