#### Ruby's attr_reader

`attr_reader` is a Ruby method that you can use to share instance variables instead of creating many getter methods. 

Here is an example of it's utility in depth:

Imagine you had a class definition of a Cat

```Ruby
# cat.rb
class Cat
  def initialize(name)
    @name = name
  end
end

rescue = Cat.new("Khaki")
puts rescue.name # => undefined method name

```

In order to access the name of the Cat, you need to create a getter method called `name`

```Ruby
# cat.rb
class Cat
  def initialize(name)
    @name = name
  end
   
  def name
    @name
  end
end

rescue = Cat.new("Khaki")
puts rescue.name # => Khaki

```

`attr_reader` is useful because it takes away the need to write many getter methods if you have more variables.

So, with `attr_reader` this is the new code

```Ruby
# cat.rb
class Cat
  attr_reader :name, :age, :color, :breed
  def initialize(name, age, color, breed)
    @name = name
    @age = age
    @color = color
    @breed = breed
  end
end

rescue = Cat.new("Khaki", 1, "Cream", "Tabby")
puts rescue.name # => Khaki

```
