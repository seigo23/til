## 新プロジェクトへの参加手順
- cloneしたらどのブランチから切るとかがややこしくなるので下記が良さそう

- まずPJ置く場所で`git init`

- もし自分のアカウント使えないとしたら公開鍵とかめんどくさいのでsshではなく`https`で、招待されたアカウント名を入れて`remote add`する（`https://my_user_name@github.com/...`みたいな）

- `remote add`したらまず`fetch`する

- そのタスクの進め方がdevelop→派生ブランチ（feature/XX_#123）→developへのPR→レビュー→マージという流れの場合

- ※この段階では`git branch`で何も標準出力に出ない

- `git branch -a`でリモート追跡情報が取れているのを確認

- `git checkout -b develop origin/develop`で純粋なリモートブランチをローカルブランチに移す

- カレントブラントがdevelopになってるので、その状態で`git checkout -b feature/XX_#123`

- ここから作業を開始する

- ※もしRubymineとかidea系のやつ使ってる場合は、.gitignoreに`/.idea`を追加しとく

  
