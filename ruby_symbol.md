
### Ruby's Symbols

Symbols in Ruby are objects that look like variables that are prefixed with a colon `:`. For example, this is a symbol in ruby: `:sym`. Symbols are often used in Ruby as keys to a hash. Symbols are immutable and, in Ruby, a symbol is more like a string than a variable. The main difference is that symbols will only be created once and point to the same area in memory. Here is an example:


``` ruby
a = :a_sym
b = :a sym

c = "a sym"
d = "a sym"
```
In this example, a and b point to the same place in memory whereas c and d will point to different areas in memory. 
