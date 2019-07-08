## skip_before_actionについて
- ApplicationControllerで`before_action: :require_login` みたいにした時、ログイン画面はどうするんやろと思ってたけど、そう言う時のためにskipできるやつがある
- 個人で作ってた時は確かbefore_actionするんじゃなくてApplicationControllerで定義したやつを全部のコントローラから呼んでた気がする。（記載漏れあり得るしだめ）
- ApplicationControllerのbefore_actionで定義することで外したい時は明示的にしないとダメになるので絶対こっちの方がいい 
- 参考：https://railsguides.jp/action_controller_overview.html#%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF
