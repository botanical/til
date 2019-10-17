#### Ruby's attr_reader

A getter method in Ruby retrieves the value  of an instance variable from an object. They are useful when you want to retrieve a value and perform an additional computation with that value. If you simply want to retrieve the value, however, there is a better alternative: **attr_reader**!

`attr_reader` is a Ruby method that you can use to share instance variables. Using `attr_reader` is especially useful when you want to read the values of a Class that has many instance variables

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
