## ネストしたハッシュの値を取得するときはdigを使う
- `hash[:key1][:key2]`みたいな感じでネストした奥のハッシュの値とったりするけど、これだと途中がnullだった場合にぬるぽで落ちる 
- なので、こういうときは`hash.dig(:key1,:key2)`としておけば途中がnullならnullで返してくれるので安全
- 参考：https://qiita.com/jnchito/items/02ba8aad634a6bd8a2f6
