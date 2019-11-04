# ifと同時に代入が可能なので注意
- 以下の文は`==`を`=`と書き間違えてる訳ではなくて、
- userに値を代入して、もしそれがあればという書き方になってる。
- 間違って=にしてしまうと落ちることもなくそのまま処理されるので注意
```ruby
if user = find_user
  send_mail_to(user)
end

```
- 参考：https://qiita.com/jnchito/items/dedb3b889ab226933ccf#%E4%BB%A3%E5%85%A5%E3%81%97%E3%81%A6%E3%81%8B%E3%82%89if%E3%81%A7%E5%AD%98%E5%9C%A8%E3%82%92%E7%A2%BA%E8%AA%8D%E3%82%92%E3%81%BE%E3%81%A8%E3%82%81%E3%81%A6%E6%9B%B8%E3%81%8F
