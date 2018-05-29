### Ruby's Freeze Method

Ruby's `freeze` method prevents any further modification to an existing object. Trying to modify a frozen object will result in a Runtime Error. Additionally, a frozen object cannot be unfrozen. Here is an example:

```ruby
   x = ["Kody", "Dody", "Toby"]
   x.freeze
   x << "Jody"
```
produces:
```ruby
   test.rb:3:in `<<': can't modify frozen array (RuntimeError) from test.rb:3
```

