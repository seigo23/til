## allocate
- インスタンスをinitializeなしで作りたい時に使う
- newのinitializeをスキップするバージョン
```ruby
class Cat
  attr_accessor :name
  def initialize
    @name = "NoName"
  end
end

cat1 = Cat.new
p cat1.name # "NoName"
cat2 = Cat.allocate
p cat2.name # nil

```
- 参考：https://qiita.com/hc0208/items/45cce0f3f3c843c03c01
