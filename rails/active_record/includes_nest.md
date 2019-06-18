## ネストした階層をincludes

- 孫を複数includesするとき
```ruby
Hoge.includes(baz: [:bar, :foo])

```

- ひ孫をincludesするとき
```ruby
Hoge.includes(baz: { bar: :foo })

```

- 色々まざったパターン
```ruby
Hoge.includes(:hoge, baz: [{ bar: :fiz }, :foo])

```

- 参考：https://qiita.com/takashisite/items/9d1484b88708e2872134
