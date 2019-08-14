## webAPIでのCSVの扱い
- 今はだいたいjsonやけどちょっと前のやつは普通にcsvも使ってたりする
- その場合はリクエストヘッダのmimetypeを指定して圧縮して送る
- そして向こうで解凍してparseして使うイメージ
- 参考：https://qiita.com/mserizawa/items/7f1b9e5077fd3a9d336b#%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AE%E9%80%81%E4%BF%A1%E6%96%B9%E6%B3%95
