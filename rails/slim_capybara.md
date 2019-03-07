## Slimでidとかclassに動的な値を入れて、Capybaraを楽にする

- `tr[id="spec-user-#{user.id}"]`とかって書いたらtdに動的なid付けれる
- そしてsystem specで下記みたいにすればレコード作成順に依存せず確認できる

```ruby
 within all("tr#spec-user-#{user.id}")[0] do
   expect(all('td')[2].text).to eq 'hogehoge'
 end
```


※`take_screenshot`するときは`js:true`にするのを忘れない
