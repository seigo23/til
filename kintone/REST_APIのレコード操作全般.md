## REST_APIのレコード操作全般

- レコード取得
```js

// app アプリID
// query レコード抽出条件。「order by」で並び替えや、limit、offsetなども利用可
// fields レスポンスに含めるフィールドコード(以下例では省略しているので全フィールドが返ってきます)
var param = {
    "app": 1,
    "query": "updated_time > \"2012-02-03T09:00:00+0900\" order by $id asc limit 10 offset 20"
};

kintone.api(kintone.api.url('/k/v1/records', true), 'GET', param, function(resp) {
    // 成功時の処理
    console.log(resp);
}, function(error) {
    // エラー時の処理
    console.log(error);
});
```

- レコード取得
```js
// app アプリID
var param = {
    "app": 1,
    "records": [
        {   // 1件目のレコード
            "お客様名": {
                "value": "山田太郎"
            },
            "住所": {
                "value": "東京都港区"
            }
        },
        {   // 2件目のレコード
            "お客様名": {
                "value": "鈴木花子"
            },
            "住所": {
                "value": "東京都渋谷区"
            }
        }
    ]
};

kintone.api(kintone.api.url('/k/v1/records', true), 'POST', param, function(resp) {
    // 成功時の処理
    console.log(resp);
}, function(error) {
    // エラー時の処理
    console.log(error);
});
```


- レコード更新(1件)
```js
// app アプリID
// id レコード番号
var param = {
    "app": 1,
    "id": 10001,
    "record": {
        "お客様名": {
            "value": "山田次郎"
        },
        "住所": {
            "value": "東京都港区虎ノ門"
        }
    }
};

kintone.api(kintone.api.url('/k/v1/record', true), 'PUT', body, function(resp) {
    // 成功時の処理
    console.log(resp);
}, function(error) {
    // エラー時の処理
    console.log(error);
});

```
- 参考：http://chobi-tech.com/kintone-api-matome/
