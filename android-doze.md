## Android Doze ###
Date: 2015-11-27<br>
Last Upate: 2015-11-27

New as of Android 6.0 (Marshmallow).

- Android (Official) [Optimizing for Doze and App Standby](http://developer.android.com/training/monitoring-device-state/doze-standby.html)

- PR:phonegap-plugin-push
 [Android required permissions](https://github.com/phonegap/phonegap-plugin-push/issues/258)

### Official Blogs ###

- [How Google Cloud Messaging handles Doze in Android 6.0 Marshmallow](http://android-developers.blogspot.com/2015/10/how-google-cloud-messaging-handles-doze.html) - 01 October 2015

    > GCM has two priority types for messages, called high priority and normal priority. When using high priority, GCM attempts to deliver messages immediately, waking a device in Doze, as needed. (...) However, when using normal priority (the default priority), there are a number of different behaviors when the device is in Doze (...). 1. most important change is that messages will be batched (...) 2. We **discard** messages whose time_to_live expires while the device is in Doze (including TTL=0).

- [Android M Developer Preview & Tools](http://android-developers.blogspot.com/2015/05/android-m-developer-preview-tools.html) - 28 May 2015

    > *Battery* - We?re making Android devices smarter about managing power through a new feature called **Doze**. With M, Android uses significant motion detection to learn if a device has been left unattended for a while. In this state, Android will exponentially back off background activity, trading off a little bit of app freshness for longer battery life. Consider how this may affect your app; for instance, if you?re building a chat app, you may want to make use of high priority messages to wake your app when the device is dozing.


### Blogs Related ###

- Boxcar.io: [Take your Android app to the next Push level](http://developer.boxcar.io/blog/2015-09-23-take-your-app-to-the-next-push-level/) - Sept 23, 2015
- plotprojects.com: [Dangerous permissions on Android Marshmallow](http://www.plotprojects.com/dangerous-permissions-on-android-marshmallow/) - September 30, 2015
- radius Networks: [Is Your Beacon App Ready for Android 6.0?](http://developer.radiusnetworks.com/2015/09/29/is-your-beacon-app-ready-for-android-6.html) - 29 Sep 2015

### Articles Related ###

- infoQ [Android Marshmallow Rollout Started](http://www.infoq.com/news/2015/10/android-marshmallow-rollout) - Oct 06, 2015
- indianexpress.com [Android M aka Marshmallow: Doze to app permissions, five features that matter](http://indianexpress.com/article/technology/tech-news-technology/android-6-0-marshmallow-update-5-features-you-need-to-know/) - October 6, 2015
- techtub.in [Android M: 5 hidden features you should know about](http://techtub.in/android-m-5-hidden-features-you-should-know-about/) - June 3, 2015
- infoQ [Breaking Changes in Android MBreaking Changes in Android M](http://www.infoq.com/news/2015/05/android-m) - May 29, 2015
