#### Rest Parameters

A Rest Parameter in your function is denoted by `...arg` and allows you to use an indefinite number of arguments
as an array. Here is an example:

```typescript
function eatYourVegetables(one, two, ...next) {
 console.log(next)
}

eatYourVegetables("cabbage", "carrot") // []
eatYourVegetables("cabbage", "carrot", "potato", "celery", "onion", "green onion") // ["celery", "onion", "green onion"]
```
