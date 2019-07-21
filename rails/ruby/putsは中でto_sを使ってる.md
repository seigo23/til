## putsの注意点

- 下記の時、インスタンス情報ではなくto_sの内容が呼ばれる。
- ここではputsのto_sがオーバーロードされてしまってるため。
- 参考をみたらわかる。
```ruby
class Robot
  def initialize(name)
    @name = name
    @x = @y = 0
  end

  def move(x,y)
    @x += x; @y += y
  end

  def to_s
    "{@name}: #{@x}, #{@y}"
  end
end

robo1 = Robot.new("1gou")
robo2 = Robot.new("2gou")
puts robo1 #=> 1gou: 0, 0
robo2.move(10, 20)
puts robo2 #=> 2gou: 10, 20

```

- 参考：http://ihatov08.hatenablog.com/entry/2016/06/21/115637
- 参考：https://www.task-notes.com/entry/20141109/1415520719#puts
