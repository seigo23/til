## yarnで入れたライブラリをRailsで使う方法

- すでにyarnが入ってる場合は`yarn add モジュール名`でモジュールをプロジェクトに入れる

- プロジェクトrootに`node_nodules`っていうディレクトリがあって、その中にモジュールが入ってる

- `application.js`に読み込みたいモジュールのJSファイルのパスで`require`する

- `application.css`に読み込みたいモジュールのcssファイルのパスで`inport`する

あとはそれぞれのモジュールの使い方に合わせて使う
