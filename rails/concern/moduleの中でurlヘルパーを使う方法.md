## moduleの中でurlヘルパーを使う方法
- コントローラとかやったら多分もともと継承元のクラスでurlヘルパーがincludeされてるから使えてると思うけど
- 自作のモジュールにはもちろん何も継承されてないから自分で設定する必要がある（そもそもモジュールは継承とかできない。includeならできる）
- urlヘルパーを自分でincludeしたからやと思うけど、hostを指定しろって言われる。だからメーラーで使ってるhostを入れとけばいいと思う。
- `ActionMailer::Base.default_url_options[:host]`で環境ごとのhost取れる
```ruby
module HogeModule
    # まだよく分かってないけどextendしとかないと他のコントローラから呼べなかった
    extend ActiveSupport::Concern
      class << self
        # これでurlヘルパーを使える
        include Rails.application.routes.url_helpers
        
        def xxx(user)
          # Rails.application.routes.url_helpersをincludeしてなかったら落ちる
          p user_url(user, host: default_host) 
        end 
        
        def default_host
          ActionMailer::Base.default_url_options[:host]
        end
      end
end 
        

```

- 参考1：https://qiita.com/jerrywdlee/items/f91c9ea01055cb74083c
- 参考2：https://codeday.me/jp/qa/20190206/204450.html
