## Cordova/Phonegap Known Bugs ##
Last Update: 2015-10-18

### Where you can find the Bug/Issue Respostitories ###
Date: 2015-08-01

If you don't know this by now, you should. Cordova manages the base code that is used for Phonegap and other simmilar systems include, but not limited to, Sencha Touch, Ionic, 

* [Cordova](https://issues.apache.org/jira/browse/CB/?selectedTab=com.atlassian.jira.jira-projects-plugin:issues-panel)
* [Phonegap CLI](https://github.com/phonegap/phonegap-cli/issues)
* [Phonegap Build](https://github.com/phonegap/build/issues/)

Other bugs for other phonegap open source products can be found by walking the tree from the root https://github.com/phonegap/{productName}


### Known Bugs ###

Yes there are more bugs, I just have not seen any yet. 

- Javascript 
- Android
- Windows
- Blackberry
- etc

### iOS Known Bugs ###

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


