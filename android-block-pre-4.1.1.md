# android-block-pre-4.1.1 #
Date: 2016-02-09 <br>
Last Update: 2016-03-05

Google recently sent out an alert stating, in short:

> ***Beginning May 9, 2016***, *Google Play will block publishing of any new apps or updates that use pre-4.1.1 versions of Apache Cordova.*

Google's Alert: [How to fix apps with Apache Cordova vulnerabilities](https://support.google.com/faqs/answer/6325474)

- **Recommended solution:** Upgrade to 4.3.1 because of [security issue](https://cordova.apache.org/news/2015/06/04/tools-release.html)
- **Stated solution:** Upgrade to 4.1.1
- **Solutions:** vary base on vulnerablity


## At Issue ##

- [CVE-2015-5256](https://cordova.apache.org/announcements/2015/11/20/security.html)

    > Android applications created using Apache Cordova that use a remote server contain a vulnerability where whitelist restrictions are not properly applied. Improperly crafted URIs could be used to circumvent the whitelist, allowing for the execution of non-whitelisted Javascript.
    - **Stated solution:** Upgrade to 4.1.0
    - **Solution:** Upgrade or Do not use a remote server.
- [CVE-2015-1835](http://cordova.apache.org/announcements/2015/05/26/android-402.html)

    > Android applications built with the Cordova framework that don't have explicit values set in Config.xml can have undefined configuration variables set by Intent. This can cause unwanted dialogs appearing in applications and changes in the application behaviour that can include the app force-closing.
    - **Stated solution:** Upgrade to 3.7.2 or 4.0.2
    - **Solution:** *Need to do more research* 
- [CVE-2014-3502](http://cordova.apache.org/announcements/2014/08/04/android-351.html)

    >  A specially-crafted URL could cause the Cordova-based application to start up with a different start page than the developer intended, including other HTML content stored on the Android device. This has been the case in all released versions of Cordova up to 3.5.0, and has been fixed in the latest release (3.5.1).
    - **Stated solution:** Upgrade to 3.5.1
    - **Solution:** Only one, \*\*upgrade now\*\* to 3.7.2 or 4.0.2.

### [CVE-2015-1835](http://cordova.apache.org/announcements/2015/05/26/android-402.html) In Depth ###

The security issue reported on May 27, 2015 by Trend Micro is entitiled:

[Trend Micro Discovers Apache Cordova Vulnerability that Allows One-Click Modification of Android Apps](http://blog.trendmicro.com/trendlabs-security-intelligence/trend-micro-discovers-apache-vulnerability-that-allows-one-click-modification-of-android-apps/)

- Versions at issue - All version from 0.9.3 (November 2010) thru Cordova Android 4.0.1 (A fix was applied to [4.0.2 on 26 May 2015](https://cordova.apache.org/announcements/2015/05/26/android-402.html))
- Attack vector - unset preferences are set from an `Intent` bundle (or external Java code)
    >  Quote from bulletin: *(It) means that it is accessible from outside the app, so attackers can inject malicious intent bundles to the activity to tamper the build-in characteristics of app, either from remote web servers, or local compromised apps.*
- Possible Solutions other than upgrading - Set the ALL the preferences for the app, even if set to the default value.





