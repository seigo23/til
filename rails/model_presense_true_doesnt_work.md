# 項目を渡してるのにmust existになる時
- だいたい、新しい項目をフォームに足した時に起こる
- コントローラ側でパラメータを許可してないから、サーバ側に送れてるけど消されてる
- んで、belongs_to入れてたら勝手に必須になるから、サーバ側に送れてる（Viewの記述は間違ってない）けど、コントローラ側でパラメータが弾かれて、nullみたいな扱いになるから、入れろって言われる。
- あの`must exist`とかは、view側で判断してるんじゃなくて、サーバ側で一回判断してから出てるっぽいから注意（仕様によるかもやけど）
参考：https://teratail.com/questions/123791
