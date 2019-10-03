## ストロングパラメータでそのままupdate
- 下記みたいな感じにで、updateのカラム名を指定しなくても、paramsはpermitされたタイミングでカラム名と値のハッシュになってるので
- そのままアップデートできる。

```
def update
@user = User.first

@user.update(update_params)
end


private

def update_params
  params.require(:user).permit(:name, :email, :password)
end

```
