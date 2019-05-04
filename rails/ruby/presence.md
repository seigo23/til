## presenceメソッド（selfかnilを返す）
- `user.name.present? ? user.name : 'anonymous'`
- これは下みたいにできる
- `user.name.presence || 'anonymous'`
- 上記はuser.name.present?がtrueの時selfを返して、falseの時nilを返してくれる
- 表示するときに便利
- 参考：https://qiita.com/k-shogo/items/5bbc23e1d0dd0ad3a8a2
