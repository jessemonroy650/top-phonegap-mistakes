# javascript-engines #
Date: 2015-11-14
Last Update: 2015-11-14


| OS      | Javascript engine |
|---------|-------------------|
| iOS     | JavaScriptCore    |
| Android | V8?               |


## Available Javascript Engines<sup>1</sup> ##

- Rhino - The most popular JavaScript Engine developed in Java, originally by Netscape, but now maintained by Mozilla. Unfortunately, its development is not very active, documentation at some points is inadequate and outdated, and the API is not very elegant.
- Nashorn - Another JavaScript engine developed in Java by Oracle. It was released along with Java 8 a few days ago. Oracle has open-sourced the project, but unfortunately, it cannot run on Android?s Dalvik VM.
- V8 - The JavaScript engine developed in C++ by Google, which powers the Chrome and Chromium web-browsers, and other projects like node.js. Open-source project.
- SpiderMonkey - The first-ever JavaScript engine developed in C/C++, originally by Netscape, and now maintained by Mozilla. It powers the Firefox web-browser. Open-source project.
- JavaScriptCore (the JavaScript engine, not the iOS framework) - The JavaScript engine developed in C/C++ by Apple, Adobe and others, which powers the Safari web-browser (among others). It?s part of the WebKit framework. Open-source project.


### Articles ###

- [Android: Your JS Engine is not always V8](http://phonegap.com/2011/01/14/android-your-js-engine-is-not-always-v8/) - 14 Jan 2011
    - WebKit is different on every phone
    - The Browser and the WebKit engine are different things.
    - WebKit can have a different engine

- [Nitro JavaScript Engine in iOS PhoneGap Apps](phonegap-tips.com/articles/nitro-javascript-engine-in-ios-phonegap-apps.html) - June 8, 2013 (date by archive.org)

- [Part I: How to Choose a JavaScript Engine for iOS and Android Development](http://openaphid.github.io/blog/2013/01/17/part-i-how-to-choose-a-javascript-engine-for-ios-and-android-apps/) - Jan 17th, 2013

- [10 very good reasons to stop using JavaScript](https://www.leaseweb.com/labs/2013/07/10-very-good-reasons-to-stop-using-javascript/) - 2013/07/10
    1. JavaScript hurts your mobile visitors
    2. JavaScript hurts your robustness
    3. JavaScript hurts your security (and your privacy)
    4. JavaScript hurts your SEO
    5. JavaScript hurts your development time
    6. JavaScript hurts your testing costs
    7. JavaScript hurts your website performance
    8. JavaScript hurts your software investment
    9. JavaScript hurts your software architecture
    10. JavaScript is not needed


### References ###

1. [JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine)
2. [V8 (JavaScript engine)](https://en.wikipedia.org/wiki/V8_%28JavaScript_engine%29)
3. [Developing a mobile cross-platform library - Part 3. JavaScript](http://www.skyscanner.net/blogs/developing-mobile-cross-platform-library-part-3-javascript) - 25 March 2014

> Unfortunately, in Android, there is no such cool framework like JavaScriptCore, so we have to embed a JavaScript engine ourselves. The alternatives are

4. [Part I: How to Choose a JavaScript Engine for iOS and Android Development](http://openaphid.github.io/blog/2013/01/17/part-i-how-to-choose-a-javascript-engine-for-ios-and-android-apps/) - Jan 17th, 2013
