## Whitelist misc ##
Date: 2015-11-02

This page include misc that are (at least) related to Phonegap  Whitelist


*Windows 8.1 allows only https URIs, not http URIs*<br>
https://msdn.microsoft.com/en-us/library/windows/desktop/dn457654%28v=vs.85%29.aspx
> While apps built for Windows 8 can include http and https URIs in their application content URIs, apps built for Windows 8.1 may include only https URIs. 


*ApplicationContentUriRules*<br>
https://msdn.microsoft.com/en-us/library/windows/apps/br211416.aspx
> Specifies which pages in the web context have access to the system's geolocation devices (if the app has permission to access this capability) and access to the clipboard.


### <a name=previous_stuff>STUFF REMOVED FROM `new-to-Phonegap.md`</a> ###

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
