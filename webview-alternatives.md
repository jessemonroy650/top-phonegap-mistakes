## Notes on Webview Alternatives ##
Date: 2015-09-10
Google: phonegap webview

PhoneGap is an application container technology that allows you to create natively-installed applications for mobile devices using HTML, CSS, and JavaScript.

The user interface for PhoneGap applications is created using HTML, CSS, and JavaScript. The UI layer of a PhoneGap application is a web browser view that takes up 100% of the device width and 100% of  the device height.

Think of this as a "chrome-less" web browser.  It renders HTML content, without the "chrome" or window decoration of a regular web browser.  You build your application to take advantage of this space,  and you build navigational/interactive/content elements and application chrome into your HTML and CSS based user interface.

On iOS, this is the Objective-C UIWebView class; on Android, this is android.webkit.WebView.

*PhoneGap Explained Visually*
http://phonegap.com/2012/05/02/phonegap-explained-visually/

*Another explaination*
http://www.asyncdev.net/2012/10/phonegap-a-misunderstood-hybrid-framework/


* [Crosswalk](https://crosswalk-project.org/)
** an x86 version of the plugin to PGB: https://build.phonegap.com/plugins/4652
* [WKWebView](https://github.com/Telerik-Verified-Plugins/WKWebView)
** an alternative for iOS
* [CocoonJs](https://www.ludei.com/landing/cocoonjs-phonegap/)
