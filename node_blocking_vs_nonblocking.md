#### Blocking vs Nonblocking I/O

In **blocking**, while we are fetching from out application,
it cannot do anything else. In other words, *blocking
occurs when the execution of javascript in the Node.js process
needs to wait until a non-javascript operation completes*.

**Blocking** methods execute *synchronously* (in order) whereas **nonblocking**
methods execute *asynchronously*. Using nonblocking doesn't
make our operations faster but it lets us execute multiple
functions at a time. The non-blocking version is faster in
total execution time.
