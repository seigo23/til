##  render newで値を保持できる
- 下記みたいな感じでモデルの保存に失敗した時、入力された値を保持したままnewのページに飛ばせる

```ruby
## 下記では@messageが保存できなかった場合、app/views/messages/new.html.hamlへ飛ぶ
## その場合、入力していた値は保持されている！（newアクションに飛ぶわけではない）

def create
  @message = Message.new(message_params)
  if @message.save
    redirect_to messages_path(@message)
  else
    render :new
  end
end

```

- 参考：https://qiita.com/suimi34/items/8f04431954255f23b80c
