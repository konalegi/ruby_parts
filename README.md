
* What is main identifiers in ruby?

```Text
  # Variables
    - Local
    - Instance (@)
    - Class (@@)
    - Global ($)
  # Constants
  # Keywords
  # Method Names
```

### Method Arguments
  * What will be meaning of a,b,c,d,e?

    ```Ruby
      def args_test(a,b=1,*c,d,e)
        puts "Arguments:" p a,b,c,d,e
      end
      args_test(1,2,3)
    ```

  * Is it work? Why?

  ```Ruby
    def args2(x,*y,z=1)
      p x, y, z
    end
  ```

  * What output will be?

  ```Ruby
    def args_test(x,b)
      p x, b
    end

    args_test(1, a:1, b:2, c:3)
  ```

```Ruby
  a = :text
  b = :text
  p a == b
  p a.object_id == b.object_id

  a = 'text'
  b = 'text'
  p a == b
  p a.object_id == b.object_id
```


```Ruby
  class B
    def self.say_hello
      p 'say hello from B'
    end
  end

  class C < B
    def B.say_hello
      p 'say hello from C'
    end
  end

  B.say_hello
```

```Ruby
module A
  def say_hello
    p 'hello from A'
  end
end
module B
  def say_hello
    p 'hello from B'
  end
end
class C
  include A
  include B
  include A
end
C.new.say_hello
```

```Ruby
class A
  def say_hello
    @v = 'i am variable V1'
    p @v
  end
  @v = 'i am variable V2'
end
A.new.say_hello
```

```Ruby
class A
  @v = 'i am variable AV1'
  def set_variable
    @@v = 'i am variable AV2'
  end
  def get_variable
    @@v
  end
end
class B < A
  @v = 'i am variable BV1'
  def set_variable
    @@v = 'i am variable BV2'
  end

  def get_variable
    @@v
  end
end
p B.instance_variable_get(:@v)
p A.instance_variable_get(:@v)
p '---------'
A.new.set_variable
p B.new.get_variable
p '--------'
p A.class_variable_get(:@@v)
```

```Ruby
# mylibrary.rb

class MyLibrary
  puts "I was loaded!"
end

##

irb(main):001:0> require 'mylibrary'

irb(main):001:0> autoload :MyLibrary, 'mylibrary'
```

```Ruby
# which one will fail in Rails?

irb(main):001:0> (1..42).to_a.forty_two
irb(main):001:0> (1..42).to_a.forty_one
irb(main):001:0> (1..42).to_a.forty

```

```Ruby
module MyModule
  class << self
    def say_hello
      p 'Hello'
    end
  end
end

MyModule.say_hello
```

MyModule.say_hello

