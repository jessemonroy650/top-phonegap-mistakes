### Current Tripping Points to Cordova/Phonegap ###
Date: 2015-10-18<br>
Last Update: 2016-01-10

## 1. *Phonegap Desktop App* causes problems for new comers. ##

*Phonegap Desktop App*, current version is [0.2.1](https://github.com/jessemonroy650/top-phonegap-mistakes/blob/master/history/phonegap-desktop.md) (as of 2015/12/22). It has the doubious distinction of having NO documentation. The little directions available come from the [Phonegap Developer App](https://github.com/jessemonroy650/top-phonegap-mistakes/blob/master/history/phonegap-desktop.md) and [THE phonegap tutorial](http://docs.phonegap.com/). 

The largest issue is [Step 5: Going Further](http://docs.phonegap.com/getting-started/5-going-further/). In this step, and afterwards, they do NOT inform people that using the framework work created with *Phonegap CLI* will NOT work with *Phonegap Build*.

## 2. *Phonegap Build* now supports the &lt;platform&gt; element ##

What's New

   * &lt;Platform&gt; tag - The platform tag, note the missing xml optional namespace, is now obeyed on Build.
   * Platform Specific Preferences - like version and orientation
   *  Splashscreens and Icons -Splashscreen and icons can now be used without the gap namespace as well. 

    http://phonegap.com/blog/2015/11/17/config_xml_update

## 3. Using `this` incorrectly, in the wrong context.

You are not using the `this` context correctly. This is a common mistake. The Javascript `this` does NOT work like the Java `this`.    

The reason it does not work is because the `this` gets resolved at **run-time**, not assemble-time (or compile-time). When the event fires, `this` resolves to the the global `this` because your app object is now out of scope. The event fires \*outside* of your `app` object.

A quick fix would be to do `app.onDeviceReady` instead of <s>`this.onDeviceReady`</s> You can test this by making your `onDeviceReady()` a global function and leaving the `this` in place.

OHH, and any `setTimeout()` answer that anyone has given you does not know they need to wait for the `deviceready` event. Bad code and bad advice abound in the Javascript world. 

These videos should help. ? Best of Luck.

- [Context in JavaScript - 1/4 - Purpose and Problems with JavaScript's "This"](https://www.youtube.com/watch?v=su-SdgebJCE)
- [Context in JavaScript - 2/4 - How JavaScript Decides What "This" Actually Is](https://www.youtube.com/watch?v=hJ_YD4Ljbqc)
- [Context in JavaScript - 3/4 - "This" May Not Be What You Expected & How to Fix It](https://www.youtube.com/watch?v=PNqoehDEZ3E)
- [Context in JavaScript - 4/4 - Mastering "This:" Additional Techniques & Future Support](https://www.youtube.com/watch?v=QQ4__W9nELc)






