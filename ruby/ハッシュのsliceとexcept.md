## ハッシュのsliceとexcept
- ActiveSupport拡張というのを使えば下記のようなことができる
- 本来はselectとかrejectとかでブロックで条件に当てはまるやつを抜き出すとかするとこがこれだけで済む
```ruby
some_hash = {
  key_a: "some content",
  key_b: "some content",
  key_c: "some content"
}

# :key_aと:key_bを取り出したい
some_hash.slice(:key_a, :key_b) #=> {key_a: ..., key_b: ...}

# :key_cを除外したい
some_hash.except(:key_c) #=> {key_a: ..., key_b: ...}
```
- 参考：https://qiita.com/mah_lab/items/ed10bae99105ea2fd8bd
