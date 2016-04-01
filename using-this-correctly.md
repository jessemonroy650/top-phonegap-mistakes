# using-this-correctly #
Date: 2016-01-10 <br>
Last Update: 2016-04-01

## Using `this` correctly, requires knowing the context. ##

Often people use the `this` incorrectly. This is a common mistake. The Javascript `this` does NOT work like the Java `this`, nor like most computer languages.    

The reason it does not work is because the `this` gets resolved at **run-time**, not assemble-time (or compile-time). When an event fires, `this` resolves to the global `this` because the function is now out of scope.

These videos should help.

**Videos by Adam Breindel**
- [Context in JavaScript - 1/4 - Purpose and Problems with JavaScript's "This"](https://www.youtube.com/watch?v=su-SdgebJCE) 10 minutes
- [Context in JavaScript - 2/4 - How JavaScript Decides What "This" Actually Is](https://www.youtube.com/watch?v=hJ_YD4Ljbqc) 4 minutes
- [Context in JavaScript - 3/4 - "This" May Not Be What You Expected & How to Fix It](https://www.youtube.com/watch?v=PNqoehDEZ3E) 7 minutes
- [Context in JavaScript - 4/4 - Mastering "This:" Additional Techniques & Future Support](https://www.youtube.com/watch?v=QQ4__W9nELc) 6 minutes

- [Scope and this in JavaScript](http://javascriptplayground.com/blog/2012/04/javascript-variable-scope-this)
- [Understanding Scope and Context in JavaScript](http://ryanmorr.com/understanding-scope-and-context-in-javascript/)
