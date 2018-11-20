### jest.doMock(module name, factory, options)

`jest.doMock()` takes in a `module name`, a `factory`, and `options` parameter. This method is useful when you want to
mock a function with the same module name in the same file or if you want to prevent a mocked module from affecting an
actual module with the same name. 

Here is an example of mocking two functions with the same module name:
```typescript
beforeEach(() => {
  jest.resetModules();
})

test('khaki 1', () => {
  jest.doMock('../khaki', () => {
    return jest.fn(() => "purr")
  });
  const khaki = require('../khaki')
  expect(khaki()).toEqual("purr")
})

test('khaki 2', () => {
  jest.doMock('../khaki', () => {
    return jest.fn(() => "meow")
  });
  const khaki = require('../khaki')
  expect(khaki()).toEqual("meow")
})
```

Here is an example of mocking a function with the same module name as another function being used in the file:
```typescript
beforeEach(() => {
  jest.resetModules()
})

test('khaki an unmocked test', () => {
  const khaki = require('../index')
  // and we are assuming that, in index.ts, khaki.talk() returns purr always...
  const result = khaki.talk() 
  expect(khaki()).toEqual("purr")
})

test('khaki a mocked test', () => {
  jest.doMock('../khaki', () => {
    return jest.fn(() => "meow")
  });
  const khaki = require('../khaki')
  expect(khaki()).toEqual("meow")
})
```
