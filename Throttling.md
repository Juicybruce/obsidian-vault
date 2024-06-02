Throttling simply doesn't allow a function to be called more than once every *x* milliseconds.

The main difference between this and [[Debouncing]] is that throttle guarantees the invocation of the function regularly, **at least** once every *x* milliseconds

##### Use Cases 

##### Infinite scrolling
Here debounce wont be useful as we want the checks (and possible fetch) to happen **before** the user stops scrolling, but we want to limit the scroll triggers

