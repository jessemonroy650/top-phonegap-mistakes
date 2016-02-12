## Top Mistakes by Developers new to Cordova/Phonegap ##
DATE: 2015-10-18<br>
LAST UPDATE: 2015-12-12

<a href=#001>1</a>
<a href=#002>2</a>
<a href=#003>3</a>
<a href=#004>4</a>
<a href=#005>5</a>
<a href=#006>6</a>
<a href=#007>7</a>
<a href=#008>8</a>
<a href=#009>9</a>
<a href=#010>10</a>
<a href=#011>11</a>
<a href=#012>12</a>
<a href=#013>13</a>

###<a name=001>1.</a> Thinking Phonegap is just one system ###

  There are three similar platforms, Cordova (CLI), Phonegap (CLI), and Phonegap Build and five system (counting Cordova/Phonegap SDK<sup>[1](#footnotes)</sup>). People often confuse the three very similar platforms and get tangled in the minor variations that differentiate them.

  Oddly enough, the best explanation comes from something built on top of Angular, and wraps the Cordova/Phonegap CLI. - *Ionic*.

  From the Ionic Blog *[The Last Word on Cordova and PhoneGap](http://blog.ionic.io/what-is-cordova-phonegap/)*
  > PhoneGap proper was created around 2009 by a startup called Nitobi as an open source way to access the "native" environment through an embedded Web View in a native app. The goal of the project was to make it possible to build the bulk of a mobile app experience with pure web technologies like HTML5, CSS, and Javascript, but still be able to call into native code when necessary.
  >
  > In 2011 Adobe purchased Nitobi and with it the rights to the PhoneGap brand, and the open source core was donated to the Apache Software Foundation under the name Cordova.
  >
  > Read more on the *[Ionic Blog](http://blog.ionic.io/what-is-cordova-phonegap/)*

  On the **Cordova/Phonegap SDK (or IDE)** &ndash; for all intensive purposes, these are the same as *Cordova/Phonegap CLI*, with an extra step involving [`config.xml`](http://cordova.apache.org/docs/en/5.0.0/config_ref_index.md.html#The%20config.xml%20File_the_feature_element). The SDK is used for IDEs including, but not limited to Android Studio, Visual Studio, Intel XDK, IntelliJ IDEA 14, Eclipse/THyM, Mobile First, Corona SDK.

  In addition, this leads to reading the wrong docs for the wrong platform. A common mistake for *Phonegap Build* is to use the [*Cordova* construct](http://cordova.apache.org/docs/en/5.1.1/config_ref/index.html) of <s>`<platform>`</s> and `<feature>`. As of today (2015-11-17), `<platform>` is supported by *Phonegap Build* [SEE](http://phonegap.com/blog/2015/11/17/config_xml_update)

  **The Official Websites**

  * [Cordova](http://cordova.apache.org/)
  * [Phonegap](http://phonegap.com/)
  * [Phonegap Build](https://build.phonegap.com/plans)

  *Blog Posts Related to #1*
  * [Cordova vs. PhoneGap: An update](http://blog.devgeeks.org/post/73789983750/cordova-vs-phonegap-an-update) - Jan 19, 2014 - devgeeks.org
  * [PhoneGap, Cordova, and what's in a name?](http://phonegap.com/2012/03/19/phonegap-cordova-and-what%E2%80%99s-in-a-name/) - 2012/03/19 - phonegap.com

###<a name=002>2.</a> Does not read the docs. ###
  There are three (3) sets of docs. One for *Cordova CLI* (Command Line Interface), another for *Phonegap CLI*, and one for *Phonegap Build*. They are similar, but NOT the same. Also, to add to the confusion, sometimes the Cordova documentation is the only set of docs available; this happens for some plugins. This also happens with Phonegap &ndash; the Phonegap Developer's Guide for example. (aka Beginners Guide)

  **The Official Documentation**
  * [Cordova](http://cordova.apache.org/docs/en/3.0.0/)
  * [Phonegap Beginner's Guide](http://docs.phonegap.com/) & [Phonegap 3.0.0](http://docs.phonegap.com/en/3.0.0/) (older,but sometimes better)
  * [Phonegap Build](http://docs.build.phonegap.com/en_US/#googtrans%28en%29)

###<a name=003>3.</a> Does not follow the blogs.###

  All three platforms have blogs and twitter accounts. **Ignore at your peril.**
  * Official Apache [Cordova Blog](http://cordova.apache.org/blog/) - https://twitter.com/apachecordova
  * Official Adobe [Phonegap Blog](http://phonegap.com/blog/) - https://twitter.com/phonegap
  * Official Adobe [Phonegap Build Blog](http://phonegap.com/blog/phonegap-build/) - https://twitter.com/phonegapbuild

###<a name=004>4.</a> In the code, did not listen for the 'deviceready' event. ###

  This is listed MULTIPLE times in the documentation, and is include in every example where it is appropriate. It is still missed. Here is the appropriate point in the [section of documentation](http://cordova.apache.org/docs/en/latest/cordova/events/events.deviceready.html) we need. 

  > This event is essential to any application. It signals that Cordova's device APIs have loaded and are ready to access.

  > Cordova consists of two code bases: native and JavaScript. While the native code loads, a custom loading image displays. However, JavaScript only loads once the DOM loads. This means the web app may potentially call a Cordova JavaScript function before the corresponding native code becomes available.

  > The `deviceready` event fires once Cordova has fully loaded. Once the event fires, you can safely make calls to Cordova APIs. Applications typically attach an event listener with `document.addEventListener` once the HTML document's DOM has loaded.

  <p />And in case you think this is minor, even veterans like Raymond Camden [have forgotten this](http://www.raymondcamden.com/2015/07/15/fyi-cordova-events-must-be-run-after-deviceready).

###<a name=005>5.</a> When designing the app, thinks phonegap works like a website or webbrowser. ###

  Cordova/Phonegap is a framework that happens to use a library, called [webview](webview.md) on Android (and similar libraries on other platforms), that happens to use HTML5 to render the UI (User Interface). The framework is NOT a webserver. The framework is also NOT a webbrowser. This also means many of the BOM (Browser Object Model) compenents do not exist; such as "location bar", bookmarks, cookies, [cache](http://www.raymondcamden.com/2015/02/26/reminder-you-dont-need-appcache-for-phonegapcordova), CORS, etc.

  *Quote* ***[Phonegap FAQ](http://phonegap.com/about/faq/)***
  > Q: Can you use PHP/ASP/JSF/Java/.NET with PhoneGap?
  >
  > A: A PhoneGap application may <u>only</u> use HTML, CSS, and JavaScript. However, you can make use of network protocols (XmlHTTPRequest, Web Sockets, etc) to easily communicate with backend services written in any language. This allows your PhoneGap app to remotely access existing business processes while the device is connected to the Internet.

  This also means that assets (javascript, css, etc) should be on the device NOT the network.

  For example, if you have this:<br>
  `<script src="https://code.jquery.com/jquery-1.11.3.min.js"></script>`<br>
  or this<br>
  `<script src="//code.jquery.com/jquery-1.11.3.min.js"></script>`<br>
  change it to this:<br>
  `<script src="jquery-1.11.3.min.js"></script>`

  In addition, Google and Apple frowns on using apps as wrappers for websites.

  *Quote* ***[Quote Google Developer Program Policies](https://play.google.com/about/developer-content-policy.html) - Spam and Placement in the Store***
  > Do not post an app where the primary functionality is to:
  >    - Drive affiliate traffic to a website or
  >    - Provide a webview of a website not owned or administered by you (unless you have permission from the website owner/administrator to do so)

  *Quote* ***[Apple iTunes Guidelines](https://developer.apple.com/app-store/review/guidelines/) - 2.12***
  > Apps that are not very useful, unique, are simply web sites bundled as Apps, or do not provide any lasting entertainment value may be rejected

###<a name=006>6.</a> Not setting the "phonegap version" for your compiler###

  With the CLI version, if you do not assign a version for your platform _OR_ in ''Phonegap Build'' if you do not set the ```phonegap-version``` in config.xml, YOU WILL GET THE LATEST VERSION. If you are lucky, your program just works as expected. If you are not lucky, you'll get a set of cascading error. 

  Luckily for all of us, Holly Schinsky has written a nice blog post to explain it all: *(NOTE: Holly has not had time to update the article since the move to NPM, use the NPM names, not the names she is using.)*

  *Cordova/PhoneGap Version Confusion*<br />
  http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/

###<a name=007>7.</a> Not setting "version" for your plugins###

  I've been guilty of this mistake. Even worst, I gave people code examples making this mistake. I hope those people will read this one day and make the appropriate correction. To be clear on this, it now consider *"best practice"* to always use a version number with your plugin.

  In the last ''Top Mistake'' (#6), Holly Schinsky disucussed this in her blog post. But just to get the point across, here is a Post from the Nitobi Forum,

  *[ Notes for upgrading to cli-5.1.1 on PGB](http://community.phonegap.com/nitobi/topics/notes-for-upgrading-to-cli-5-1-1-on-pgb) (Phonegap Build)*

###<a name=008>8.</a> Forgot to add the plugin to `config.xml`, or `cordova.js` to `index.html`.###

  Oops. Every developer has done this at one time or another. I've done it, and them spent 8 hours debugging this mistake. [Raymond Camden](http://www.raymondcamden.com/2013/11/02/Seeing-two-geolocation-prompts-in-a-PhoneGapCordova-application) has also. OUCH! 

  Luckily on *Cordova/Phonegap CLI* this is dealt with, but on [Cordova/Phonegap SDK](http://docs.phonegap.com/en/4.0.0/config_ref_index.md.html#The%20config.xml%20File_the_feature_element) and [Phonegap Build](http://docs.build.phonegap.com/en_US/configuring_plugins.md.html#Plugins) **you** have to do this. It is referenced differently by both. The vocabulary is different for both. Read the docs.

###<a name=009>9.</a> Using an online example for "phonegap CLI" and then using "phonegap Build" ###

  I confess to doing this. I also confess to giving people the wrong version. Sometimes, I have gave them Phonegap Build, when I should have given them Phonegap CLI.

  *This is happening more and more with disaterous results and frustrating.*

  To be clear, if you create an App with the command line tools, that App will NOT work with *Phonegap Build*; the structure is different. If you need a place to start, use this boilerplate [Phonegap--Generic-Boilerplate8](https://github.com/jessemonroy650/Phonegap--Generic-Boilerplate8). Note, this is an example. You still need to optimize this example, if you are going to use it.

###<a name=010>10.</a> Not adding the new "white-list", "white-list plugin" parameters in config.xml AND "Content Security Policy"###

  This is sooo new and obnoxious, one can only have pity on returning developers. In addition, this was buried in both the *Phonegap blog* and the *Cordova blog*.

  This relatively * NEW * requirement means &ndash; to access ANY website or resources on the web, you MUST use the whitelist and the whitelist plugin. This requirement goes into affect, if you are using cordova-android@4.0.0 or better; including cli-5.1.1 &amp; cli-5.2.0. 

**CHANGE 2015-11-27T22:52:06**

  Today I move more of the stuff here to misc. (see below)

**CHANGE 2015-11-14T02:17:49**

  Today I decided to point to a much cleaner version of this with a better way to deal with the `whitelist` system.  Stuff that was previously here is now in [whitelist-misc.md](whitelist-misc.md#previous_stuff) (This stuff will eventually be merged or moved to other sections; copy if you need it.)

  [HOW TO apply the Cordova/Phonegap the whitelist system](the-whitelist-system.md)

  **Added on 2015-11-27**

  If you are looking for additional guideance you the `whitelist` system, read the [`whitelist` matrix](whitelist-matrix.md)

### <a name=011>11.</a> You need to get your plugins from NPM now.###

  The rules regarding sourcing your plugins can be rather confusing. The best thing to do is read the blog posts - below. Developers that use **CLI** can source from github, again see the blog post.

  2015-10-09 - Without announcment, tweet, or blog, the repository change a full week before it was scheduled. I can do nothing, but complain.... This is damm annoying.

  * [Cordova npm search page](http://cordova.apache.org/plugins/)
  * [Cordova CORE plugins](http://cordova.apache.org/docs/en/5.4.0/cordova/plugins/pluginapis.html)
  * [**Latest** Plugins Release](http://cordova.apache.org/news/2015/11/24/plugins-release.html) - 24 Nov 2015 - If you are using the CLI or the SDK, you can use these versions.
  * [Plugins Release](http://cordova.apache.org/news/2015/06/22/plugins-release.html) June 22, 2015 - If you are using *Phonegap Build*, you want to use these versions.

  
  *Blog Posts Related to #11*

  * Cordova [Plugins Release](cordova.apache.org/news/2015/11/24/plugins-release.html) - 2015/11/24
  * Cordova [Tools Release: November 6th, 2015](http://cordova.apache.org/news/2015/11/06/tools-release.html) - 2015/11/06

    > Cordova will now auto convert old-style plugin IDs to new style plugin IDs when doing a cordova plugin add. This only happens if the old-style plugin ID exists in the registry-mapper, it will be auto converted to the new ID and fetched from npm instead.

  * Cordova [Cordova Plugins Registry becomes immutable](http://cordova.apache.org/news/2015/09/08/CPR-readonly.html) 2015/09/08
  * Cordova [Plugins Release and Moving plugins to npm](http://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html) 2015/04/21

###<a name=012>12</a>. For *Phonegap Build* ONLY `<feature>` is deprecated ###

  `<feature>` tags are deprecated. That means they are no longer used.
  You can [read about it here](http://docs.build.phonegap.com/en_US/configuring_features.md.html#Features)
  
  > Aside from the debug-server feature, the feature tag is essentially deprecated on PhoneGap Build since PhoneGap APIs were pluginized. Permissions are now generally managed by individual plugins, and application manifests and permissions can be modified directly using the config-file element. However for backwards-compatibility, they are still supported and map to device permissions on Android and Windows Phone 8:

###<a name=013>13</a>. For some Cordova Plugins, there is likely an HTML5 API. ###

  SEE: http://mobilehtml5.org/

  **NOTE:** Many HTML5 APIs will work with *Cordova*, and where appropriate *Cordova* will use the HTML5 API. However, sometimes the *Cordova* Plugin and *HTML5 API* clash; not all instances are reported or tested. (Keep in mind more than 2000 Android devices are in the field.)

  There will be more on this later. Just getting started. 2015-11-03

### Some additional related articles ###

* [Beginner Stumbling Blocks in Phonegap & Cordova](http://scottbolinger.com/beginner-phonegap-cordova/) - Scott Bolinger - +wordpress
* [7 Lessons from 3 Years of HTML5 Mobile Application Development](http://www.joshmorony.com/7-lessons-from-3-years-of-html5-mobile-application-development/) - Josh Morony
* [Cross-platform Mistakes](http://blog.41studio.com/cross-platform-mistakes/) - 41Studio - +RubyOnRails
* [PhoneGap Development Mistakes and How to Avoid Them](https://chrisgriffith.wordpress.com/2014/10/10/phonegap-development-mistakes-and-how-to-avoid-them/) - Chris Griffith
* [Can I use PHP to build a webapp using the PhoneGap framework?](http://www.quora.com/Can-I-use-PHP-to-build-a-webapp-using-the-PhoneGap-framework) - Quora 

----

### Frustrating Issues for the Volunteers ###

Virtually none (any?) of the people who read and help out on the list are paid to do so, or indeed have any formal connection to the Cordova project. We help because we want to, because other people helped us, because having a thriving Cordova community is good for everyone.

However it is a constant frustration when people make the same mistakes in writing a post to the group and asking for help. 

Many of the posts repeat the same mistake time and time again. The volunteers respond time and time again with the same response, sometime the responses are very curt and very direct. 

The problems are:

1. Nowhere near enough information, too much information, inappropriate information or assumed information.
2. No description of the environment the user has, e.g. CLI, IDE or Phonegap Build.
3. Plugins not working. The writer makes the assumption that the volunteers know every plugin.
4. Asking for high level help. 
5. Asking the same questions time after time. 
6. Not reading the docs (which to be honest can be a mess).
7. Not reading the start page
8. Others...

So lets dig into the sort of mistakes people make and how not to make them again,

1. **Not getting enough information from a posting**<p />We know that Phonegap entices new developer because of the promise of mobile development, so we try to be patient.<p /> Please post the following information:
  1. *What you are trying to do. Be specific, not general.* It takes time to write a succint and easy to read request for help. As already stated none of us are paid to help, we are taking time out of doing our day (and night) job to help you. You need to make it easy for us to help you, if you write too much and it rambles people will lose interest and ignore you. If it's too short, then people will ignore you as asking for more information that might or might not arrive is too much trouble. It takes time to write a decent email request for help, to summarise the information appropriately so its clear and easy to understand, it might easily take a few hours or a whole day to assemble the right information. It's a lot easier to help somebody when its clear that they are prepared to put the time in to help themselves.
  2. *Do not forget that we have no idea who you are, we have no idea what your app does or what your level of experience is.* You cannot assume anything whatsoever,  *you* need to ensure you put enough information in but not too much. Nobody is going to read pages of explanation and code. Put yourselves in our position and read what you have put, does it make sense to somebody who has zero knowledge of what you are trying to do? Read it again and again and check what you have put, simplify things down to make it easy. This takes time and effort to do.
  2. *What have you tried to do to make it work?* Time and time again, people post requests for help and state nothing beyond "X doesn't work", but give no indication of what they have tried to do to make it work. An example of a good request is you can't make a connection to a website on IOS 9 but you could on IOS 8, you checked the whitelist plugin and Content Security Policy meta tag in the index.html file (post the CSP tag and URL) and it still doesn't worked, here's the error in Xcode. Thats a useful post that immediately demonstrates you've tried to fix it, you've provided a bit more useful information on the environment you're using and an error code. 
  3. *What did not work as expected. What was expected to happen?* It may be that your expectation of what was supposed to happen is incorrect and what happened is the right behaviour. Don't forget that Android and IOS have different default behaviours for many things.
  4. *What level of experience you have with mobile development.* This gives us a big clue as to how we can help you. If you have never done a mobile app before and you are trying to build a complex system, we might advise you to go and build a small app first to learn about what you should and shouldn't do. Its often quicker to build a smaller app that proves the concept rather than jumping in and trying to boil the oceon in one go. Be honest about your abilites, its no shame to be a beginner, everybody without exception ahd to start from nothing.  <p />
  
2. **Not knowing if the person posting the question is using a CLI, an IDE, or Phonegap Build.**<p />In theory, phonegap works with a varitey of IDEs, but it also supports a CLI (Command Line Interface). This creates multiple issues. The largest question becomes, is the environment setup correctly. This happens most often with MS Windows, but it also happens with Linux. Not so much on iOS (any more). The issues with Phonegap Build can be very different to CLI. Some of the volunteers only use one system so it would be good to get this information out early.
3. **Plugins don't work.**<p />There is not much we can do expect help you understand the configuration as defined by the author of the plugin. Too often a plugin becomes neglectware and we are both stuck. In this case, choose another plugin. There are lots and lots of plugins available, an excellent way to check out the vitality of a plugin is to look at the issues list if its hosted on Github. If there are lots of questions AND answers then its being supported. In many cases the issues forum for the plugin are a better place to ask questions than here as who knows if the author subscribes to this list.
4. **Getting confused by the different versions of documentation.**<p />It is easy to get confused when looking at the ''Phonegap'' documentation and NOT REALIZE that there is documentation for ''Phonegap Build''
5. **The documentation is a mess.**<p />Luckily the leading edge documentation is mostly correct.
6. **Some APIs have shifted over time because of political issues.**<p />File, File Storage, and File Transfer is the classic example of this issue. Please read the documentation carefully. Make no assumptions that a small minor change in numbering is actually a small minor change in functionality.
7. **The definition for using config.xml is different for ''Cordova'', ''Phonegap'', and ''Phonegap Build''.**<p />Although they are very similar, they are different. Please read the documentation.

----
####<a name=footnotes>footnotes</a>####
1. From the documentation, it is presumed the meaning for SDK is the SDK packaged for use with an IDE; such as Eclipse, Android Studio, [intel-xdk](http://xdk-software.intel.com/), MS Visual Studio, XCode, etc.

----

* 2015-08-16 - Thanks to Raymond Camden for his clarifications and corrections.
