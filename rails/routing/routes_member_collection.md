## ルーティングのmemberとcollection
- 詳細は後半に書いてる

### 結論：下記でハマった。
- こんな感じでmemberとかcollectionとか入れずにresourcesに直接ブロッック渡したら自動的にmember扱いとなって、特定のデータしか扱えなくなること。
- 何も指定しなかったらresourcesにいい感じにルーティング足されるやろうと思ってた。
```ruby
resources :books do
  post :search
end
```
- 下記詳細

- `post :search ,on: :collection`みたいに 使えば1行で書ける

- `member`はresourcesでいうshowとかeditとかの`:id`で取るみたいに特定の一つのデータに対するもの

- `collection`は複数のデータに対するもの

- 参考に全て載ってるけど下記みたいに使う。
```ruby
resources :books do
  collection do
    post :search
    post :remove_multi
  end
  member do
    get :thumbnail
    get :sample_file
  end
end
```

参考：http://techblog.kyamanak.com/entry/2017/08/12/155914
参考：https://techracho.bpsinc.jp/baba/2014_03_03/15619
