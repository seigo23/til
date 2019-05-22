# ransackの基本
- 基本の流れは下記
  - コントローラで下記みたいに書く。この時@qの中にはクエリ情報が入ってる
    - @q = `@post.search(params[:q])`

  - 実際のレコードを見たい時は下記のようにする
    - `@posts = @q.result`
    - これでPostモデルの取りたいデータがくる

  - `params[:q]`の中に入り得るもの
    -  `{ "s" => "priority asc" }` → sはsortのaliasで、こういう風に送ると`order by priority asc`という風に変換される

  - viewとかからこんな感じでパラメータを渡す
     `<%= link_to(posts_path(q:{post_type_in: [1,3,4], post_status_eq: 0})) do ... なんかボタンとかのDOM ... end %> `

  - よくpunditとかkaminari一緒に使われて下記みたいになるから注意（よくごっちゃになる）
    - `policy_scope(Post)`はPundit
    - `search(params[:q])`はRansack
    - `.page(params[:page]).per(5)`はkaminari
```ruby
     @q = policy_scope(Post).search(params[:q])
     @posts = @q.result.page(params[:page]).per(5)  
```

  - 下記のようにすれば簡単にソート機能が付けれる（例）
    -  `<%= sort_link(@q, :title, '件名', default_order: :asc) %>`

- sはsortsのエイリアス
- この辺の何がどういうクエリを表すかは公式とか下記サイトにのってる
  - 参考：http://nekorails.hatenablog.com/entry/2017/05/31/173925
