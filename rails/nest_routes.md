## ネストしたルーティング

```ruby
namespace :account do
  resources :mail_layout, only: %i[create show] do
    resources :mail_layout_details, except: [:destory], param: :type
  end
end

```

→こんなんになる
http://localhost:3000/account/mail_layout/1/mail_layout_details/confirm_type/edit

- /1/はshowの:id
- /confirm_type/ は paramのtype
- editはそのままedit
