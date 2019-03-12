## メールが送信されてないことの検証

下記でメールが送信されていないことの検証ができる

```ruby
expect { subject }.to change { ActiveMailer::Base.deliveries.count }.by(0)
```
