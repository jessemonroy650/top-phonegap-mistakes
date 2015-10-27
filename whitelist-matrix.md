# White-list Matrix #
Date: 2015-10-26

Often I think someone at Microsoft designed this, but then I realize that the entire things was the product of multiple committes working indepently - with no real design criteria, it all makes sense.

If you have never heard of a [decision table](https://en.wikipedia.org/wiki/Decision_table), today you'll learn of the value of them. This easy enough. Start at the top (1.) and continue till to the bottom (9.). If you drop out anywhere along the way. You are done.  However, the tables in 1., 7., 

The table does not loop back or interconnect. This is, in fact, a simple expert system &ndash; with you as the feedback. Meaning, if you discover an error, let me know. I or someone else will adjust this set of tables.


1. [Is my version of Cordova/Phonegap included](#version)?
2. [Which `whitelist` guide should I use](#guide)?
3. [Which plugin, `whitelist` or `legacy-whitelist`](#plugin)?
4. [Do I have to apply `allow-navigation`](#navigation)?
5. [Do I have to apply `allow-intent`](#intent)?
6. [Do I have to apply `access origin`](#access)?
7. [How does this affect `inappbrowser`](#inappbrowser)?
8. [How do I apply those `config.xml` elements](#config.xml)?
9. [CSP (Content Security Policy)](#csp)?
10. [ATS](#ats)?

###1. <a name=version>Is my version of Cordova/Phonegap included</a>###

| Your Version of<br>*Cordova/Phonegap Tools* <sup>¢</sup> | support | notes |
|----------------------------------|---------|-------|
| 2.x | Not support | deprecated |
| 3.x | Available   |  - |
| 4.x | Required    | white-list, plugin |
| 5.x<sup>¥</sup> | Required    | white-list, plugin, CSP |
| Any above AND iOS9<sup>£</sup> | Required | Apple's ATS<sup>§</sup> |

- ¢ = Cordova and Phonegap versions do NOT align, but are close. This version is not the \*pinned* version either. If you do not know the difference, [learn](http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/) - [official release policy](https://github.com/apache/cordova-coho/blob/master/docs/versioning-and-release-strategy.md).
- ¥ = This include cli-5.1.0 and cli.5.2.0
- £ = As of 2015-10-28, iOS9 is officially **not** supported until *Cordova iOS 4.0.0* is released ([SEE](http://community.phonegap.com/nitobi/topics/phonegap-build-ios-9-support-status)).
- § = ATS requires &ndash; if you are using Apple's SSL, then the server you connect to [run TLSv1.2](http://ste.vn/2015/06/10/configuring-app-transport-security-ios-9-osx-10-11/)

###2. <a name=guide>Which guide</a>###

For all intensive purpose, there are three (3) whitelist guides. They all have mistakes, lack current information, and suffer from neglect. However, there are important pointers for each platform. So, if you are working on *Windows, Blackberry, Tizen*, or one of the other platform, do read the appropriate guide. 

1. [Cordova Whitelist Guide](http://cordova.apache.org/docs/en/5.1.1/guide/appdev/whitelist/index.html) - Cordova CLI and SDK
2. [Phonegap Whitelist Guide](http://docs.phonegap.com/en/edge/guide_appdev_whitelist_index.md.html#Whitelist%20Guide) - Phonegap CLI and SDK
3. [Phonegap Build Whitelist Guide](http://docs.build.phonegap.com/en_US/configuring_access_elements.md.html#Access%20Elements) - Phonegap Build only


###3. <a name=plugin>Which plugin, `whitelist` or `legacy-whitelist`</a>###

`legacy-whitelist`

> This plugin implements the Cordova 3.6 Whitelist policy for Cordova 4.0. 

If you implemented the whitelist system for Android before `15 Apr 2015`, then you can still use this system. As of that date, the new `whitelist` plugin is available and it runs with a different set of rules. However, the `legacy-whitelist` is also available and is currently support - but not likely much longer.

`whitelist`

> This plugin implements a whitelist policy for navigating the application webview on Cordova 4.0

If you have not implemented the whitelist system yet, then you want to start here. This plugin has more parameters and has better granularity that the legacy plugin.

###4. <a name=navigation>allow-navigation</a>###

Controls which URLs the \*WebView* itself can be navigated to. Applies to top-level navigations only. 

By default, navigations only to `file://` URLs, are allowed. To allow other other URLs, you must add `<allow-navigation>` tags to your `config.xml`.

*Quirks:* On Android, it also applies to iframes for non-http(s) schemes.

**DANGEROUS-SETTING:** `<allow-navigation href="*" />`

###5. <a name=intent>allow-intent</a>###

Controls which URLs the app is allowed to ask the \*system* to open. By default, no external URLs are allowed.

This whitelist does not apply to plugins, only hyperlinks and calls to `window.open()`.

*Quirks:* On Android, this equates to sending an intent of type BROWSEABLE.

**DANGEROUS-SETTING:** `<allow-intent href="*" />`

###6. <a name=access>access origin</a>###

Controls which network requests (images, XHRs, etc) are allowed to be made (via cordova native hooks).

Without any `<access>` tags, only requests to `file://` URLs are allowed. However, the default Cordova application includes `<access origin="*">` by default.

*Quirk:* Android also allows requests to `https://ssl.gstatic.com/accessibility/javascript/android/` by default, since this is required for TalkBack to function properly.

**DANGEROUS-SETTING:** `<access origin="*" />`

###7. <a name=inappbrowser>inappbrowser</a>###

This one point where the documentation conflicts itself. If you do a search for `whitelist` you will see do different conflicting lines. The poor design here indicates that this will be re-written. The inconsistence in the writing style points to multiple authors, hence the neglect.

*In the middle of the  3rd paragraph is*

> The InAppBrowser is not subject to the whitelist, nor is opening links in the system browser.

*In `cordova.InAppBrowser.open()`, under 'target' is*

> _self: Opens in the Cordova WebView if the URL is in the white list, otherwise it opens in the InAppBrowser.

###8. <a name=config.xml>How do I apply those `config.xml` elements</a>###

The documentation suggests that the CSP be used instead of `access origin`. I disagree. CSP is confusing and unclear. Further the design by committee lends it ripe for a re-write. In addition, the inconsitency with inappbrowser adds to more confusion.

| Which XML element  |  Controls  |  Quirks  |
|--------------------|------------|----------|
| `allow-navigation` | [WebView](webview.md)<sup>¿</sup> | *Android* applies this to iframes (non-http(s))
| `allow-intent`     | URL request to system `window.open()`<sup>¿</sup> | *Android* equivalent to BROWSEABLE
| `access origin`    | Controls network requests (images, XHRs, etc) via Cordova | *Android* makes allowance for [Talkback](http://www.androidcentral.com/what-google-talk-back) <sup>µ</sup>

- ¿ = It unclear how this interacts with `inappbrowser`
- µ = The documentation alludes that Android has this built-in.

###9. <a name=csp>CSP (Content Security Policy)</a>###

CSP has to be the most heinous part of the `whitelist` system. It has sixteen (16) directives and they have overlapping logic. I can safely predict this will be rewritten.

The CSP is configured per web page using HTTP headers. Whenever the browser loads an HTML document, the response headers of the HTTP request that delivered the document are used to configure the *content security policy* for all content that originates from this HTML document.

The CSP is configured via a single header (Content-Security-Policy or X-Content-Security-Policy). The value of this header is a string that is effectively a set of directives separated by a semicolon. The directives define a list of sources that are safe to communicate with. There is a directive for each of the resource types such as images, xhr, styles, scripts.


Each of the directives listed can define one or more sources that are safe to consume. 
You can combine sources, which can include 'CSP Keywords', 'CSP Data(words)', and 'Host (regular) Expressions'. 

**Directives**

| CSP Directives | Governs
|-----------|--------
| child-src   | the nested browsing contexts and the execution of Workers
| connect-src | network activities such as XMLHttpRequest::send
| font-src    | fonts loading
| form-action | form submissions
| frame-ancestors | embedding of iframes, objects, applets etc
| img-src     | loading of images
| media-src   | video and audio sources
| object-src  | plugins
| script-src  | scripts execution
| style-src   | CSS sources
| (more)      | SEE [W3.org directives](http://www.w3.org/TR/CSP2/#directives)


**CSP Keywords** 

- \*The single quotes are required.*

| CSP Keywords | Meaning
|---------|---------
| 'none' | Refers to the empty set; that is, no URLs match.
| 'self' | Refers to the origin from which the protected document is being served, including the same URL scheme and port number.
| 'unsafe-inline' | Allows the use of inline resources, such as inline `<script>` elements, javascript: URLs, inline event handlers, and inline `<style>` elements.<br>**This is what makes this ridiculous for mobile Apps**
| 'unsafe-eval' | Allows the use of eval() and similar methods for creating code from strings. <br>**What does "similar methods" mean**

**CSP Data** 

| CSP Data(words) | Meaning 
|------|---------|
| data: | Allows data: URIs to be used as a content source. This is insecure; an attacker can also inject arbitrary data: URIs. Use this sparingly and definitely not for scripts.
| mediastream: | Allows mediastream: URIs to be used as a content source.
| blob: | Allows blob: URIs to be used as a content source. <br>**This is another ridiculous thing for mobile Apps**
| filesystem: | Allows filesystem: URIs to be used as a content source.<br>**This is another ridiculous thing for mobile Apps**
| gap: | This is required for iOS. **It is badly documented**

**CSP Host (regular) Expressions**

| need add | examples 

There are four (4) documents worth reading on this subject.

- [Content Security Policy Reference](http://content-security-policy.com/) Website
- [CSP Policy Directives](https://developer.mozilla.org/en-US/docs/Web/Security/CSP/CSP_policy_directives#Keywords) - Mozilla
- [Using Content Security Policy to Make Apps More Secure]() - #60devs
- [CSP 2 Directives](http://www.w3.org/TR/CSP2/#directives) - W3.org

###10. <a name=ats>ATS</a>###


----

When I say the information about the `whitelist` system was buried, I mean these three (3) blog posts

Plugins Release and Moving plugins to npm: April 21, 2015
SEE: New Whitelist Plugins
https://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html

Apache Cordova Android 4.0.0: 15 Apr 2015
SEE: Major Changes 
http://cordova.apache.org/announcements/2015/04/15/cordova-android-4.0.0.html
- CSP is now supported
- Network requests are blocked by default without the plugin
- latest default app created by cordova-cli will include this plugin by default

SEE: org.apache.cordova.inappbrowser@0.5.4
http://cordova.apache.org/announcements/2015/04/15/cordova-android-4.0.0.html

