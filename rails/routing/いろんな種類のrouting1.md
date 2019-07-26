## ルーティング例
```ruby
namespace :api do
    scope ":version" do
      namespace :admin do
        resource :user, only: [] do
          get "super_user/:id", action: "super_user", as:"super_user"
          get :init_list
        end
      end
    end 
end 
 
```

- テストとかで使う時は以下のように使う

```ruby

 # get :init_list
 #=> `init_list_api_admin_user_path(version: "v1")`
 # これでApi::Admin::Userコントローラのinit_listアクションを呼べる 

 # get "super_user/:id", action: "super_user", as:"super_user"
 #=> `super_user_api_admin_user_path(version: "v1", id: @user.id )`
 # これでApi::Admin::Userコントローラのsuper_userアクションをidありで呼べる 

```
