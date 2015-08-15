## Top Mistakes by Developers new to Phonegap/Cordova ##


1. **There are three similar systems, Cordova, Phonegap, and Phonegag Build. People often confuse the three very similar system and get tangle in minor variations that differentate them.**<p />Oddly enough, the best explanation comes from something built on top of Phonegap - *Ionic*, from their blog post *[The Last Word on Cordova and PhoneGap](http://blog.ionic.io/what-is-cordova-phonegap/)*
> PhoneGap proper was created around 2009 by a startup called Nitobi as an open source way to access the "native" environment through an embedded Web View in a native app. The goal of the project was to make it possible to build the bulk of a mobile app experience with pure web technologies like HTML5, CSS, and Javascript, but still be able to call into native code when necessary.
>
> In 2011 Adobe purchased Nitobi and with it the rights to the PhoneGap brand, and the open source core was donated to the Apache Software Foundation under the name Cordova.
>
> Read more on the *[Ionic Blog](http://blog.ionic.io/what-is-cordova-phonegap/)*

2. **Does not read the docs.**<p />There are three (3) sets of docs. One for Cordova CLI (Command Line Interface), another for Phonegap CLI, and one for Phonegap Build. They are similar, but NOT the same. Also, to add to the confusion, sometimes the Cordova documentation is the only set of docs available. This happens for some plugins. This also happens in the Phonegap Devleoper's Guide. (aka Beginners Guide)
* [Cordova](http://cordova.apache.org/docs/en/3.0.0/)
* [Phonegap Beginner's Guide](http://docs.phonegap.com/) & 
[Phonegap 3.0.0](http://docs.phonegap.com/en/3.0.0/) (older,but sometimes better)
* [Phonegap Build](http://docs.build.phonegap.com/en_US/#googtrans%28en%29)

3. **Does not follow the blogs.**<p />
4. **In the code, did not listen for the 'deviceready' event.**<p />
5. **When designing the app, thinks phonegap works like a website.**<p />
6. **Not setting "phonegap-version" in config.xml.**<p />
7. **Not setting "version" for you plugins in config.xml.**<p />
8. **Forgot to add the plugin to config.xml.**<p />
9. **Using an online example for "phonegap CLI" and then using "phonegap Build"**<p />
10. **Not adding the new "white-list" and "white-list plugin" parameters in config.xml.**<p />

## Frustrating Issues for the Volunteers ##


1. **Not knowing if the person posting the question is using a CLI, an IDE, or Phonegap Build.**<p />In theory, phonegap works with a varitey of IDEs, but it also supports a CLI (Command Line Interface). This creates multiple issues. The largest is the environment is not setup correctly. This happens most often with MS Windows, but it also happens with Linux. Not so much on iOS (any more).
2. **Plugins don't work.**<p />There is not much we can do expect help you understand the configuration as defined by the author of the plugin. Too often the plugin becomes neglectware and we are both stuck. In this case, choose another plugin.
3. **Getting confused by the different versions of documentation.**<p />It is easy to get confused when looking at the ''Phonegap'' documentation and NOT REALIZE that there is documentation for ''Phonegap Build''
4. **The documentation is a mess.**<p />Luckily the leading edge documentation is mostly correct.
5. **Some APIs have shifted over time because of political issues.**<p />File, File Storage, and File Transfer is the classic example of this issue. Please read the documentation carefully.
6. **The definition for using config.xml is different for ''Cordova'', ''Phonegap'', and ''Phonegap Build''.**<p />Although they are very similar, they are different. Please read the documentation.

