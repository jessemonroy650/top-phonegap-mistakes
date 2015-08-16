### Top Mistakes by Developers new to Cordova/Phonegap ###


1. **There are three similar systems, Cordova, Phonegap, and Phonegag Build. People often confuse the three very similar system and get tangle in minor variations that differentate them.**<p />
  Oddly enough, the best explanation comes from something built on top of Phonegap - *Ionic*, from their blog post 

  *[The Last Word on Cordova and PhoneGap](http://blog.ionic.io/what-is-cordova-phonegap/)*
  > PhoneGap proper was created around 2009 by a startup called Nitobi as an open source way to access the "native" environment through an embedded Web View in a native app. The goal of the project was to make it possible to build the bulk of a mobile app experience with pure web technologies like HTML5, CSS, and Javascript, but still be able to call into native code when necessary.
  >
  > In 2011 Adobe purchased Nitobi and with it the rights to the PhoneGap brand, and the open source core was donated to the Apache Software Foundation under the name Cordova.
  >
  > Read more on the *[Ionic Blog](http://blog.ionic.io/what-is-cordova-phonegap/)*

  **The Websites**
  * [Cordova](http://cordova.apache.org/)
  * [Phonegap](http://phonegap.com/)
  * [Phonegap Build](https://build.phonegap.com/plans)

2. **Does not read the docs.**<p />
  There are three (3) sets of docs. One for *Cordova CLI* (Command Line Interface), another for *Phonegap CLI*, and one for *Phonegap Build*. They are similar, but NOT the same. Also, to add to the confusion, sometimes the Cordova documentation is the only set of docs available. This happens for some plugins. This also happens in the Phonegap Devleoper's Guide. (aka Beginners Guide)

  **The Documentation**
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

  <p />And in case you think this is minor, even veterans like Raymond Camden [has forgotten this](http://www.raymondcamden.com/2015/07/15/fyi-cordova-events-must-be-run-after-deviceready).

5. **When designing the app, thinks phonegap works like a website.**<p />
  Cordova/Phonegap is framework that happens to use a library, called webview on Android (and similar libraries on other platforms), that happens to use HTML5 to render the UI (User Interface). The framework is NOT a webserver.

  *Quote* ***[Phonegap FAQ](http://phonegap.com/about/faq/)***
  > Q: Can you use PHP/ASP/JSF/Java/.NET with PhoneGap?
  >
  > A: A PhoneGap application may <u>only</u> use HTML, CSS, and JavaScript. However, you can make use of network protocols (XmlHTTPRequest, Web Sockets, etc) to easily communicate with backend services written in any language. This allows your PhoneGap app to remotely access existing business processes while the device is connected to the Internet.

  In addition, Apple frown on using apps as wrappers for websites.

  *Quote* ***[Apple iTunes Guidelines](https://developer.apple.com/app-store/review/guidelines/) - 2.12***
  > Apps that are not very useful, unique, are simply web sites bundled as Apps, or do not provide any lasting entertainment value may be rejected

6. **Not setting "phonegap-version" in config.xml.**<p />
  With the CLI version, if you do not assign a version for your platform _OR_ in ''Phonegap Build'' if you do not set the ```phonegap-version``` in config.xml, YOU WILL GET the latest version. If you are lucky, your program just works as expected. If you are not lucky, you'll get a set of cascasding error. 

  Luckily for all of us, Holly Schinsky has written a nice blog post to explain it all:

  *Cordova/PhoneGap Version Confusion*<br />
  http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/

7. **Not setting "version" for you plugins in config.xml.**<p />
  I've been guilty of this mistake. Even worst, I gave people code examples making this mistake. I hope those people will read this one day and make the appropriate correction.

  In the last ''Top Mistake'' (#6), Holly Schinsky disucussed this in her blog post. But just to get the point across, here is a Post from the Nitobi Forum,

  *[ Notes for upgrading to cli-5.1.1 on PGB](http://community.phonegap.com/nitobi/topics/notes-for-upgrading-to-cli-5-1-1-on-pgb)*

   This brings up a good point. Sometimes annoucement, or reiterations, are made on the forum. If you miss them, these set of bookmarks tries to stay up to date.

  *[(Official) Messages from Phonegap Build Technical Support in the Forum](http://codesnippets.altervista.org/documentation/phonegap/bookmarks/fromSupport.html)*

8. **Forgot to add the plugin to config.xml.**<p />
  Oops. Every developer has done this at one time or another. I've done it, and them spent 8 hours debugging this mistake. OUCH!

9. **Using an online example for "phonegap CLI" and then using "phonegap Build"**<p />
  I confess to doing this. I also confess to giving people the wrong version. Sometimes, I have gave them Phonegap Build, when I should have given them Phonegap CLI.

  This also happens on the forum, repeatedly, not with disaterous results, but when it happens, it is frustrating. Use caution.

10. **Not adding the new "white-list" and "white-list plugin" parameters in config.xml.**<p />
  This is sooo new and obnoxious, one can only have pitty on returning developers. In addition, this was buried in Cordova Blog.

  *[Plugins Release and Moving plugins to npm: April 21, 2015](https://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html)* and **New Whitelist Plugins**

  *[Notes for upgrading to cli-5.1.1 on PGB](http://community.phonegap.com/nitobi/topics/notes-for-upgrading-to-cli-5-1-1-on-pgb)* and Whitelist for Phonegap Build


### Frustrating Issues for the Volunteers ###


1. **Not knowing if the person posting the question is using a CLI, an IDE, or Phonegap Build.**<p />In theory, phonegap works with a varitey of IDEs, but it also supports a CLI (Command Line Interface). This creates multiple issues. The largest is the environment is not setup correctly. This happens most often with MS Windows, but it also happens with Linux. Not so much on iOS (any more).
2. **Plugins don't work.**<p />There is not much we can do expect help you understand the configuration as defined by the author of the plugin. Too often the plugin becomes neglectware and we are both stuck. In this case, choose another plugin.
3. **Getting confused by the different versions of documentation.**<p />It is easy to get confused when looking at the ''Phonegap'' documentation and NOT REALIZE that there is documentation for ''Phonegap Build''
4. **The documentation is a mess.**<p />Luckily the leading edge documentation is mostly correct.
5. **Some APIs have shifted over time because of political issues.**<p />File, File Storage, and File Transfer is the classic example of this issue. Please read the documentation carefully.
6. **The definition for using config.xml is different for ''Cordova'', ''Phonegap'', and ''Phonegap Build''.**<p />Although they are very similar, they are different. Please read the documentation.

