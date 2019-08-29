## 標準出力にSQLを出す方法
- Rails コンソールで`ActiveRecord::Base.logger = Logger.new(STDOUT)`を打てばいい
- 参考：https://blog.fakiyer.com/entry/2015/07/14/194824
