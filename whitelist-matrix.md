## White-list Matrix ##
Date: 2015-10-26

Often I think someone at Microsoft designed this, but then I realize that the entire things was the product of multiple committes working indepently - with no real design criteria. 

If you have never heard of a [decision table](https://en.wikipedia.org/wiki/Decision_table), today you'll learn of the value of them. This easy enough. Start at the top (1.) and continue till to the bottom (9.). If you drop out anywhere along the way. You are done. 

The table does not loop back or interconnect. This is, in fact, a simple expert system &ndash; with you as the feedback. Meaning, if you discover an error, let me know. I or someone else will adjust this set of tables.


1. [Is my version of Cordova/Phonegap included](#version)?
2. [Which `whitelist` guide should I use](#guide)?
3. [Which plugin, `whitelist` or `legacy-whitelist`](#plugin)?
4. [Do I have to apply `allow-navigation`](#navigation)?
5. [Do I have to apply `allow-intent`](#intent)?
6. [Do I have to apply `access origin`](#access)?
7. [How does this affect `inappbrowser`](#inappbrowser)?
8. [CSP](#csp)?
9. [ATS](#ats)?

###1. <a name=version>Is my version of Cordova/Phonegap included</a>###

| Your Version of<br>*Cordova/Phonegap Tools* <sup>¢</sup> | support | notes |
|----------------------------------|---------|-------|
| 2.x | Not support | deprecated |
| 3.x | Available   |  - |
| 4.x | Required    | white-list, plugin |
| 5.x<sup>¥</sup> | Required    | white-list, plugin, CSP |
| Any above AND iOS9<sup>£</sup> | Required | Apple's ATS<sup>§</sup> |

- ¢ = Cordova and Phonegap versions do NOT align, but are close. This version is not the \*pinned* version either. If you do not know the difference, [learn](http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/) - [official release policy](https://github.com/apache/cordova-coho/blob/master/docs/versioning-and-release-strategy.md).
- ¥ = This include cli-5.1.0 and cli.5.2.0
- £ = As of 2015-10-28, iOS9 is officially **not** supported until *Cordova iOS 4.0.0* is released ([SEE](http://community.phonegap.com/nitobi/topics/phonegap-build-ios-9-support-status)).
- § = ATS requires &ndash; if you are using Apple's SSL, the server you connect to [run TLSv1.2](http://ste.vn/2015/06/10/configuring-app-transport-security-ios-9-osx-10-11/)

###2. <a name=guide>Which guide</a>###

For all intensive purpose, there are three (3) whitelist guides. They all have mistakes, lack current information, and suffer from neglect. However, there are important pointers for each platform. So, if you are working on *Windows, Blackberry, Tizen*, or one of the other platform, do read the appropriate guide. 

1. [Cordova Whitelist Guide](http://cordova.apache.org/docs/en/5.1.1/guide/appdev/whitelist/index.html) - Cordova CLI and SDK
2. [Phonegap Whitelist Guide](http://docs.phonegap.com/en/edge/guide_appdev_whitelist_index.md.html#Whitelist%20Guide) - Phonegap CLI and SDK
3. [Phonegap Build Whitelist Guide](http://docs.build.phonegap.com/en_US/configuring_access_elements.md.html#Access%20Elements) - Phonegap Build only


###3. <a name=plugin>Which plugin, `whitelist` or `legacy-whitelist`</a>###

`legacy-whitelist`

> This plugin implements the Cordova 3.6 Whitelist policy for Cordova 4.0. 

If you implemented the whitelist system for Android before `15 Apr 2015`, then you can still use this system. As of that date, the new `whitelist` plugin is available and it runs with a different set of rules. However, the `legacy-whitelist` is also available and is currently support - but not likely much longer.

`whitelist`

> This plugin implements a whitelist policy for navigating the application webview on Cordova 4.0

If you have not implemented the whitelist system yet, then you want to start here. This plugin has more parameters and has better granularity that the legacy plugin.

###4. <a name=navigation>allow-navigation</a>###

Controls which URLs the \*WebView* itself can be navigated to. Applies to top-level navigations only. 

By default, navigations only to file:// URLs, are allowed. To allow other other URLs, you must add <allow-navigation> tags to your config.xml.

*Quirks:* On Android, it also applies to iframes for non-http(s) schemes.

**DANGEROUS-SETTING:** `<allow-navigation href="*" />`

###5. <a name=intent>allow-intent</a>###

Controls which URLs the app is allowed to ask the \*system* to open. By default, no external URLs are allowed.

This whitelist does not apply to plugins, only hyperlinks and calls to window.open().

*Quirks:* On Android, this equates to sending an intent of type BROWSEABLE.

###6. <a name=access>access origin</a>###



###7. <a name=inappbrowser>inappbrowser</a>###

###8. <a name=csp>CSP</a>###

###9. <a name=ats>ATS</a>###


----

When I say the information about the `whitelist` system was buried, I mean these three (3) blog posts

Plugins Release and Moving plugins to npm: April 21, 2015
SEE: New Whitelist Plugins
https://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html

Apache Cordova Android 4.0.0: 15 Apr 2015
SEE: Major Changes 
http://cordova.apache.org/announcements/2015/04/15/cordova-android-4.0.0.html
- CSP is now supported
- Network requests are blocked by default without the plugin
- latest default app created by cordova-cli will include this plugin by default

SEE: org.apache.cordova.inappbrowser@0.5.4
http://cordova.apache.org/announcements/2015/04/15/cordova-android-4.0.0.html

