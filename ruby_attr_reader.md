## Ruby's attr_reader and attr_writer

### Getter Methods and Setter Methods
Getter methods are used to retrieve the value of an instance variable from an object and Setter methods are used to set the value of an instance variable. In many languages, you can read and write the value of an instance variable directly but in Ruby you have to specify a getter and setter

For example, let's say you have a Ruby program with a `class Cat` and you create a new instance of Cat attached to a variable `tabby`:
```Ruby
class Cat
  def initialize(name)
    @name = name
  end
end

tabby = Cat.new('Telemakhos') #=> #<Cat:0x00007fe3cd10ebc8 @name="Telemakhos">
puts tabby.name #=> NoMethodError (undefined method `name' for #<Cat:0x00007fe3cd10ebc8 @name="Telemakhos">)
```
If you try to access the name of the cat, as you can see from above, you will get a `NoMethodError`. In order to access the name of the cat or set the name, you must create a **Getter** and **Setter** method like below

```Ruby
class Cat
  def initialize(name)
    @name = name
  end

  def name #getter method
    @name
  end
  
  def name=(name) #setter method
    @name = name
  end
end

tabby = Cat.new('Telemakhos')
puts tabby.name #=> "Telemakhos"
```

Now imagine if you had more properties to a Cat than just `name`
```Ruby
class Cat
  def initialize(name, age, breed, weight)
    @name = name
    @age = age
    @breed = breed
    @weight = weight
  end
end
```
If you wanted to **get** or **set** any of those properties, it would require *eight* more getter and setter methods!

### There is a better alternative: **attr_reader** and **attr_writer**!

`attr_reader` and `attr_writer` are Ruby methods that can be used to replace getter and setter methods and mimic the accessing of instance variables seen in other languages such as TypeScript. Using `attr_reader` and `attr_writer` is especially useful when you want to read and manipulate the values of a Class that has many instance variables

Here is an example of it's utility in depth:


```Ruby
# cat.rb
class Cat
  attr_reader :name, :age, :breed, :weight
  attr_writer :name, :age, :breed, :weight
  def initialize(name, age, breed, weight)
    @name = name
    @age = age
    @breed = breed
    @weight = weight
  end
end

cat = Cat.new("Julie", 3, "Tabby", 8)
puts cat.name # => "Julie"
puts cat.age # => 3
puts cat.breed # => "Tabby"
puts cat.weight # => 8
cat.weight = 10
puts cat.weight # => 10

```

In conclusion, `attr_reader` and `attr_writer` can replace a bunch of getter and setter methods in just a single line!
