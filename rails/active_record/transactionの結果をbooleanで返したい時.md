## transactionの結果をbooleanで返したい時
- こんな感じ
- transacitonに成功した場合はtrueが返ってくる
- rescueしなかったら普通にエラーを返してくるので、rescueで拾ってfalseを返すようにする
- transactionがrollbackする基準はエラーが発生したかどうかなので、updateじゃなくてupdate!を使うこと（t/fではなくエラーを返す必要あり）
```ruby
def xxx(args)
  ActiveRecord::Base.transaction do
    @user.update!(name: args[:name])
  end
  rescue
  false
end
```
