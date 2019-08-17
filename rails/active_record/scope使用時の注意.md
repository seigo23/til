## scope使用時の注意
- user has_many tweets の場合、
- userモデル内で、`scope :user_all_tweets, -> { self.tweets.order(:id).first }`みたいなのを定義した場合、
- このscopeのレシーバはuserが配列で来ることを想定してないので注意
- てかそもそもインスタンスメソッドをscopeで定義できない？
