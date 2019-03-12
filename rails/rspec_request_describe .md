## gem 'rspec_request_describe' 

このgemを使ってる場合は、
下記みたいにリクエストのエンドポイントは
describeに書いたやつで自動的に設定される。

だから、is_expectedだけでいける。（subjectとかも使える）

詳細は公式のReadmeのUsageみる。


```ruby

describe 'GET path/some/request/' do
  it 'return 200' do
    is_expected.to eq(200)
  end
end

```

