## params[:q]とは別のパラメータを使ってorをしたい時
- 下記みたいにする。
```ruby
custom_q_0 = params[:q]
custom_q_1 = { price_not_null: true, fee_not_null: true, m: 'or' }
Model.ransack(g: { '0': custom_q_0, '1': custom_q_1 })

# 驚くことに下記も同様となる
Model.ransack(g: [custom_q_0, custom_q_1])
```

- これで、`params[:q]` AND `price_not_null: true` OR `fee_not_null: true`が実現できる
- 参考：https://kei178.me/programming/1462/



## 注意
- 下記みたいにgroupingsを使う場合はキー0や1のバリューはnilでは落ちるので注意（with_indifferent_accessがぬるぽする）
- `Model.ransack(g: { '0': custom_q_0, '1': custom_q_1 })`


