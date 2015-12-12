## Whitelist misc ##
Date: 2015-11-02

This page include misc that are (at least) related to Phonegap  Whitelist

If however, your version is before 4.0.0, let use say 3.5.0 or 3.7.0, then you will *not* have to add the *white-list* requirement.

  To be clear, the "whitelist" has been around for a bit, but the plugin and requirement is very new. As you would expect, when the "whitelist" was added, the defacto *open-access* feature was deprecated. Or said another way, the defacto *open-access* feature was planned and scheduled to be eliminated. This change marks a step in removal of the *open-access* feature.

  In addition, the Content Security Policy (CSP) has caught numerous developers - because it was soooo poorly publicized. <b>Depending on your use and the version of Phonegap you are using, the CSP needs to go in every single HTML page you used, just like you have to wait for 'deviceready'. However, there are cases where it is not needed at all. The documentation is confusing for some, please read it carefully.</b> The documentation is buried in the bottom of many of the latest documentation pages.

  Lastly, Raymond Camden in his blog points to a [LARGE change in policy starting with Cordova 5](http://www.raymondcamden.com/2015/05/25/important-information-about-cordova-5)



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

* [cordova-plugin-whitelist bugs](https://issues.apache.org/jira/issues/?jql=project%20%3D%20CB%20AND%20status%20in%20%28Open%2C%20%22In%20Progress%22%2C%20Reopened%29%20AND%20resolution%20%3D%20Unresolved%20AND%20component%20%3D%20%22Plugin%20Whitelist%22%20ORDER%20BY%20priority%20DESC%2C%20summary%20ASC%2C%20updatedDate%20DESC)
