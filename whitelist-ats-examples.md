## ATS Examples ##
Last Update: 2015-11-01

**Turns off all security. - Widely given as an answer.** <sup>[1](#footnotes)</sup>
```
<key>NSAppTransportSecurity</key>
    <dict>
    <key>NSAllowsArbitraryLoads</key>
    <true/>
    </dict>
```

**[Exclude local servers](http://stackoverflow.com/a/32764234/3255670)**
```
<key>NSAppTransportSecurity</key>
<dict>
    <key>NSExceptionDomains</key>
    <dict>
        <key>server.local</key>
        <dict/>
        <key>NSExceptionAllowsInsecureHTTPLoads</key>
        <true/>
    </dict>
</dict>
```

**[ATS General Purpose](http://stackoverflow.com/a/30732693/3255670)**
```
<key>NSAppTransportSecurity</key>
<dict>
    <key>NSExceptionDomains</key>
    <dict>
        <key>testdomain.com</key>
        <dict>
            <key>NSIncludesSubdomains</key>
            <false/>
            <key>NSExceptionAllowsInsecureHTTPLoads</key>
            <false/>
            <key>NSExceptionRequiresForwardSecrecy</key>
            <true/>
            <key>NSExceptionMinimumTLSVersion</key>
            <string>TLSv1.2</string>
            <key>NSThirdPartyExceptionAllowsInsecureHTTPLoads</key>
            <false/>
            <key>NSThirdPartyExceptionRequiresForwardSecrecy</key>
            <true/>
            <key>NSThirdPartyExceptionMinimumTLSVersion</key>
            <string>TLSv1.2</string>
            <key>NSRequiresCertificateTransparency</key>
            <false/>
        </dict>
    </dict>
</dict>
```


####<a name=bydefault>Access By Default</a>####

As of iOS9, all network access is turned off by default.
***NONE.***

####<a name=references>References</a>####

**APPLE** *About the security content of iOS 9.1*<br>
https://support.apple.com/en-us/HT205370<br>
ATS is not listed as an issue.

**APPLE** *Information Property List Key Reference: NSAppTransportSecurity*<br>
https://developer.apple.com/library/ios/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW33

**GOOGLE** *Handling App Transport Security in iOS 9*<br>
http://googleadsdeveloper.blogspot.com/2015/08/handling-app-transport-security-in-ios-9.html

**IONIC** *Preparing for iOS 9*<br>
http://blog.ionic.io/preparing-for-ios-9/

https://github.com/AFNetworking/AFNetworking/issues/2779#issuecomment-112030880<br>

>I want to make sure everyone fully understands this behavior. I spent some time in the labs last week at WWDC, and got the following information.

>Setting NSAllowsArbitraryLoads to true will allow it to work, but Apple was very clear in that they intend to reject apps who use this flag without a specific reason. The main reason to use NSAllowsArbitraryLoads I can think of would be user created content (link sharing, custom web browser, etc). And in this case, Apple still expects you to include exceptions that enforce the ATS for the URLs you are in control of.

>If you do need access to specific URLs that are not served over TLS 1.2, you need to write specific exceptions for those domains, not use NSAllowsArbitraryLoads set to yes. You can find more info in the NSURLSesssion WWDC session.

>Please be careful in sharing the NSAllowsArbitraryLoads solution. It is not the recommended fix from Apple.

Another set of possible answer.<br>
http://stackoverflow.com/a/32764234/3255670

####<a name=usefularticles>Useful Articles</a>####

Cordova 5.3.1 and iOS9 platform - I can't load images and scripts form external sources<br>
http://stackoverflow.com/a/33422392/3255670

Plugin as a solution

    `cordova plugin add cordova-plugin-disable-nsapptransportsecurity`

    https://www.npmjs.com/package/cordova-plugin-disable-nsapptransportsecurity

----


How to Disable App Transport Security - Oct 13, 2015<br>
https://medium.com/five-minute-watchkit/how-to-disable-app-transport-security-2c8d5d298160

Fix iOS 9 App Transport Security Issues In Apache Cordova - Oct 14, 2015<br>
https://blog.nraboy.com/2015/10/fix-ios-9-app-transport-security-issues-in-apache-cordova/
"""
If your Apache Cordova application uses the InAppBrowser plugin to access external resources such as websites, you might have experienced the following error:
"""
> webView:didFailLoadWithError - -1200: An SSL error has occurred and a secure connection to the server cannot be made.

How do I load an HTTP URL with App Transport Security enabled in iOS 9? [duplicate]<br>
http://stackoverflow.com/questions/30731785/how-do-i-load-an-http-url-with-app-transport-security-enabled-in-ios-9/30732693#30732693

Transport Security has Blocked a cleartext HTTP<br>
http://stackoverflow.com/questions/31254725/transport-security-has-blocked-a-cleartext-http?noredirect=1#comment52543453_31254725

####<a name=footnotes>Footnotes</a>####

\#1 This answer was given widely. I suspect this was originally given by Apple. Answer available from [Google](http://googleadsdeveloper.blogspot.com/2015/08/handling-app-transport-security-in-ios-9.html), [Ionic](http://blog.ionic.io/preparing-for-ios-9/), and several blogs list on this page.



