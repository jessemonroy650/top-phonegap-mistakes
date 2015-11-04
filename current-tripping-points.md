### Current Tripping Points to Cordova/Phonegap ###
Last Update: 2015-11-03
<br>Date: 2015-10-18

## 1. iOS9 is Now supported ##

Read the blog post

Apache Cordova iOS 3.9.2<br>
http://cordova.apache.org/announcements/2015/11/02/cordova-ios-3-9-2.html

> We are happy to announce that Cordova iOS 3.9.2 has been released and will be the default iOS version.

> This release addresses multiple iOS 9/9.1 and XCode 7/7.1 issues. It also deprecates a number of APIs, which will be removed in Cordova iOS 4.0.0. For a full list of API changes see API changes in 4.0.md

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


