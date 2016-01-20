## Get Better Performance from your App ##
Date: 2015-10-11<br>
Last Update: 2016-01-10

This will be cleaned up - soon. (2016-01-10)


Generally, the tips come in two varities.

1. Do this.
2. Don't do this.

### 1. Do this ###

* [Performance & UX Considerations For Successful PhoneGap Apps](http://www.tricedesigns.com/2013/03/11/performance-ux-considerations-for-successful-phonegap-apps/) - Andrew Trice - March 11, 2013 
 1. Hardware Acceleration
 2. The Impact of Content Reflow (7 points to analyze)
 3. Keep Graphics Simple
 4. Touch Interactivity (use touch events, not mouse)
 5. JavaScript Optimizations
 6. Native Performance
 7. UI & UX Considerations
 8. Test On Devices

### 2. Don't do this. ###

* [You half assed it. That is why your PhoneGap application sucks.](http://sintaxi.com/you-half-assed-it) - Brock Whitten - undated
 > Here are just a few rather obvious mistakes they make.
 
 1. Uses JQuery (and JQuery Mobile)
 2. Massive Footprint. 248k wowsers
 3. click instead of tap
 4. setTimeout animations

* [BazaarJS: our criticisms of Angular](http://www.leanpanda.com/blog/2015/09/20/our-criticisms-of-angularjs/) - Stefano Verna &ndash; September 20, 2015

- Problem #1: Scope inheritance and dynamic scoping
- Problem #2: Dirty checking
- Problem #3: Dependency injection
- Problem #4: Pointless complexity
- Problem #5: Server-side rendering


## Other DO THIS Articles ##

- [Minimizing browser reflow](https://developers.google.com/speed/articles/reflow?hl=en)

## Other Useful articles ##

- [Apache Cordova: after 10 months, I won't be using it anymore](http://geekcoder.org/apache-cordova-after-10-months-i-wont-using-it-anymore/) - July 06, 2015
- [ogv.js: An Ogg Theora and Vorbis Video Decoder in JavaScript](http://badassjs.com/post/71980473022/ogvjs-an-ogg-theora-and-vorbis-video-decoder-in) - January 2nd 2014
- [Top 10 Performance Techniques for PhoneGap and Hybrid Apps ? Slides Available](http://coenraets.org/blog/2013/10/top-10-performance-techniques-for-phonegap-and-hybrid-apps-slides-available/?utm_source=rss%26utm_medium=rss%26utm_campaign=top-10-performance-techniques-for-phonegap-and-hybrid-apps-slides-available) - October 30, 2013 by Christophe Coenraets
- [The Complete Guide to Building HTML5 Games with Canvas & SVG](http://www.htmlgoodies.com/html5/client/the-complete-guide-to-building-html5-games-with-canvas-svg.html) - undated, appears 2013
- [HTML5 vs Native: The Mobile App Debate](http://www.html5rocks.com/en/mobile/nativedebate/) - June 3rd, 2011 by Michael Mahemoff

## My notes from the documentation ##

### Tip #1 ###
With the Android [Webview](http://developer.android.com/reference/android/webkit/WebView.html) you can reduce screen flicker \*when changing orientation*, by reading below.

_Cookie and Window Management_

The standard behavior for an Activity is to be destroyed and recreated, when the device orientation or any other configuration changes. This will cause the WebView to reload the current page. **If you don't want that, you can set your Activity to handle the orientation and keyboardHidden changes**, and then just leave the WebView alone. It'll automatically re-orient itself as appropriate. Read Handling Runtime Changes for more information about how to handle configuration changes during runtime.



## Videos ##

### Responsive HTML5 Touch Interfaces ###

* Stephen Woods: "Creating Responsive HTML5 Touch Interfaces"
* http://yuiblog.com/blog/2012/02/23/video-stephen-woods-html5-touch/
* includes: swipe, snap back/forward, bounce, native scrolling, pinch to zoom + pro-tips.


## Unapplied/Unsorted ##

*Lodash, the JavaScript Library You're Already Using*<br>
http://www.infoq.com/news/2015/03/lodash-utility-library

> Though lodash is popular with node.js developers, it is also used by browser-based projects. Web developers can use the experimental build tool to cherry-pick which methods their project needs rather than downloading the entire library. For node.js projects, individual methods can be included when the whole package isn't needed.

*Comparing JavaScript Templating Engines: Jade, Mustache, Dust and More* - November 11, 2014<br>
https://strongloop.com/strongblog/compare-javascript-templates-jade-mustache-dust/

> Lets talk templates, specifically JavaScript powered templates. Even more specifically ? template engines that work as well on the server side as they do on the client side. 

*Templating Engines* (undated)<br>
http://jster.net/category/templating-engines

> These JavaScript templating engines allow you to perform string interpolation and then some using some specific templating syntax. Examples: mustache.js and Jade. 



