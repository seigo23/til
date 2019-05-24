## send_data
- 簡単にCSVとかいろんな形式のデータを出力することができる
- ソース見たらわかるけど、renderまで中でやってくれてるから、send_dataだけ使えばクライアントのダウンロードまでやってくれるっぽい
- CSVの場合は下記みたいに使う

```ruby
users = User.all
send_data users.to_csv, type: "text/csv; charset=shift_jis", filename: "all_users.csv"
```

- 参考：http://railsdoc.com/references/send_data
- ソース：https://github.com/rails/rails/blob/e220a34e396f026bbee8c7492aaa0ca515995a05/actionpack/lib/action_controller/metal/data_streaming.rb#L127
