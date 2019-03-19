## CapybaraでAjaxを待ちたいとき
- 非同期なので先に走っちゃって`element_not_found`的なのが出る
- 下記のようなやつを`spec/support/system_helper.rb`とかに書く。
- `system_helper.rb`を読み込む設定もいる。下の方参照
- `Capybara.default_wait_time`とかでデフォルトの待ち時間が設定されてる時もある
- とりあえずAjax投げてその結果をexpectに使うならwait_for_ajaxにブロック渡してその中でやるべき

spec/support/system_helper.rb
```ruby
def wait_for_ajax(wait_time = 2)
    Timeout.timeout(wait_time) do
      loop until finished_all_ajax_requests?
    end
    yield if block_given?
  end

  def finished_all_ajax_requests?
    # jQuery.active = 実行中のAjaxの数
    page.evaluate_script('jQuery.active').zero?
  end
```

###使うとき
```ruby
#この辺でAjax走らせる処理

wait_for_ajax do
  expect(xxx).to  eq 'zzz'
end
```

###ちなみに読み込む設定はこんな感じ
spec/rails_helper.rb

```ruby
RSpec.configure do |config|
  # 他にもいるかもやけど
  config.include SystemHelper, type: :system
end
```
