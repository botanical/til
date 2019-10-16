#### Ruby's attr_reader

`attr_reader` is a Ruby method that you can use to share instance variables instead of creating many getter methods. 

Here is an example of it's utility in depth:

Imagine you had a class definition of a Cat

```Ruby
# cat.rb
class Cat
  def initialize(name, age, color, breed)
    @name = name
    @age = age
    @color = color
    @breed = breed
  end
end

cat = Cat.new("Khaki", 3, "Cream", "Tabby")
puts cat.name # => undefined method name

```

In order to access the name, age, breed, or color of the Cat, you need to create getter methods for `name`, `age`, `breed`, and `color` like this:

```Ruby
# cat.rb
class Cat
  def initialize(name)
    @name = name
  end
   
  def name
    @name
  end
  
  def age
    @age
  end
  
  def breed
    @breed
  end
  
  def color
    @color
  end
end

cat = Cat.new("Khaki", 3, "Cream", "Tabby")
puts cat.name # => Khaki

```

`attr_reader` is useful because it takes away the need to write many getter methods if you have more variables.

So, with `attr_reader` this is the new code:

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

cat = Cat.new("Khaki", 1, "Cream", "Tabby")
puts cat.name # => Khaki

```
