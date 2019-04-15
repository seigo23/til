## includesとjoinsの違いでハマったとこ
- includesしただけではjoinsみたいにincludesされた側のカラムにアクセスできない
- できると思ってハマってた
- だから、例えばUserとTweetモデルがあったとして下記みたいな感じ（実際に動かしたわけじゃないからコケるかも）
```ruby
##  N+1パターン
Users.all.each do |u|
 p u.name
 p u.tweet.title
end

##  事前キャッシュしてるのでN+1起きないパターン
Users.all.includes(:tweet).each do |u|
 p u.name
 
  #ここがなぜかu.titleで取れると思ってた（結合されてると思ってたので）
 p u.tweet.title
end

```

ほんで、`u.tweet.titleやとデメテル的にだめやからuserテーブルにdeligate: title, to: :tweet, prefix:false`みたいにしとけば最初意図してた感じでかける


参考：https://workout-engineer.com/rails-includes%E3%81%A8joins%E3%81%AE%E9%81%95%E3%81%84%E3%82%92%E8%A7%A3%E8%AA%AC%EF%BC%81/
