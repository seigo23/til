## 文字列を指定文字数で切り取って残りを...で省略できる
- 下記みたいな感じ
```ruby
'Once upon a time in a world far far away'.truncate(27)
# => "Once upon a time in a wo..."
```

- デフォルトは30文字になってる。
- 参考：http://railsdoc.com/references/truncate
- 参考：https://qiita.com/tomoko523/items/7ccd3c9bb97c26ee568b
