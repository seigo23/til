## ヒアドキュメントの代入

- 下記はarray配列のなかにselect文が文字列として2要素分入る（eachが2回回るから）
- ヒアドキュメントはその宣言とともに変数に代入できるので便利

```ruby
array = []
company_names = ['googlex', 'yahoox']
company_names.each do |company_name|
    array.push (<<~SQL)
            select
              u.id
            from
              users u
            inner join
              company c
            on c.user_id = u.id
            where
              c.name = #{company_name}
            and  u.salary > 200000
    SQL
end
```
