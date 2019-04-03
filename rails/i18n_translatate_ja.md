## gem: i18n_generatorsについて
- を入れた状態で`rails g i18n ja`をすると、下記ファイルができる
  - `config/locales/ja.yml`
  - `config/locales/translation_ja.yml`
- この`config/locales/translation_ja.yml`がモデルと結びついてる
- `config/locales/translation_ja.yml`になかったら次は`config/locales/ja.yml`を探しに行くみたいになってるっぽい


- とにかく、フォームのlabelとかで`body`を`体`とか`name`を`名`って訳したりしてるってことは絶対にどこかで定義されてるはずなので、まずはグレップして、現状どこのlocaleファイルを見てるか確認すること


```yaml
# config/locales/translation_ja.yml
# 下記がモデル名の設定

ja:
  activerecord:
    models:
      user: ユーザ
      
# 下記がアトリビュート（カラム名）の設定
    attributes:
      user:
        id: 'ID'
        name: '名前'
        email: 'メールアドレス'
    
```
