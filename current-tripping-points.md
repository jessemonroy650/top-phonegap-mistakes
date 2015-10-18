### Current Tripping Points to Cordova/Phonegap ###
Date: 2015-10-18

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

## 2. Not setting compiler version ##

The alternative is this quick fix &ndash. However, this creates a [security issue](http://www.androidauthority.com/google-webview-security-582363/) which you may not want to by pass.

**QUICK FIX** Add this to your `config.xml`<br />
`<preference name="phonegap-version" value="3.7.0" />`

over the last two (2) weeks Cordova has made some major changes. The documentation has NOT caught up. I don't expect it will catch up for at least a few weeks. You have two (2) options:

1) Set your Compiler version to something before Cordova 4.0.0
2) Follow the complete protocol for using the `white-list`

From [Top Mistakes by Developers new to Cordova/Phonegap](https://github.com/jessemonroy650/top-phonegap-mistakes/blob/master/new-to-Phonegap.md) you have hit:

 * \#6 **Not setting the "phonegap version" for your compiler**
 * \#7 **Not setting "version" for you plugins**
 * \#10 **Not adding the new "white-list" and "white-list plugin" parameters in config.xml.**

For #6 & #7

 > With the CLI version, if you do not assign a version for your platform OR in ''Phonegap Build'' if you do not set the phonegap-version in config.xml, YOU WILL GET THE LATEST VERSION. If you are lucky, your program just works as expected. If you are not lucky, you'll get a set of cascading errors.

 > Luckily for all of us, Holly Schinsky has written a nice blog post to explain it all: **(NOTE: Holly has not had time to update the article since the move to NPM, use the NPM names, not the names she is using.)**

 > *Cordova/PhoneGap Version Confusion*<br />
 > http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/

For #10

 > This relatively * NEW * requirement means &ndash; to access ANY website or resources on the web, you MUST use the whitelist and the whitelist plugin. This requirement goes into affect, if you are using cordova-android@4.0.0 or better; including cli-5.1.1 and cli-5.2.0. If however, your version is before 4.0.0, let's say 3.5.0 or 3.7.0, then you will *not* have to add the *white-list* requirement.

 > To be clear, the "whitelist" has been around for a bit, but the plugin and requirement is very new. As you would expect, when the "whitelist" was added, the defacto open-access feature was deprecated. Or said another way, the defacto open-access feature was planned and scheduled to be eliminated. This change marks a step in removal of the open-access feature.

 > In addition, the Content Security Policy (CSP) has caught numerous developers - because it was soooo poorly publicized. <b>Depending on your use and the version of Phonegap you are using, the CSP needs to go in every single HTML page you used, just like you have to wait for 'deviceready'. However, there are cases where it is not needed at all. The documentation is confusing for some, please read it carefully.</b> The documentation is buried in the bottom of many of the latest documentation pages.

 > Lastly, Raymond Camden in his blog points to a [LARGE change in policy starting with Cordova 5](http://www.raymondcamden.com/2015/05/25/important-information-about-cordova-5)

 <b>Related Links</b>
 > Phonegap Build Forum: [Notes for upgrading to cli-5.1.1 on PGB](http://community.phonegap.com/nitobi/topics/notes-for-upgrading-to-cli-5-1-1-on-pgb) and now required Whitelist

 > * [Cordova Whitelist Guide](https://www.npmjs.com/package/cordova-plugin-whitelist)
 > * [Phonegap Whitelist Guide](http://docs.phonegap.com/en/4.0.0/guide_appdev_whitelist_index.md.html#Whitelist%20Guide)
 > * [Phonegap Build Whitelist Guide](http://docs.build.phonegap.com/en_US/configuring_access_elements.md.html#Access%20Elements)
 > * [White-list Plugin](https://www.npmjs.com/package/cordova-plugin-whitelist) - READ BOTTOM section for instruction on CSP


## 3. Plugins have MOVED!! ##

Without announcement or warning the Cordova team has moved the plugins. Luckily, the previous URL redirects, but some of the URLS &ndash; notably http://plugins.cordova.io/npm/index.html?q= is GONE!!

The rules regarding sourcing your plugins can be rather confusing. The best thing to do is read the blog posts - below. Developers that use CLI can source from github, again see the blog post.

2015-10-09 - Without announcment, tweet, or blog, the repository change a full week before it was scheduled. I can do nothing, but complain.... This is damm annoying.

- NEW NEW [Cordova npm search page](http://cordova.apache.org/plugins/)
- NEW NEW [Cordova CORE plugins](http://cordova.apache.org/docs/en/5.1.1/cordova/plugins/pluginapis.html)
- [Latest version of plugins](http://cordova.apache.org/news/2015/06/22/plugins-release.html) June 22, 2015

- [Cordova Plugins Registry becomes immutable](http://cordova.apache.org/news/2015/09/08/CPR-readonly.html) 2015/09/08
- [Plugins Release and Moving plugins to npm](http://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html) 2015/04/21
- [List of the Latest *Core* Plugins and their versions](http://cordova.apache.org/news/2015/06/22/plugins-release.html) June 22, 2015


## 4. `<feature>` is deprecated ##

`<feature>` tags are deprecated. That means they are no longer used.
You can [read about it here](http://docs.build.phonegap.com/en_US/configuring_features.md.html#Features)

###I QUOTE

> Aside from the `debug-server` feature, the `<feature>` tag is essentially deprecated on *PhoneGap Build* since *PhoneGap APIs* were pluginized. Permissions are now generally managed by individual plugins, and application manifests and permissions can be modified directly using the [config-file element](http://docs.build.phonegap.com/en_US/configuring_config_file_element.md.html). However for backwards-compatibility, they are still supported and map to device permissions on Android and Windows Phone 8:

In other words, you have a duplicate configuration, and it is doing nothing. Take it out.


