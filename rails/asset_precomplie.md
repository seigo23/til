## プリコンパイルできない時の対処
- `bundle exec rake assets:precompile RAILS_ENV=production`でプリコンパイルしたファイルがあるpublic/assetsが作られる
- もしプリコンパイルがうまく動作しない場合は、すでに最新のデータでプリコンパイルが終わってる可能性があるので、sshで入る先が間違ってないか確認する
- 本番データをプリコンパイルしたいのにssh入る先がテスト環境になってて詰まった。
- あと、プリコンパイル下データを削除するには下記のコマンド
- `bundle exec rake assets:clobber RAILS_ENV=staging`でpublic/assetsを削除する
- 参考：https://qiita.com/metheglin/items/c5c756246b7afbd34ae2
