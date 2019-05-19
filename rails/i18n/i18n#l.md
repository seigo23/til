# lでformatを指定できる

- 下記みたいに、`l` を入れることで表示オブジェクトの後にformatを指定できる
- formatの形式は自分でlocalファイルに定義して、そのymlからformat名をシンボルで呼び出す感じ
```ruby
# app/views/home/index.html.erb
<h1><%= t :hello_world %></h1>
<p><%= flash[:notice] %></p>
<p><%= l Time.now, format: :short %></p> 
```



参考：公式（https://railsguides.jp/i18n.html#%E6%97%A5%E4%BB%98%E3%83%BB%E6%99%82%E5%88%BB%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%83%E3%83%88%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B）
参考：ymlへの書き方（https://qiita.com/cyborg__ninja/items/446506f60648e3e51c2c）
