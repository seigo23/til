## curlでリクエストヘッダを複数つける方法
- 下記がkintoneをちょっと意識した適当な例（トークンとかは適当なやつ）
- `curl -H 'API-TOKEN:XKsefNKdafnrxZNetokun' -H 'X-Requested-With:HtpRuest' http://someurl?query=limit 500&id=2`
- 参考：https://qiita.com/youcune/items/45271a32dccb7498033f#%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%83%98%E3%83%83%E3%83%80%E3%82%92%E6%8C%87%E5%AE%9A%E3%81%99%E3%82%8B
