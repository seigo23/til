## enumの便利な使い方
- ていうかメソッド
- Articleモデルのstatusカラムがenumで、`{ draft: 0, published: 1 }`こんな感じの時
- `Article.statuses`で`{ draft: 0, published: 1 }`というハッシュが返ってくる
- つまりこんな感じで使える`Article.where(status: Article.statuses[:draft])`
- 参考：https://qiita.com/shizuma/items/d133b18f8093df1e9b70#enum%E3%81%AE%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89
