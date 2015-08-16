= NOTES =
Date: 2015-08-15


**ISSUE**

 - 3 dot bubble in phonegap app for settings...
 - https://groups.google.com/forum/#!topic/phonegap/1kPAHbv7OYw

 - PhoneGap Build Android crates floating bubble with 3 dots
 - http://stackoverflow.com/questions/31900356/phonegap-build-android-crates-floating-bubble-with-3-dots

**Affects**

 - Samsung Galaxy S6
 - Motorola ?

**CAUSE**

 - Apparently, Samsung eliminate the [menu] button on some Samsung models. In addition, Android removed the button from the specification. The circle with the three dots is a "soft button" that simulates the [menu].
 - [What is that little circle with three dots inside of it?](http://forums.androidcentral.com/samsung-galaxy-s6/513901-what-little-circle-three-dots-inside.html)
 - [Development Notes: Physical Buttons on Android](https://github.com/jessemonroy650/Phonegap-PhysicalButton-test/blob/master/NOTES.md)

**Solution:**

 - set *minSDK* and *targetSDK* when building

**References to Resolve Issue:**

 - [Phonegap CLI](http://docs.phonegap.com/en/edge/config_ref_pgb_config.md.html) - EDGE
 - [Phonegap Build](http://docs.build.phonegap.com/en_US/3.3.0/configuring_preferences.md.html#Preferences) - 3.3.0

![alt text](./samsung_annoyance.png)

![alt test](./WK4ymSv.png)
