# using-this-correctly #
Date: 2016-01-10 <br>
Last Update: 2016-01-20

## Using `this` correctly, requires knowing the context. ##

Often people use the `this` incorrectly. This is a common mistake. The Javascript `this` does NOT work like the Java `this`, nor like most computer languages.    

The reason it does not work is because the `this` gets resolved at **run-time**, not assemble-time (or compile-time). When the event fires, `this` resolves to the the global `this` because your app object is now out of scope. The event fires \*outside* of your `app` object.

A quick fix would be to do `app.onDeviceReady` instead of <s>`this.onDeviceReady`</s> You can test this by making your `onDeviceReady()` a global function and leaving the `this` in place.

OHH, and any `setTimeout()` answer that anyone has given you does not know they need to wait for the `deviceready` event. Bad code and bad advice abound in the Javascript world. 

These videos should help. ? Best of Luck.

- [Context in JavaScript - 1/4 - Purpose and Problems with JavaScript's "This"](https://www.youtube.com/watch?v=su-SdgebJCE)
- [Context in JavaScript - 2/4 - How JavaScript Decides What "This" Actually Is](https://www.youtube.com/watch?v=hJ_YD4Ljbqc)
- [Context in JavaScript - 3/4 - "This" May Not Be What You Expected & How to Fix It](https://www.youtube.com/watch?v=PNqoehDEZ3E)
- [Context in JavaScript - 4/4 - Mastering "This:" Additional Techniques & Future Support](https://www.youtube.com/watch?v=QQ4__W9nELc)
