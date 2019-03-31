## BFFがSSRを担当するサーバ
- SSRはあくまでBFFの一部の機能で、APIを束ねたりする機能もBFFにはある
- BFF=Backends For Frontends
- SPAでSSRはありえる。
- SPAで最初のレンダリングをSSRサーバで行う。
- SPAフレームワークのVueとかReactとかで使うSSRフレームワーク、NuxtとかNextとかは最初の1回だけSSRサーバでSSRして、そのあとはフロントでJSで書き換えてる
- Nuxtを使ったからと言ってブラウザ依存関連の問題が全部解決できるわけではない。（初期読み込み時はSSRするのでただのSPAより速くなる）
- ファーストビューに必要なCSSとかだけ取ってくるとかもあって、そういうファーストビューに必要なものをクリティカルパスという
 

参考：https://www.atmarkit.co.jp/ait/articles/1805/18/news022.html
