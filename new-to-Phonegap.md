### Top Mistakes by Developers new to Cordova/Phonegap ###

1. **Thinking Phonegap is just one system**<p />There are three similar platforms, Cordova (CLI), Phonegap (CLI), and Phonegag Build and five system (counting Cordova/Phonegap SDK<sup>1</sup>). People often confuse the three very similar platforms and get tangled in the minor variations that differentiate them.<p />
  Oddly enough, the best explanation comes from something built on top of Angular, and wraps the Cordova/Phonegap CLI. - *Ionic*.

  From the Ionic Blog *[The Last Word on Cordova and PhoneGap](http://blog.ionic.io/what-is-cordova-phonegap/)*
  > PhoneGap proper was created around 2009 by a startup called Nitobi as an open source way to access the "native" environment through an embedded Web View in a native app. The goal of the project was to make it possible to build the bulk of a mobile app experience with pure web technologies like HTML5, CSS, and Javascript, but still be able to call into native code when necessary.
  >
  > In 2011 Adobe purchased Nitobi and with it the rights to the PhoneGap brand, and the open source core was donated to the Apache Software Foundation under the name Cordova.
  >
  > Read more on the *[Ionic Blog](http://blog.ionic.io/what-is-cordova-phonegap/)*

  On the **Cordova/Phonegap SDK (or IDE)** &ndash; for all intensive purposes, these are the same as *Cordova/Phonegap CLI*, with an extra step involving [`config.xml`](http://cordova.apache.org/docs/en/5.0.0/config_ref_index.md.html#The%20config.xml%20File_the_feature_element).

  **The Official Websites**
  * [Cordova](http://cordova.apache.org/)
  * [Phonegap](http://phonegap.com/)
  * [Phonegap Build](https://build.phonegap.com/plans)

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
  Cordova/Phonegap is a framework that happens to use a library, called webview on Android (and similar libraries on other platforms), that happens to use HTML5 to render the UI (User Interface). The framework is NOT a webserver.

  *Quote* ***[Phonegap FAQ](http://phonegap.com/about/faq/)***
  > Q: Can you use PHP/ASP/JSF/Java/.NET with PhoneGap?
  >
  > A: A PhoneGap application may <u>only</u> use HTML, CSS, and JavaScript. However, you can make use of network protocols (XmlHTTPRequest, Web Sockets, etc) to easily communicate with backend services written in any language. This allows your PhoneGap app to remotely access existing business processes while the device is connected to the Internet.

  In addition, Apple frowns on using apps as wrappers for websites.

  *Quote* ***[Apple iTunes Guidelines](https://developer.apple.com/app-store/review/guidelines/) - 2.12***
  > Apps that are not very useful, unique, are simply web sites bundled as Apps, or do not provide any lasting entertainment value may be rejected

6. **Not setting the "phonegap version" for your compiler** <p />
  With the CLI version, if you do not assign a version for your platform _OR_ in ''Phonegap Build'' if you do not set the ```phonegap-version``` in config.xml, YOU WILL GET THE LATEST VERSION. If you are lucky, your program just works as expected. If you are not lucky, you'll get a set of cascading error. 

  Luckily for all of us, Holly Schinsky has written a nice blog post to explain it all:

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

  This relatively * NEW * requirement means &ndash; to access ANY website or resources on the web, you MUST use the whitelist and the whitelist plugin. This requirement goes into affect, if you are using cordova-android@4.0.0 or better; including cli-5.1.1. If however, your version is before 4.0.0, let use say 3.5.0 or 3.7.0, then you will *not* have to add the *white-list* requirement.

  To be clear, the "whitelist" has been around for a bit, but the plugin and requirement is very new. As you would expect, when the "whitelist" was added, the defacto *open-access* feature was deprecated. Or said another way, the defacto *open-access* feature was planned and scheduled to be eliminated. This change marks a step in removal of the *open-access* feature.

  In addition, the *Content Security Policy (CSP)* has caught numerous developers - because it was soooo poorly publicized. This CSP needs to go in every single HTML page you used, just like you have to wait for 'deviceready'. The documentation is buried in the bottom of many of the latest documentation pages.

  Cordova Blog: *[Plugins Release and Moving plugins to npm: April 21, 2015](https://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html)* and **New Whitelist Plugins**; scroll down to the title.

  Phonegap Build Forum: *[Notes for upgrading to cli-5.1.1 on PGB](http://community.phonegap.com/nitobi/topics/notes-for-upgrading-to-cli-5-1-1-on-pgb)* and now required **Whitelist**

  * [Cordova Whitelist Guide](https://cordova.apache.org/docs/en/4.0.0/guide_appdev_whitelist_index.md.html) or [npm version](https://www.npmjs.com/package/cordova-plugin-whitelist)
  * [Phonegap Whitelist Guide](http://docs.phonegap.com/en/4.0.0/guide_appdev_whitelist_index.md.html#Whitelist%20Guide)
  * [Phonegap Build Whitelist Guide](http://docs.build.phonegap.com/en_US/configuring_access_elements.md.html#Access%20Elements)
  * [cordova-plugin-whitelist](https://github.com/apache/cordova-plugin-whitelist)


  *Apple has a similar system that is in place. You can read some of the details in this link.*<br />
  See: [Configuring App Transport Security Exceptions in iOS 9 and OSX 10.11](http://ste.vn/2015/06/10/configuring-app-transport-security-ios-9-osx-10-11/)<br />
  Also: [Working with Apple's App Transport Security](http://www.neglectedpotential.com/2015/06/working-with-apples-application-transport-security/)<br />
  **[Apple's official documentation for App Transport Security](https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/index.html#//apple_ref/doc/uid/TP40016240)**

11. **You need to get your plugins from NPM now.**

  The rules regarding sourcing your plugins can be rather confusing. The best thing to do is read the blog posts - below. Developers that use **CLI** can source from github, again see the blog post.

  * new [cordova npm search page](http://plugins.cordova.io/npm/index.html)
  
  *Blog Posts Related to #11*
  * [Cordova Plugins Registry becomes immutable](http://cordova.apache.org/news/2015/09/08/CPR-readonly.html) 2015/09/08
  * [Plugins Release and Moving plugins to npm](http://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html) 2015/04/21


**Some additional related articles**

* [Beginner Stumbling Blocks in Phonegap & Cordova](http://scottbolinger.com/beginner-phonegap-cordova/) - Scott Bolinger - +wordpress
* [7 Lessons from 3 Years of HTML5 Mobile Application Development](http://www.joshmorony.com/7-lessons-from-3-years-of-html5-mobile-application-development/) - Josh Morony
* [Can I use PHP to build a webapp using the PhoneGap framework?](http://www.quora.com/Can-I-use-PHP-to-build-a-webapp-using-the-PhoneGap-framework) - Quora 
* [Cross-platform Mistakes](http://blog.41studio.com/cross-platform-mistakes/) - 41Studio - +RubyOnRails

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
