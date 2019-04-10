##  etc/hostsの使い方
- ローカルでのDNSの役割
- 自分で何も設定してないのに`localhost`が認識されるのはここに設定されてるから。
- 下記がデフォルトで入ってる

```
127.0.0.1       localhost
255.255.255.255 broadcasthost
::1             localhost
```

- 例えばここに下記を追加したらaaa.comとbbb.comが127.0.0.1（つまりローカルホスト）に変換される

```
127.0.0.1 aaa.com bbb.com
```

- 参考：https://wa3.i-3-i.info/word11760.html
