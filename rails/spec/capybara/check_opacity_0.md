## Capybaraでチェックボックス選択時の注意
- cssで透過設定（opacity:0;）されてる時、`check "id名" , visible: false`ってしないとだめ
- ハマったところは、画面上では透過されてる感じもなく普通に見えてるのに`visible:false`を入れないとダメなとこ
