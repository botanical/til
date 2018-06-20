#### Recognizing Dependencies

When writing code, it is best to avoid making an object depend on another. An object has a dependency if:
1. the object knows the name of another class
2. the object expects a different `Class` instance other than `self` to respond to a method
3. the object knows the parameter requirements of a method from a different class
