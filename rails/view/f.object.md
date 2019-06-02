# f.objectとは
- そもそもform_forのブロック変数`f`はフォームのインスタンスらしい
- ほんで、`form_for(@user)`とかってよくやるけど、この場合のf.objectは@userと同じ
- @userやと@userのインスタンス変数名が変わった時にだるいから`f.object`としてるだけみたい。
- 参考：https://mon-sele.com/post18/
