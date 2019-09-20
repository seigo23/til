## seedの綺麗な書き方
- app/db/seeds.rbの中にあんまり複雑な処理をかくとややこしくなる
- だから、複雑になっちゃう処理は`app/db/fixtures/xxxx.rb`みたいにファイルを切り分ける
- そして、seeds.rbから`require Rails.root.join("db", "fixtures", "xxxx.rb")'`みたいにしてその処理を書いたファイルを呼び出す
- xxxx.rbにはやりたい処理をそのまま書く`(User.find_or_create_by!(name:"田中"...))`みたいな感じ
参考：https://qiita.com/masaki7555/items/d65f56958020cbca5ee0
