### Current Tripping Points to Cordova/Phonegap ###
Last Update: 2015-11-03
<br>Date: 2015-10-18

## 1. No support for iOS9 YET! ##

**PhoneGap Build iOS 9 Support Status**

* Sept 23, 2015
* http://community.phonegap.com/nitobi/topics/phonegap-build-ios-9-support-status
* Top line: iOS 9 is **NOT** officially supported until Cordova-iOS 4.0.0, which the Cordova team is hard at work on. However some issues can be solved with some simple configuration changes. 

> At this point in time, 4 bugs are reported to the Cordova Bug repository. Your issue does not appear in the respository - as of this date.

 * 4 bugs - https://issues.apache.org/jira/browse/CB-9684?jql=text%20~%20%22iOS9%22
 * 1 bug - https://openradar.appspot.com/22186109

  Regardless, of what you are using, as the forum post states, iOS 9 is not officially supported until Cordova-iOS 4.0.0. This means, if you encouter a bug, you must - create a work around, or wait until it is officially supported, _OR_ file a bug report with cordova, _OR_ wait until someone else creates a work around.
  
  Sometimes Phonegap makes announcements on the forum and not the blog.<br />
  For more: [(Official) Messages from Phonegap Build Technical Support in the Forum](http://codesnippets.altervista.org/documentation/phonegap/bookmarks/fromSupport.html)

## 2. Plugins have MOVED!! ##

Without announcement or warning the Cordova team has moved the plugins. Luckily, the previous URL redirects, but some of the URLS &ndash; notably http://plugins.cordova.io/npm/index.html?q= is GONE!!

The rules regarding sourcing your plugins can be rather confusing. The best thing to do is read the blog posts - below. Developers that use CLI can source from github, again see the blog post.

2015-10-09 - Without announcment, tweet, or blog, the repository change a full week before it was scheduled. I can do nothing, but complain.... This is damm annoying.

- NEW NEW [Cordova npm search page](http://cordova.apache.org/plugins/)
- NEW NEW [Cordova CORE plugins](http://cordova.apache.org/docs/en/5.1.1/cordova/plugins/pluginapis.html)
- [Latest version of plugins](http://cordova.apache.org/news/2015/06/22/plugins-release.html) June 22, 2015

- [Cordova Plugins Registry becomes immutable](http://cordova.apache.org/news/2015/09/08/CPR-readonly.html) 2015/09/08
- [Plugins Release and Moving plugins to npm](http://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html) 2015/04/21
- [List of the Latest *Core* Plugins and their versions](http://cordova.apache.org/news/2015/06/22/plugins-release.html) June 22, 2015


## 3. `<feature>` is deprecated ##

`<feature>` tags are deprecated. That means they are no longer used.
You can [read about it here](http://docs.build.phonegap.com/en_US/configuring_features.md.html#Features)

###I QUOTE

> Aside from the `debug-server` feature, the `<feature>` tag is essentially deprecated on *PhoneGap Build* since *PhoneGap APIs* were pluginized. Permissions are now generally managed by individual plugins, and application manifests and permissions can be modified directly using the [config-file element](http://docs.build.phonegap.com/en_US/configuring_config_file_element.md.html). However for backwards-compatibility, they are still supported and map to device permissions on Android and Windows Phone 8:

In other words, you have a duplicate configuration, and it is doing nothing. Take it out.


