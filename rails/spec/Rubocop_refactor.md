## Rubocopで怒られたやつ

### 三項演算子じゃなくてダブルパイプ使えよ！パターン
例えばなんかハッシュとかに代入するときに、

- ダメな例
```ruby
{ is_valid: params[:is_valid] ? params[:is_valid] : false }
```


- 良い例
```ruby
{ is_valid: params[:is_valid] || false }
```

左から順に入れられて、ダメだった次って感じの動きになるので `||`を使うこと
