## Notes on Webview Alternatives ##
Date: 2015-09-10<br />
Google: [phonegap webview](https://www.google.com/search?q=phonegap+webview)

Notes on the webviews used by [Cordova/Phonegap are here](webview.md)

Cordova/PhoneGap is an application container technology that allows you to create natively-installed applications for mobile devices using HTML, CSS, and JavaScript.

The UI (user interface) for PhoneGap applications is created using HTML, CSS, and JavaScript. The UI layer of a PhoneGap application is a library - colloquially known as *webview*. It uses up to 100% of the device width and 100% of the device height 

Think of *webview* as a "chrome-less" web browser.  It renders HTML content, without the "chrome" or window decoration of a regular web browser.  You build your application to take advantage of this space,  and you build navigational/interactive/content elements and the application chrome into your HTML and CSS based user interface.

On iOS, this is the Objective-C UIWebView class; on Android, this is android.webkit.WebView.

* *[PhoneGap Explained Visually](http://phonegap.com/2012/05/02/phonegap-explained-visually/)*
* *[PhoneGap: a misunderstood hybrid framework](http://www.asyncdev.net/2012/10/phonegap-a-misunderstood-hybrid-framework/)*

NOTE: Some of these libraries are based on [WebKit](https://www.webkit.org/). However, WebKit allows customization. This means not all features apply to all browsers that use WebKit as there base.

Google: [webview alternative](https://www.google.com/search?q=webview+alternative)

### Webview Alternatives ###

1. [Crosswalk](https://crosswalk-project.org/) an x86 version of the plugin to PGB: https://build.phonegap.com/plugins/4652
2. [WKWebView](https://github.com/Telerik-Verified-Plugins/WKWebView) an alternative for **iOS**
3. [cordova-plugin-safariviewcontroller](https://github.com/EddyVerbruggen/cordova-plugin-safariviewcontroller)
### Work in Progress ###

1. [WinRT XAML Toolkit](http://winrtxamltoolkit.codeplex.com/) - work in progress (last update may 2014) for **Windows** Runtime using XAML supports Windows 8+


### Available, but Not Useful ###

1. [GeckoView](http://starkravingfinkle.org/blog/2013/10/geckoview-embedding-gecko-in-your-android-application/) - As mentioned in the project page, we don?t intend GeckoView to be a drop-in replacement for WebView. Internally, Gecko is very different from Webkit and trying to expose the same features using the same APIs just wouldn?t be scalable or maintainable.
2. [Zirco](http://code.google.com/p/zirco-browser/source/browse/trunk/src/org/zirco/ui/components/CustomWebView.java?r=435) - an open-source alternative browser for Android. The code is READ-ONLY mode. [The browser itself](https://code.google.com/p/zirco-browser/) is still available on [Google Play](https://play.google.com/store/apps/details?id=org.zirco&hl=en).
3. [JavaFX](https://docs.oracle.com/javafx/2/webview/jfxpub-webview.htm) - A tutorial entitled  *Adding HTML Content to JavaFX Applications*
4. [WebView QML Type](http://doc.qt.io/qt-5/qml-qtwebkit-webview.html) - This is a webview library, but ther are no indications this has been ported to Android or other mobile systems.
3. [SFSafariViewController](https://developer.apple.com/library/prerelease/ios/documentation/SafariServices/Reference/SFSafariViewController_Ref/index.html#//apple_ref/occ/cl/SFSafariViewController) - It shares cookies and other website data with Safari, and has many of Safari's great features, such as Safari AutoFill and Safari Reader. **iOS, noticed with iOS9** [SEE](http://community.phonegap.com/nitobi/topics/sfsafariviewcontroller-webview-alternative-for-ios9-or-better)


### Important Articles Regarding Android ###

* *Migrating to WebView in Android 4.4* - undated
* https://developer.android.com/guide/webapps/migrating.html
* This is important when using the stock webview. The breakpoint, or Cordova equivalent, is Cordova 4.0.0. This library handles Multi-threading, amount other things.
> Android 4.4 (API level 19) introduces a new version of WebView that is based on Chromium. This change upgrades WebView performance and standards support for HTML5, CSS3, and JavaScript to match the latest web browsers. Any apps using WebView will inherit these upgrades when running on Android 4.4 and higher.

> Note: If your targetSdkVersion is set to "18" or lower, WebView operates in "quirks mode" in order to avoid some of the behavior changes described below, as closely as possible?while still providing your app the performance and web standards upgrades. (...)

* *Chrome custom tabs smooth the transition between apps and the web* - September 2, 2015
* http://blog.chromium.org/2015/09/chrome-custom-tabs-smooth-transition_2.html
* *Custom Tabs* is likely the basis for [InAppBrowser](https://www.npmjs.com/package/cordova-plugin-inappbrowser) - [Developer's Guide](https://developer.chrome.com/multidevice/android/customtabs)

* *Run Chrome Apps on Mobile Using Apache Cordova* - undated
* https://developer.chrome.com/apps/chrome_apps_on_mobile
* This undated article was likely release before Cordova 4.0.0.

* *Developing Native Apps with HTML5 and Apache Cordova* - updated 10/04/2015 
* http://www.hippopunk.com/en/native-apps-with-html5-development
* Discusses some of the common issues with using the factory installed webview library and discusses some other alternatives.

* *How To Use iOS WKWebView with UIWebView Fallback* - December 3, 2014
* http://floatlearning.com/2014/12/one-webview-to-rule-them-all/
> iOS 8 finally gave developers access to a WebKit-powered Web view, called simply WKWebView.

> Previously, the much slower UIWebView was the only tool at an iOS developer?s disposal, but the new WKWebView allowed us to bring users the same 60fps high-performance browsing behind mobile Safari.

* *Easy Android App Development with Webview*
* http://www.human-element.com/easy-android-app-development-webview/
* Note: This is Java-only code, intended for building your own webview.
> If you are trying to build your own app, then this is what you came here for. Who cares about this paragraph, *just give me the code samples*. I know how it is. That?s why I included COMPLETE examples, instead of just bits and pieces.

* *WebView*
* http://www.b4x.com/android/wiki/index.php/WebView
* Yet another tutorial to build your own webview.
> The WebView view uses the internal WebKit engine to display Html pages. The page displayed can be an online page loaded with LoadUrl or an Html string loaded with LoadHtml.

* *Android Tutorial for Beginners 20 # Android WebView Example* - Feb 2015
* https://www.youtube.com/watch?v=nB-relROsrY

### Important References ###

1. [ECMAScript 5 compatibility table](http://kangax.github.io/compat-table/es5/)
2. [browser compatibility cheat sheet](http://sheet.shiar.nl/browser)
3. [Optimizing content for different browsers: the RIGHT way](https://www.w3.org/community/webed/wiki/Optimizing_content_for_different_browsers:_the_RIGHT_way)
4. [How to Make All Browsers Render HTML5 Mark-up Correctly](http://code.tutsplus.com/tutorials/how-to-make-all-browsers-render-html5-mark-up-correctly-even-ie6--net-8669)

