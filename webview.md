## Webview ##
Date: 2015-10-15

These are notes on the webviews that are used with Cordova/Phonegap.

NOTE: Some of these libraries are based on [WebKit](https://www.webkit.org/). However, WebKit allows customization. This means not all features apply to all browsers that use WebKit as there base. For a more detailed explaination, read this blog post by Paul Irish - [Webkit for Developers](http://www.paulirish.com/2013/webkit-for-developers/)


###Android###

- [Webview](http://developer.android.com/reference/android/webkit/WebView.html)
  - As of API 17/Jelly Bean, private browsing is no longer supported.
  - As of API 19/KitKat, webview is based on [Chromium](http://www.chromium.org/Home)

[Android version history](https://en.wikipedia.org/wiki/Android_version_history)

###iOS###

- [WKWebView Class Reference](https://developer.apple.com/library/ios/documentation/WebKit/Reference/WKWebView_Ref/) - Available in iOS 8.0 and later. This is based on WebKit.
- [UIWebView Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIWebView_Class/) - Available in iOS 2.0 and later. In apps that run in iOS 8 and later, use WKWebView instead of this.

###Blackberry 10###

- [WebView](https://developer.blackberry.com/native/reference/cascades/bb__cascades__webview.html)

###Windows 10###

- [What's new in Windows 10](https://dev.windows.com/en-us/getstarted/whats-new-windows-10#web) - undated

> The WebView control uses the same rendering engine as the new Edge browser. This provides the most accurate, standards-compliant mode of HTML rendering.

- [windows10 tag](http://blogs.windows.com/buildingapps/tag/windows-10/)
- [What?s new in WebView in Windows 8.1](https://blogs.windows.com/buildingapps/2013/07/17/whats-new-in-webview-in-windows-8-1/) - July 17, 2013
- [Ten Things You Need to Know About WebView](http://blogs.msdn.com/b/wsdevsol/archive/2012/10/18/nine-things-you-need-to-know-about-webview.aspx) - 18 Oct 2012

###Tizen###

- [WebView](https://developer.tizen.org/community/tip-tech/launching-tizen-applications-on-android-platform)

###Firefox OS###

- nothing yet

###Ubuntu###

- nothing yet

###Mobile/GeckoView###

 Bottom line, it's not ready. NOTE, this is not Firefox OS. This is a library intended for Android.

- [Mobile/GeckoView](https://wiki.mozilla.org/Mobile/GeckoView)
- [Outstanding bugs](https://bugzilla.mozilla.org/show_bug.cgi?id=880107)
