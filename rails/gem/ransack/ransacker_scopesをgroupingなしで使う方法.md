## ransackable_scopesをgroupingなしで使う方法
- groupingにするとやっぱりransackable_scopesは使えないっぽい
- こんな感じでparams[:q]の中にキーを追加したりして調整する
- A and (B or C)みたいなややこしい時以外は極力グルーピング使わない方が良い。
- 上記の時は`m : "or"`を追加しないとあかんからしょうがないけど。

```ruby
 if some_condition # 分岐させたい特定の条件
      params[:q] = {} unless params[:q]
      params[:q][:user_id_in] = [1,2,3]
      params[:q][:user_id_not_null] = true
    end
    
    @q = User.ransack(params[:q])
    @users = @q.result.page(params[:page])
```
