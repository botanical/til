
### Ruby's Count Method for Strings

The count method for strings takes in a string: `count([some_str])` and `some_str` defines the set of characters to count in a given string. The intersection of the sets defines the characters to count in the given string. Here is an example:

```Ruby
l = "hello code monkey!"
l.count "lo" #=> 5
l.count "loe" #=> 8 
l.count("lo","o") #=> 3 
