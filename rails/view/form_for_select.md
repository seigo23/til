## for_forでのセレクトボックス 
- 下記みたいな感じ
- f.select ラベル名（ransack使うときは命名注意） 選択肢と値を配列で入れる オプションって感じ

```ruby
 <%= f.select :user_role_eq, [['一般ユーザ',1],['スーパーユーザ',9]], {include_blank: "ユーザを選択"}, {autofocus: 'true', class: '任意のクラス名'}%>

```

