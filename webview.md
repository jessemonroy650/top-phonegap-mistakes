## Webview ##
Date: 2015-10-15<br>
Last Update: 2016-01-24

These are notes on the webview libraries that are used with Cordova/Phonegap.

- A description of webview and some [alternative libraries](webview-alternatives.md).
- [What is a WebView?](http://developer.telerik.com/featured/what-is-a-webview/)
- See also: [Webkit for Developers](http://www.paulirish.com/2013/webkit-for-developers/) by Paul Irish.
- Some details for these libraries are in [webview-details](webview-details.md)
- [webview-bugs](webview-bugs.md)

NOTE: Some of these libraries are based on [WebKit](https://www.webkit.org/). However, WebKit allows customization. This means not all features apply to all browsers that use WebKit. For a more detailed explaination, read this blog post by Paul Irish - [Webkit for Developers](http://www.paulirish.com/2013/webkit-for-developers/)


### Android ###

- [Webview](http://developer.android.com/reference/android/webkit/WebView.html)
  - As of API 19/KitKat(4.4-4.4.4), webview is based on [Chromium](http://www.chromium.org/Home)
  - As of API 17/Jelly Bean(4.2-4.2.2), private browsing is no longer supported.
  - As of API 6/Eclair(2.0?2.1), support is available for different screen densities, especially `-webkit-device-pixel-ratio` Media queries
  - As of API 3/Cupcake(1.5), Zoom is supported

  - In order to support inline HTML5 video in your application, you need to have hardware acceleration turned on.

[Android version history](https://en.wikipedia.org/wiki/Android_version_history)

### iOS ###

- [WKWebView Class Reference](https://developer.apple.com/library/ios/documentation/WebKit/Reference/WKWebView_Ref/) - Available in iOS 8.0 and later. This is based on WebKit.
- [UIWebView Class Reference](https://developer.apple.com/library/ios/documentation/UIKit/Reference/UIWebView_Class/) - Available in iOS 2.0 and later. In apps that run in iOS 8 and later, use WKWebView instead of this.

### Blackberry 10 ###

- [WebView](https://developer.blackberry.com/native/reference/cascades/bb__cascades__webview.html)

### Windows 10 ###

Finally found it. 2015-11-03

- [WebView](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.webview.aspx)

- [What's new in Windows 10](https://dev.windows.com/en-us/getstarted/whats-new-windows-10#web) - undated

> The WebView control uses the same rendering engine as the new Edge browser. This provides the most accurate, standards-compliant mode of HTML rendering.

- [windows10 tag](http://blogs.windows.com/buildingapps/tag/windows-10/)
- [What?s new in WebView in Windows 8.1](https://blogs.windows.com/buildingapps/2013/07/17/whats-new-in-webview-in-windows-8-1/) - July 17, 2013
- [Ten Things You Need to Know About WebView](http://blogs.msdn.com/b/wsdevsol/archive/2012/10/18/nine-things-you-need-to-know-about-webview.aspx) - 18 Oct 2012

### Tizen ###

- [WebView](https://developer.tizen.org/community/tip-tech/launching-tizen-applications-on-android-platform)

### Firefox OS ###

- nothing yet

### Ubuntu ###

- nothing yet

### Mobile/GeckoView ###

 Bottom line, it's not ready. NOTE, this is not Firefox OS. This is a library intended for Android.

- [Mobile/GeckoView](https://wiki.mozilla.org/Mobile/GeckoView)
- [Outstanding bugs](https://bugzilla.mozilla.org/show_bug.cgi?id=880107) - [meta] Tracking bug for GeckoView embedding work on Android

### Important References ###

1. [ECMAScript 5 compatibility table](http://kangax.github.io/compat-table/es5/)
2. [browser compatibility cheat sheet](http://sheet.shiar.nl/browser)



