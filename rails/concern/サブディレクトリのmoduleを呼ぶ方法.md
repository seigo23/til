## サブディレクトリのmoduleを呼ぶ方法
- こんな感じで呼べた。
- 多分コントローラ側でincludeするのがええんやろうけどうまくいかなかった。
- ディレクトリが複数形の時はmodule名も呼び出し時も複数形にしないとダメなので注意

```ruby 
  # module app/controller/concern/supers/hoge.rb
  module Supers
    module Hoge
      extend ActiveSupport::Concern
      class << self
        def piyo
          # 処理
        end
      end
    end
  end 

 # コントローラ
 # includeしなくても使えた。（多分直接読んでる） 
 Supers::Hoge.piyo
  
```

