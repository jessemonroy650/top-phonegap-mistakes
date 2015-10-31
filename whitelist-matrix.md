# White-list Matrix #
Date: 2015-10-26

If you have never heard of a [decision table](https://en.wikipedia.org/wiki/Decision_table), today you'll learn of the value of them. This easy enough. Start at the top (1.) and continue till to the bottom (9.). If you drop out anywhere along the way. You are done.  

However, the tables in 1., 7., 9., and 10. are short cuts (or aides) to help you get to the right place. You will notice, the tables do not loop back or interconnect. This was intentionally done to help you work in a linear fashion.

This is, in fact, a simple expert system &ndash; with you as the feedback. Meaning, if you discover an error, let me know. I or someone else will adjust this set of tables.


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

```
cordova -v
```

It is recommend that you move to Cordova V4.x as a minimum. Older versions are difficult to support and many plugins do not work correctly.

| Your Version of<br>*Cordova/Phonegap Tools* <sup>¢</sup> | support | notes |
|----------------------------------|---------|-------|
| 2.x | Not support | deprecated |
| 3.x | Available   |  - |
| 4.x | Required    | white-list, plugin |
| 5.x<sup>¥</sup> | Required    | white-list, plugin, CSP |
| Any above AND iOS9<sup>£</sup> | Required | Apple's ATS<sup>§</sup> |

- ¢ = Cordova and Phonegap versions do NOT align, but are close. This version is not the \*pinned* version either. If you do not know the difference, [learn](http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/) &mdash; [official release policy](https://github.com/apache/cordova-coho/blob/master/docs/versioning-and-release-strategy.md).
- ¥ = This include cli-5.1.0 and cli.5.2.0
- £ = As of 2015-10-29, iOS9 is officially **not** supported. ([SEE](http://community.phonegap.com/nitobi/topics/phonegap-build-ios-9-support-status)).
- § = ATS requires &ndash; if you are using Apple's SSL, then the server you connect to [run TLSv1.2](http://ste.vn/2015/06/10/configuring-app-transport-security-ios-9-osx-10-11/)

###2. <a name=guide>Which guide</a>###

For all intensive purpose, there are three (3) whitelist guides. They all have mistakes, lack current information, and suffer from neglect. However, there are important pointers for each platform. So, if you are working on *Windows, Blackberry, Tizen*, or one of the other platform, do read the appropriate guide.

However, the best and most accurate information seems to come from from the documentation for the `whitelist` plugin. It is at the bottom of this list.

1. [Cordova Whitelist Guide](http://cordova.apache.org/docs/en/5.1.1/guide/appdev/whitelist/index.html) - Cordova CLI and SDK
2. [Phonegap Whitelist Guide](http://docs.phonegap.com/en/edge/guide_appdev_whitelist_index.md.html#Whitelist%20Guide) - Phonegap CLI and SDK
3. [Phonegap Build Whitelist Guide](http://docs.build.phonegap.com/en_US/configuring_access_elements.md.html#Access%20Elements) - Phonegap Build only
4. [cordova-plugin-whitelist](https://www.npmjs.com/package/cordova-plugin-whitelist) - npm


###3. <a name=plugin>Which plugin, `whitelist` or `legacy-whitelist`</a>###

[`legacy-whitelist`](https://www.npmjs.com/package/cordova-plugin-legacy-whitelist)

> This plugin implements the Cordova 3.6 Whitelist policy for Cordova 4.0. 

If you implemented the whitelist system for Android before `15 Apr 2015`, then you can still use this system. As of that date, the new `whitelist` plugin is available and it runs with a different set of rules. While the legacy-whitelist` is currently supported, you are strongly recommended to move to the `whitelist` plugin.

[`whitelist`](https://www.npmjs.com/package/cordova-plugin-whitelist)

> This plugin implements a whitelist policy for navigating the application webview on Cordova 4.0

If you have not implemented the `whitelist` system yet, then you want to start here. This plugin has more parameters and has better granularity that the legacy plugin.

##The Cordova `whitelist`##
###4. <a name=navigation>allow-navigation</a>###

Controls which URLs the \*WebView* itself can be navigated to. Applies to top-level navigations only. 

By default, navigations only to `file://` URLs are allowed. To allow other URLs, you must add `<allow-navigation>` tags to your `config.xml`.

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

This is one point where the documentation conflicts with it's self. If you do a search for 'whitelist' on the [documentation](https://www.npmjs.com/package/cordova-plugin-inappbrowser) you will see conflicting lines. The inconsistence in the writing style points to multiple authors, poor design, and neglect. Expect a rewrite.

*In the middle of the  3rd paragraph is*

> The InAppBrowser is not subject to the whitelist, nor is opening links in the system browser.

*In `cordova.InAppBrowser.open()`, under 'target' is*

> _self: Opens in the Cordova WebView, if the URL is in the white list, otherwise it opens in the InAppBrowser.

###8. <a name=config.xml>How do I apply those `config.xml` elements</a>###

<b>FOREWARNED.</b> The documentation suggests that the CSP be used instead of `access origin`. I disagree. CSP is confusing and unclear. However, `access origin` is weak and ripe for more security warnings. There is inconsistency in both methods. *As a developer, you should make an objective decision on this.* <b>FOREWARNED.</b>

| Which XML element  |  Controls  |  Quirks  |
|--------------------|------------|----------|
| `allow-navigation` | [WebView](webview.md)<sup>¿</sup> | *Android* applies this to iframes (non-http(s))
| `allow-intent`     | URL request to system `window.open()`<sup>¿</sup> | *Android* equivalent to BROWSEABLE<br><b>does not apply to plugin</b>
| `access origin`    | Controls network requests (images, XHRs, etc) via Cordova | *Android* makes allowance for [Talkback](http://www.androidcentral.com/what-google-talk-back) <sup>µ</sup><br>th default Cordova application includes `<access origin="*">`

- ¿ = It unclear from the documentation how this interacts with `inappbrowser`.
- µ = The documentation alludes that Android has this built-in.

##W3's CSP##
###9. <a name=csp>CSP (Content Security Policy)</a>###

**Opinion**
> CSP has to be the most *heinous* part of the `whitelist` system. It has sixteen (16) directives and they have overlapping logic. Note, some developer have implemented this in a morning. *You are forewarned.*

The CSP is configured per web page using HTTP headers. Whenever the browser loads an HTML document, the response headers of the HTTP request that delivered the document are used to configure the *content security policy* for all content that originates from this HTML document.

The CSP is configured via a single header (Content-Security-Policy or X-Content-Security-Policy). The value of this header is a string that is effectively a set of directives separated by a semicolon. The directives define a list of sources that are safe to communicate with. There is a directive for each of the resource types such as images, xhr, styles, scripts.

Several websites were culled for information

- [W3.org CSP2](http://www.w3.org/TR/CSP2/)
- [Mozilla CSP Policy Directives](https://developer.mozilla.org/en-US/docs/Web/Security/CSP/CSP_policy_directives)
- [http://content-security-policy.com/](http://content-security-policy.com/)
- [CanIUse](http://caniuse.com/#search=csp)


Each of the directives listed can define one or more sources that are safe to consume. 
You can combine sources, which can include 'CSP Keywords', 'CSP Data(words)', and 'Host (regular) Expressions'. 

**Directives**

| CSP Directives | W3 Section | Governs
|----------------|------------|--------
| base-uri    | 7.1  | restricts the URLs that can be used to specify the document base URL
| child-src   | 7.2  | the nested browsing contexts and the execution of Workers
| connect-src | 7.3  | network activities such as XMLHttpRequest::send
| default-src | 7.4  | sets a default source list for a number of directives
| font-src    | 7.5  | fonts loading
| form-action | 7.6  | form submissions
| frame-ancestors | 7.7  | embedding of iframes, objects, applets etc
| frame-src   | 7.8  | *is deprecated*
| img-src     | 7.9  | loading of images
| media-src   | 7.10 | video and audio sources
| plugin-types | 1.12 | (these are MIME-type plugins, not Cordova)
| report-uri  | 7.13 | a URL to which the user agent sends reports about policy violation
| sandbox     | 7.14 | specifies an HTML sandbox policy that the user agent applies to the protected resource
| object-src  | 7.11 | objects (flash, audio, etc.)
| script-src  | 7.15 | scripts execution
| style-src   | 7.16 | CSS sources

- SEE [W3.org directives](http://www.w3.org/TR/CSP2/#directives) for more details

**CSP Keywords** 

- \*The single quotes are required.*

| CSP Keywords | Meaning
|---------|---------
| 'none' | Refers to the empty set; that is, no URLs match.
| 'self' | Refers to the origin from which the protected document is being served, including the same URL scheme and port number.
| 'unsafe-inline' | Allows the use of inline resources, such as inline `<script>` elements, javascript: URLs, inline event handlers, and inline `<style>` elements.<br>**This is what makes this ridiculous for mobile Apps**<br>  [Early event handlers](http://www.quirksmode.org/js/events_early.html) -- [Working with Inline Event Handlers](http://www.htmlgoodies.com/html5/javascript/working-with-inline-event-handlers.html#fbid=UZJyfkvftFq)
| 'unsafe-eval' | Allows the use of eval() and similar methods for creating code from strings. <br>**What does "similar methods" mean?** No one says.

- SEE [W3.org source list syntax](http://www.w3.org/TR/CSP2/#source-list-syntax) for some details. It is no clear definition or descriptions for these keywords.
- SEE [Mozilla Keywords](https://developer.mozilla.org/en-US/docs/Web/Security/CSP/CSP_policy_directives#Keywords) for some definitions.

**CSP Data** 

| CSP Data(words) | Meaning 
|------|---------|
| data: | Allows `data:` URIs to be used as a content source. This is insecure; an attacker can also inject arbitrary `data:` URIs. Use this sparingly and definitely not for scripts.
| mediastream: | Allows `mediastream:` URIs to be used as a content source.
| blob: | Allows `blob:` URIs to be used as a content source. <br>**This is another ridiculous thing for mobile Apps**
| filesystem: | Allows `filesystem:` URIs to be used as a content source.<br>**This is another ridiculous thing for mobile Apps**
| gap: | *This dataword only applies to Cordova/Phonegap.* At this time, it is only required for iOS. **It is badly documented**

- SEARCH [W3.org CSP2](http://www.w3.org/TR/CSP2/) for some usage rules
- SEE [Mozilla Data](https://developer.mozilla.org/en-US/docs/Web/Security/CSP/CSP_policy_directives#Data) for some description on these words.

**CSP Host (regular) Expressions**

| need add | examples 

There are four (4) documents worth reading on this subject.

- [Content Security Policy Reference](http://content-security-policy.com/) Website
- [CSP Policy Directives](https://developer.mozilla.org/en-US/docs/Web/Security/CSP/CSP_policy_directives#Keywords) - Mozilla
- [Using Content Security Policy to Make Apps More Secure]() - #60devs
- [CSP 2 Directives](http://www.w3.org/TR/CSP2/#directives) - W3.org

## Apple's ATS##
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

