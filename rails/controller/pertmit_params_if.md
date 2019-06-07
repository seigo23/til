# ストリロングパラメータの分岐について
- permitはどんどん上書きされていくのでpermitする内容を上書きするようにかく
```ruby
private
    def member_params
      attrs = [:number,:name,:full_name,:gender,:birthday,:email,:password,:password_confirmation]
      attrs << :administrator if current_member.administrator?  # 注目
      params.require(:member).permit(attrs)
    end
```
- 参考：https://qiita.com/rik0/items/e691d0b7bfcf112e7dc3
