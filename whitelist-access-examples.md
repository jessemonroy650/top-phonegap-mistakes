# whitelist-access-examples #
Date: 2015-11-16<br>
Last Update: 2015-12-12

[`The Whitelist System`](the-whitelist-system.md) -> Whitelist `access` Examples

Purpose: Controls which network requests (images, XHRs, etc) are allowed to be made (via cordova native hooks).

With every major release (1.x,2.x,3.x,4.x,5.x) of Cordova/Phonegap, the `whitelist` system has changed. In the beginning the `<access (...) />` element was limited to `http:` and `https:`; the [W3C RFC](http://www.w3.org/TR/widgets-access/#definitions) stated as much. However, the system and the associated plugin became a catch-all. There was even a `<preference name="websecurity" value="disable" />` for a while. It now appears out of favor.

As of [*Cordova Android* 4.0.0](http://cordova.apache.org/announcements/2015/04/15/cordova-android-4.0.0.html) (15 Apr 2015) and [*Cordova iOS* 4.0.0](http://cordova.apache.org/announcements/2015/12/08/cordova-ios-4.0.0.html) (08 Dec 2015), using the `whitelist` system is required to gain access to "network resources". However, the latest Cordova [cordova-plugin-whitelist](https://github.com/apache/cordova-plugin-whitelist) suggests that the `<access (...) />` element *is mostly historical for webviews which do not support CSP*.

**NOTE** *External Application Whitelist* has morphed into `<allow-intent (..) />` and `<allow-navigation (...) />`. See the [cordova-plugin-whitelist](https://www.npmjs.com/package/cordova-plugin-whitelist) documentation for details.

```
    <!-- Access to all domains. This will likely work for all -->
    <access origin="*" />

    <!-- Access cordova.io via port 80; request is case insensative. -->
    <access origin="http://CORDOVA.io/" />

    <!-- Access cordova.apache.org via port 80.  -->
    <access origin="http://cordova.apache.org/" />

    <!-- Access any subdomain on apache.org via port 80.  -->
    <access origin="http://*.apache.org/" />

    <!-- Access any subdomain on apache.org via port 80.  -->
    <access origin="http://apache.org/" subdomains="true" />

    <!-- Access phonegap.com via port 80  -->
    <access origin="https://phonegap.com/" />

    <!-- Access build.phonegap.com via port 443  -->
    <access origin="https://build.phonegap.com/"  />

    <!-- Access privatedomain.com via port 443  -->
    <access origin="https://privatedomain.com:8080/"  />

    <!-- Access any subdomain on privatedomain.com via port 443  -->
    <access origin="https://privatedomain.com:8080/"  subdomains="true"  />
```


## NOTES, REFERENCES ##

### https://github.com/apache/cordova-plugin-whitelist ###

Without any `<access>` tags, only requests to `file://` URLs are allowed. However, the default Cordova application includes `<access origin="*">` by default.

Quirk: Android also allows requests to https://ssl.gstatic.com/accessibility/javascript/android/ by default, since this is required for TalkBack to function properly.

### http://cordova.apache.org/docs/en/5.4.0/guide/appdev/whitelist/index.html ###

### http://docs.phonegap.com/en/4.0.0/guide_appdev_whitelist_index.md.html#Whitelist%20Guide ###

**Android Whitelisting**

Platform-specific whitelisting rules are found in res/xml/config.xml.

NOTE: On Android 2.3 and before, domain whitelisting only works for href hyperlinks, not referenced resources such as images and scripts. Take steps to avoid scripts from being injected into the application.

NOTE: In order to prevent external URLs such as mailto: from being opened in the Cordova webview as of Cordova 3.6.0, specifying origin="*" will implicity add rules for http and https protocols. If you require access to additional custom protocols, then you should also add them explicity to the whitelist. Also see "External Application Whitelist" below for more information on launching external applications by URL.

NOTE: Some network requests do not go through the Cordova Whitelist. This includes <video> and <audio> resouces, WebSocket connections (on Android 4.4+), and possibly other non-http requests. On Android 4.4+, you can include a CSP header in your HTML documents to restrict access to those resources. On older versions of Android, it may not be possible to restrict them.

### http://www.w3.org/TR/widgets-access/ ###

***Selected Sub-Sections***

2. Definitions

> To grant access means that the user agent authorizes widget execution scopes to retrieve one or more network resources via the user agent. 

    > Some schemes (e.g. mailto:) may be handled by third-party applications and are therefore not controlled by the access mechanism defined in this specification. Similarly, policies defined using this specification do not apply to opening content in external applications. 

> A network resource is a retrievable resource of any media type that is identified by a URI that has a DNS or IP as its authority component [URI]. 

    > This deliberately excludes some schemes (e.g. `sms:`, `tel:`) from being controlled by the means provided by this specification. 

5. Policy

> In the ***default policy***, a user agent must deny access to network resources external to the widget by default, whether this access is requested through APIs (e.g. `XMLHttpRequest`) or through markup (e.g. `iframe`, `script`, `img`). 

6. The `access` Element
6.1 Attributes

- origin - An IRI attribute that defines the specifics of the access request that is made. Only the scheme and authority components can be present in the IRI that this attribute contains ([URI], [RFC3987]). Additionally, an author can use the special value of U+002A ASTERISK (*). This special value provides a means for an author to request from the user agent unrestricted access to network resources. 
- subdomains - A boolean attribute that indicates whether or not the host component part of the access request applies to subdomains (as defined in [RFC1034]) of domain in the origin attribute. The default value when this attribute is absent is false, meaning that access to subdomains is not requested. 


