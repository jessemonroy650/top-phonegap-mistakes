### Top Mistakes by Developers new to Cordova/Phonegap ###
LAST UPDATE: 2015-10-18

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

1. **Thinking Phonegap is just one system**<p />There are three similar platforms, Cordova (CLI), Phonegap (CLI), and Phonegag Build and five system (counting Cordova/Phonegap SDK<sup>1</sup>). People often confuse the three very similar platforms and get tangled in the minor variations that differentiate them.<p />
  Oddly enough, the best explanation comes from something built on top of Angular, and wraps the Cordova/Phonegap CLI. - *Ionic*.

  From the Ionic Blog *[The Last Word on Cordova and PhoneGap](http://blog.ionic.io/what-is-cordova-phonegap/)*
  > PhoneGap proper was created around 2009 by a startup called Nitobi as an open source way to access the "native" environment through an embedded Web View in a native app. The goal of the project was to make it possible to build the bulk of a mobile app experience with pure web technologies like HTML5, CSS, and Javascript, but still be able to call into native code when necessary.
  >
  > In 2011 Adobe purchased Nitobi and with it the rights to the PhoneGap brand, and the open source core was donated to the Apache Software Foundation under the name Cordova.
  >
  > Read more on the *[Ionic Blog](http://blog.ionic.io/what-is-cordova-phonegap/)*

  On the **Cordova/Phonegap SDK (or IDE)** &ndash; for all intensive purposes, these are the same as *Cordova/Phonegap CLI*, with an extra step involving [`config.xml`](http://cordova.apache.org/docs/en/5.0.0/config_ref_index.md.html#The%20config.xml%20File_the_feature_element).

  In addition, this leads to reading the wrong docs for the wrong platform. A common mistake for *Phonegap Build* is to use the [*Cordova* construct](http://cordova.apache.org/docs/en/5.1.1/config_ref/index.html) of `<platform>` and `<feature>`

  **The Official Websites**
  * [Cordova](http://cordova.apache.org/)
  * [Phonegap](http://phonegap.com/)
  * [Phonegap Build](https://build.phonegap.com/plans)

  *Blog Posts Related to #1*
  * [Cordova vs. PhoneGap: An update](http://blog.devgeeks.org/post/73789983750/cordova-vs-phonegap-an-update) - Jan 19, 2014
  * [PhoneGap, Cordova, and what?s in a name?](http://phonegap.com/2012/03/19/phonegap-cordova-and-what%E2%80%99s-in-a-name/) - 2012/03/19

2. **Does not read the docs.**<p />
  There are three (3) sets of docs. One for *Cordova CLI* (Command Line Interface), another for *Phonegap CLI*, and one for *Phonegap Build*. They are similar, but NOT the same. Also, to add to the confusion, sometimes the Cordova documentation is the only set of docs available; this happens for some plugins. This also happens with Phonegap &ndash; the Phonegap Developer's Guide for example. (aka Beginners Guide)

  **The Official Documentation**
  * [Cordova](http://cordova.apache.org/docs/en/3.0.0/)
  * [Phonegap Beginner's Guide](http://docs.phonegap.com/) & [Phonegap 3.0.0](http://docs.phonegap.com/en/3.0.0/) (older,but sometimes better)
  * [Phonegap Build](http://docs.build.phonegap.com/en_US/#googtrans%28en%29)

3. **Does not follow the blogs.**<p />
  All three platforms have blogs and twitter accounts. Ignore at your peril.
  * Official Apache [Cordova Blog](http://cordova.apache.org/blog/) - https://twitter.com/apachecordova
  * Official Adobe [Phonegap Blog](http://phonegap.com/blog/) - https://twitter.com/phonegap
  * Official Adobe [Phonegap Build Blog](http://phonegap.com/blog/phonegap-build/) - https://twitter.com/phonegapbuild

4. **In the code, did not listen for the 'deviceready' event.**<p />
  This is listed MULTIPLE times in the documentation, and is include in every example where it is appropriate. It is still missed. [Brian Ford](http://briantford.com/blog/angular-phonegap) - an Angular developer, points to the [section of documentation](http://docs.phonegap.com/en/2.3.0/cordova_events_events.md.html#deviceready) we need. 

  > This is a very important event that every Cordova application should use.
  >
  > Cordova consists of two code bases: native and JavaScript. While the native code is loading, a custom loading image is displayed. However, JavaScript is only loaded once the DOM loads. This means your web application could, potentially, call a Cordova JavaScript function before it is loaded.
  >
  > The Cordova <u>deviceready</u> event fires once Cordova has fully loaded. After the device has fired, you can safely make calls to Cordova function.

  <p />And in case you think this is minor, even veterans like Raymond Camden [have forgotten this](http://www.raymondcamden.com/2015/07/15/fyi-cordova-events-must-be-run-after-deviceready).

5. **When designing the app, thinks phonegap works like a website.**<p />
  Cordova/Phonegap is a framework that happens to use a library, called webview on Android (and similar libraries on other platforms), that happens to use HTML5 to render the UI (User Interface). The framework is NOT a webserver. The framework is also NOT a webbrowser.

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

  In addition, Apple frowns on using apps as wrappers for websites.

  *Quote* ***[Apple iTunes Guidelines](https://developer.apple.com/app-store/review/guidelines/) - 2.12***
  > Apps that are not very useful, unique, are simply web sites bundled as Apps, or do not provide any lasting entertainment value may be rejected

6. **Not setting the "phonegap version" for your compiler** <p />
  With the CLI version, if you do not assign a version for your platform _OR_ in ''Phonegap Build'' if you do not set the ```phonegap-version``` in config.xml, YOU WILL GET THE LATEST VERSION. If you are lucky, your program just works as expected. If you are not lucky, you'll get a set of cascading error. 

  Luckily for all of us, Holly Schinsky has written a nice blog post to explain it all: **(NOTE: Holly has not had time to update the article since the move to NPM, use the NPM names, not the names she is using.)**

  *Cordova/PhoneGap Version Confusion*<br />
  http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/

7. **Not setting "version" for you plugins** <p />
  I've been guilty of this mistake. Even worst, I gave people code examples making this mistake. I hope those people will read this one day and make the appropriate correction.

  In the last ''Top Mistake'' (#6), Holly Schinsky disucussed this in her blog post. But just to get the point across, here is a Post from the Nitobi Forum,

  *[ Notes for upgrading to cli-5.1.1 on PGB](http://community.phonegap.com/nitobi/topics/notes-for-upgrading-to-cli-5-1-1-on-pgb) (Phonegap Build)*

8. **Forgot to add the plugin to config.xml.** <p />
  Oops. Every developer has done this at one time or another. I've done it, and them spent 8 hours debugging this mistake. OUCH!

  Luckily on *Cordova/Phonegap CLI* this is dealt with, but on [Cordova/Phonegap SDK](http://docs.phonegap.com/en/4.0.0/config_ref_index.md.html#The%20config.xml%20File_the_feature_element) and [Phonegap Build](http://docs.build.phonegap.com/en_US/configuring_plugins.md.html#Plugins) **you** have to do this. It is referenced differently by both. The vocabulary is different for both. Read the docs.

9. **Using an online example for "phonegap CLI" and then using "phonegap Build"**<p />
  I confess to doing this. I also confess to giving people the wrong version. Sometimes, I have gave them Phonegap Build, when I should have given them Phonegap CLI.

  This also happens on the forum, repeatedly, not with disaterous results, but when it happens, it is frustrating. Use caution.

10. **Not adding the new "white-list", "white-list plugin" parameters in config.xml AND "Content Security Policy"**<p />
  This is sooo new and obnoxious, one can only have pitty on returning developers. In addition, this was buried in both the *Phonegap blog* and the *Cordova blog*.

  This relatively * NEW * requirement means &ndash; to access ANY website or resources on the web, you MUST use the whitelist and the whitelist plugin. This requirement goes into affect, if you are using cordova-android@4.0.0 or better; including cli-5.1.1 &amp; cli-5.2.0. If however, your version is before 4.0.0, let use say 3.5.0 or 3.7.0, then you will *not* have to add the *white-list* requirement.

  To be clear, the "whitelist" has been around for a bit, but the plugin and requirement is very new. As you would expect, when the "whitelist" was added, the defacto *open-access* feature was deprecated. Or said another way, the defacto *open-access* feature was planned and scheduled to be eliminated. This change marks a step in removal of the *open-access* feature.

  In addition, the Content Security Policy (CSP) has caught numerous developers - because it was soooo poorly publicized. <b>Depending on your use and the version of Phonegap you are using, the CSP needs to go in every single HTML page you used, just like you have to wait for 'deviceready'. However, there are cases where it is not needed at all. The documentation is confusing for some, please read it carefully.</b> The documentation is buried in the bottom of many of the latest documentation pages.

  Lastly, Raymond Camden in his blog points to a [LARGE change in policy starting with Cordova 5](http://www.raymondcamden.com/2015/05/25/important-information-about-cordova-5)

  Cordova Blog: *[Plugins Release and Moving plugins to npm: April 21, 2015](https://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html)* and **New Whitelist Plugins**; scroll down to the title.

  Cordova Blog: [Apache Cordova Android 4.0.0](http://cordova.apache.org/announcements/2015/04/15/cordova-android-4.0.0.html) - This blog post outline the behaviour of the white-list for Android, including CLI.

  Phonegap Build Forum: *[Notes for upgrading to cli-5.1.1 on PGB](http://community.phonegap.com/nitobi/topics/notes-for-upgrading-to-cli-5-1-1-on-pgb)* and now required **Whitelist**

  * <s>[Cordova Whitelist Guide](https://cordova.apache.org/docs/en/4.0.0/guide_appdev_whitelist_index.md.html)</s> or [npm version](https://www.npmjs.com/package/cordova-plugin-whitelist)
  * [Phonegap Whitelist Guide](http://docs.phonegap.com/en/4.0.0/guide_appdev_whitelist_index.md.html#Whitelist%20Guide)
  * [Phonegap Build Whitelist Guide](http://docs.build.phonegap.com/en_US/configuring_access_elements.md.html#Access%20Elements)
  * <s>[cordova-plugin-whitelist](https://github.com/apache/cordova-plugin-whitelist)</s>
  * NOTES on [CSP from Mozilla](https://developer.mozilla.org/en-US/docs/Web/Security/CSP/CSP_policy_directives#Keywords)

  *Apple has a similar system that is in place. You can read some of the details in this link.*<br />
  See: [Configuring App Transport Security Exceptions in iOS 9 and OSX 10.11](http://ste.vn/2015/06/10/configuring-app-transport-security-ios-9-osx-10-11/)<br />
  Also: [Working with Apple's App Transport Security](http://www.neglectedpotential.com/2015/06/working-with-apples-application-transport-security/)<br />
  * <s>[Apple's official documentation for App Transport Security](https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/index.html#//apple_ref/doc/uid/TP40016240)</s>
  * [Networking with NSURLSession - WWDC 2015 - Videos - Apple Developer](https://developer.apple.com/videos/play/wwdc2015-711/) - 40 minutes
  * [WWDC 2015 session 703, ?Privacy and Your App?, 30:18](https://developer.apple.com/videos/wwdc/2015/?id=703)
  * [How to Disable App Transport Security ? Five Minute WatchKit ? Medium](https://medium.com/five-minute-watchkit/how-to-disable-app-transport-security-2c8d5d298160) - Oct 13, 2015

11. **You need to get your plugins from NPM now.**

  The rules regarding sourcing your plugins can be rather confusing. The best thing to do is read the blog posts - below. Developers that use **CLI** can source from github, again see the blog post.

  2015-10-09 - Without announcment, tweet, or blog, the repository change a full week before it was scheduled. I can do nothing, but complain.... This is damm annoying.

  * <s>new [cordova npm search page](http://plugins.cordova.io/npm/index.html)</s>
  * NEW NEW [Cordova npm search page](http://cordova.apache.org/plugins/)
  * NEW NEW [Cordova CORE plugins](http://cordova.apache.org/docs/en/5.1.1/cordova/plugins/pluginapis.html)
  * [Latest version of plugins](http://cordova.apache.org/news/2015/06/22/plugins-release.html) June 22, 2015
  
  *Blog Posts Related to #11*
  * [Cordova Plugins Registry becomes immutable](http://cordova.apache.org/news/2015/09/08/CPR-readonly.html) 2015/09/08
  * [Plugins Release and Moving plugins to npm](http://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html) 2015/04/21
  * [List of the Latest \*Core* Plugins and their versions](http://cordova.apache.org/news/2015/06/22/plugins-release.html) June 22, 2015

<a name=012>12</a>. For *Phonegap Build* ONLY **`<feature>` is deprecated**

  `<feature>` tags are deprecated. That means they are no longer used.
  You can [read about it here](http://docs.build.phonegap.com/en_US/configuring_features.md.html#Features)
  
  > Aside from the debug-server feature, the feature tag is essentially deprecated on PhoneGap Build since PhoneGap APIs were pluginized. Permissions are now generally managed by individual plugins, and application manifests and permissions can be modified directly using the config-file element. However for backwards-compatibility, they are still supported and map to device permissions on Android and Windows Phone 8:

<a name=013>13</a>. **For some Cordova Plugins, there is likely an HTML5 API.**

  SEE: http://mobilehtml5.org/

  **NOTE:** Many HTML5 APIs will work with *Cordova*, and where appropriate *Cordova* will use the HTML5 API. However, sometimes the *Cordova* Plugin and *HTML5 API* clash; not all instances are reported or tested. (Keep in mind more than 2000 Android devices are in the field.)

  There will be more on this later. Just getting started. 2015-11-03

**Some additional related articles**

* [Beginner Stumbling Blocks in Phonegap & Cordova](http://scottbolinger.com/beginner-phonegap-cordova/) - Scott Bolinger - +wordpress
* [7 Lessons from 3 Years of HTML5 Mobile Application Development](http://www.joshmorony.com/7-lessons-from-3-years-of-html5-mobile-application-development/) - Josh Morony
* [Cross-platform Mistakes](http://blog.41studio.com/cross-platform-mistakes/) - 41Studio - +RubyOnRails
* [PhoneGap Development Mistakes and How to Avoid Them](https://chrisgriffith.wordpress.com/2014/10/10/phonegap-development-mistakes-and-how-to-avoid-them/) - Chris Griffith
* [Can I use PHP to build a webapp using the PhoneGap framework?](http://www.quora.com/Can-I-use-PHP-to-build-a-webapp-using-the-PhoneGap-framework) - Quora 

----

### Frustrating Issues for the Volunteers ###

1. **Not getting enough information from a posting**<p />We know that Phonegap entices new developer because of the promise of mobile development, so we try to be patient.<p /> Please post the following information:
  1. What you are trying to do. Be specific, not general.
  2. What have you tried.
  3. What did not work as expected.
  4. What level of experience you have with mobile development. THIS HELPS ALOT.<p />
2. **Not knowing if the person posting the question is using a CLI, an IDE, or Phonegap Build.**<p />In theory, phonegap works with a varitey of IDEs, but it also supports a CLI (Command Line Interface). This creates multiple issues. The largest question becomes, is the environment setup correctly. This happens most often with MS Windows, but it also happens with Linux. Not so much on iOS (any more).
3. **Plugins don't work.**<p />There is not much we can do expect help you understand the configuration as defined by the author of the plugin. Too often a plugin becomes neglectware and we are both stuck. In this case, choose another plugin.
4. **Getting confused by the different versions of documentation.**<p />It is easy to get confused when looking at the ''Phonegap'' documentation and NOT REALIZE that there is documentation for ''Phonegap Build''
5. **The documentation is a mess.**<p />Luckily the leading edge documentation is mostly correct.
6. **Some APIs have shifted over time because of political issues.**<p />File, File Storage, and File Transfer is the classic example of this issue. Please read the documentation carefully.
7. **The definition for using config.xml is different for ''Cordova'', ''Phonegap'', and ''Phonegap Build''.**<p />Although they are very similar, they are different. Please read the documentation.

----
####footnotes####
1. From the documentation, it is presumed the meaning for SDK is the SDK packaged for use with an IDE; such as Eclipse, Android Studio, [intel-xdk](http://xdk-software.intel.com/), MS Visual Studio, XCode, etc.

----

* 2015-08-16 - Thanks to Raymond Camden for his clarifications and corrections.
