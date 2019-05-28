# showの時のpath
- `users_path(@user)`ではなく`user_path(@user)`なので注意
- showの時は単数形でindexの時は複数形なので注意
- user_path(@user)やのに、生成されるのが`users/1`とかで複数形やから混乱した。
- 参考：https://railsguides.jp/routing.html#%E3%83%91%E3%82%B9%E3%81%A8url%E7%94%A8%E3%83%98%E3%83%AB%E3%83%91%E3%83%BC
