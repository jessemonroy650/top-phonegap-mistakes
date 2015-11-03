## Cordova/Phonegap Known Bugs ##
Last Update: 2015-10-18

### Where you can find the Bug/Issue Respostitories ###
Date: 2015-08-01

If you don't know this by now, you should. Cordova manages the base code that is used for Phonegap and other simmilar systems include, but not limited to, Sencha Touch, Ionic, 

* [Cordova](https://issues.apache.org/jira/browse/CB/?selectedTab=com.atlassian.jira.jira-projects-plugin:issues-panel)
* [Phonegap CLI](https://github.com/phonegap/phonegap-cli/issues)
* [Phonegap Build](https://github.com/phonegap/build/issues/)

Other bugs for other phonegap open source products can be found by walking the tree from the root https://github.com/phonegap/{productName}

### <a name=otherKnownBugs>Other Known Bugs</a> ###

Yes there are more bugs, I just have not seen any yet. 

- Javascript 
- Android
- Windows
- Blackberry
- etc


### <a name=androidKnownBugs>Android Known Bugs</a> ###

* *Google No Longer Provides Patches for WebView Jelly Bean and Prior*
* https://web.archive.org/web/20150905130759/https://community.rapid7.com/community/metasploit/blog/2015/01/11/google-no-longer-provides-patches-for-webview-jelly-bean-and-prior
> Over the past year, independent researcher Rafay Baloch (of "Rafay's Hacking Articles") and Rapid7's Joe Vennix have been knocking out Android WebView exploits somewhat routinely, based both on published research and original findings. Today, Metasploit ships with 11 such exploits, thanks to Rafay, Joe, and the rest of the open source security community. Generally speaking, these exploits affect "only" Android 4.3 and prior -- either native Android 4.3, or apps built with 4.3 WebView compatibility
>
> Google responds: 
> > If the affected version [of WebView] is before 4.4, we generally do not develop the patches ourselves, but welcome patches with the report for consideration. Other than notifying OEMs, we will not be able to take action on any report that is affecting versions before 4.4 that are not accompanied with a patch.

### <a name=iOSKnownBugs>iOS Known Bugs</a> ###

* *Facebook Says It Fixed A Bug That Caused Silent Audio To Vampire Your iPhone Battery*
* http://techcrunch.com/2015/10/22/facebook-says-it-fixed-a-bug-that-caused-silent-audio-to-vampire-your-iphone-battery/#.n72ctj:3Z2C

* *IPhone 6s: Display bug affecting users who restored backup from older iPhones* - October 4, 2015
* http://rapidnewsnetwork.com/iphone-6s-display-bug-affecting-users-who-restored-backup-from-older-iphones/208835/

* *app scaling in iOS9* (Official Reply) - Sept 28, 2015
* http://community.phonegap.com/nitobi/topics/app-scaling-in-ios9#reply_16164009

[AmsterdamInc reports](http://community.phonegap.com/nitobi/topics/app-scaling-in-ios9#reply_16153350).

> I can confirm that this issue was caused by one of the iOS splash screen png files missing for the 667h and 736h dimensions. Apparently in iOS 9 this is now a hard requirement, compared to iOS 8, or handled differently by Phonegap.

> Strange impact for the same app on the same phone and screen when the issue is related to this splash screen only. Anyway, I suppose this should fix some other apps as well so please double check if all the (latest) 14 iOS splash screen files are included. 

* File Input from PhoneGap 5.2.0 on iOS9 - No longer works
* https://issues.apache.org/jira/browse/CB-9725

* *[Build] cli-5.2.0 cause app cannot install on iOS*
* https://github.com/phonegap/build/issues/468

* *input type file doesn't work on iOS 9*
* https://github.com/phonegap/build/issues/470
* Creates https://issues.apache.org/jira/browse/CB-9688

### <a name=iOSSuspectedBugs>iOS Suspected Bugs</a> ###

* Bug: `tel:` not working with InAppBrowser (whitelist was checked)
* Titled: Cordova InAppBrowser not working with iOS
* http://stackoverflow.com/questions/33034398/cordova-inappbrowser-not-working-with-ios
* Conclusion reached on 2015-10-18

### <a name=ionicKnownBugs>Ionic Known Bugs</a> ###

* Preparing for iOS 9 - Sept 12, 2015
* http://community.phonegap.com/nitobi/topics/sfsafariviewcontroller-webview-alternative-for-ios9-or-better?rfm=1
* window.location bug
* Radio button issue
* App Transport Security
