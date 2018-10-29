### Typescript's Arrow Function

`=>` is also called the `fat arrow` ( and `lamdba function` in other languages ) and is useful because it makes writing
 functions easier.
 
 If you need to use an arrow function to return an object, you need to surround the object literal with parenthesis `()`
 to avoid getting an error:

Example:
```typescript
var dog = () => ({
  say: "bark"
})
```
