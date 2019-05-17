## f.selectのオプションについて
- selectのオプションは順番注意
- 下記の1と2で１は正しく動いて2が正しく動かない理由は、5個目の引数にはoptionsが入って、6個目の引数にはhtml_optionsが入るから。
- html_optionsが何かはまだよくわかってないけど、とりあえずoptionsではないものはhtml_optionsに入れないとだめっぽい。
- そんで、6個目の引数にmultiple一つだけの場合はハッシュの波括弧は省略できる。（複数になるといるっぽい？）
1:
```
<%= f.collection_select :カラム名, DB値, :id, :name, { include_blank: true, selected: DB値}, { multiple: true } %>
```

2:
```
<%= f.collection_select :カラム名, DB値, :id, :name, { include_blank: true, selected: DB値, multiple: true } %>
```

参考：https://github.com/rails/rails/blob/71c7fd101324046995d8f7e51e78475c0e37ec1a/actionview/lib/action_view/helpers/form_options_helper.rb#L788
