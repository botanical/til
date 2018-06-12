
### Ruby's Object Type Checker

To check the type of an object, or to check which class an object belongs to, use ```is_a?```. For example, checking if an object is an array would look similar to:
```Ruby
  ar = []
  if ar.is_a?(Array) then
    puts "Yes, it is an array"
  else
    puts "No, it is not an array"
```

This method can also check if an object belongs to  a superclass. More can be found [here](https://apidock.com/ruby/Object/is_a%3F).
