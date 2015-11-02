## Cordova/Phonegap the white-list system ##

Can you spell disaster? 

- **FOREWARNED.** *This document is NOT all inclusive, nor does  it cover every exception. This blog entry is a road map to understanding. It is intended for professionals. If you are new to programming and mobile in particular, you will find this confusing and frustrating.* **FOREWARNED.**

[Multiple security bugs](security-issues.md) have perhaps influenced this `white-list`. It is a result of this, or because of this, that the `white-list` system was not completely documented. Add to that the back to back *unannounced changes* to the Cordova system, and I feel like I am catching a falling knife &ndash; without a handle!!

**What Reading is Below**

- Background 
- The legacy whitelist plugin
- How it Works
- What you should watch for
- Samples
- Ionic Issues
- Security bugs
- Unannounced changes
- Documentation Issues

###Background###

Poor coding and standards have led to numerous security bugs (see below) being introduced into web based applications, both desktop and in the various mobile apps. Coders made incorrect assumptions and poor coding, opening up attack vectors and lax security on servers meant that web applications and browsers were being subverted on a regular basis.

The uses of whitelists and the Content Security Policy (CSP) tag are meant as a way of bringing security back to browsers and web applications. 

*The principle behind* the use of whitelists and CSP is simple. The programmer defines what resources they wish to use and connect to in advance. For each request that goes out, the client browser or application checks to see that the request for a resource such as a JSON file, a css file, an image or whatever is allowed. It also checks that the request that comes back is from the right server. The whitelist forces (in a nice way) a programmer to consider which resources they need to use and to define this in advance. Cordova V4.0 and later forces you to use whitelists. 

The Cordova whitelist plugin and CSP are complementary; whilst the plugin is clearly aimed at the Cordova/PhoneGap community, CSP appears to be aimed more at web browsers. The section below on CSP covers the various permutations of having and not having the whitelist plugin and the CSP tag.

This website provides an excellent description of CSP

http://www.html5rocks.com/en/tutorials/security/content-security-policy/

###The Legacy whitelist plugin###

There are currently two (2) plugins available form Cordova for implementing the `whitelist` system. There is the [Cordova whitelist plugin](https://github.com/apache/cordova-plugin-whitelist) and also a [legacy whitelist plugin](https://github.com/apache/cordova-plugin-legacy-whitelist). The new plugin simply extends the old way of doing things, with the whitelist plugins pre-Cordova V4.0. 

*Using the legacy plugin is* ***NOT*** *recommended for long term or even medium term use. Instead, use the new [Cordova whitelist plugin]() and make your code more secure.*

### How it Works ###


**IN THE FUTURE, THIS SECTION WILL HAVE ITEMS MOVED OR DELETED.**

- *To explain this clearly, there is [a matrix](whitelist-matrix.md).* It is separate from this document.

1. Version controls when you need to use it
  - Starting with Cordova 4.0.0 the white-list is required
  - After 5.0.0, there are additional rules which [Raymond Camden](http://www.raymondcamden.com/2015/05/25/important-information-about-cordova-5), dated May of 2015 alludes to
  - The alternative is this quick fix &ndash; but know that this *quick fix* removes all needs for `white-list`. This creates a [security issue](http://www.androidauthority.com/google-webview-security-582363/) which you may not want to by pass.
  - **QUICK FIX** Add this to your `config.xml` **for PHONEGAP BUILD ONLY** <br />
  - `<preference name="phonegap-version" value="3.7.0" />`
  - For *Cordova/Phonegap CLI* see [Cordova/PhoneGap Version Confusion](http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/) - Outdated, but useful

2. [plugin](https://www.npmjs.com/package/cordova-plugin-whitelist)
  - The one you want is `cordova-plugin-whitelist`
  - While some advise using not using version numbers so you get the "latest and greatest", the side effect is that in future upgrades your code will break in unexpectecd ways.
  - The developer is advised to make an "objective" decision
  - *Phonegap CLI* `cordova add plugin cordova-plugin-whitelist`
  - *Phonegap CLI* `cordova add plugin cordova-plugin-whitelist@1.1.0`
  - *Phonegap Build* `<gap:plugin name=cordova-plugin-whitelist source=npm>`
  - *Phonegap Build* `<gap:plugin name=cordova-plugin-whitelist version=1.0.1 source=npm>`
3. white-list
  - `<allow-navigation (...) />`
  - Controls which URLs the WebView itself can be navigated to. Applies to top-level navigations only.
  - `<allow-intent (...) />`
  - Controls which URLs the app is allowed to ask the system to open. By default, no external URLs are allowed.
  - `<access origin=(...) />`
  - Controls which network requests (images, XHRs, etc) are allowed to be made (via cordova native hooks).
  - **DANGEROUS, BUT WORKING**
  - `<allow-navigation href="*" />`
  - `<allow-intent href="*" />`
  - `<access origin="*" />`
4. CSP (in the webpage)
  - Filters at the webpage level
  - `<meta http-equiv="Content-Security-Policy" content=(...") />`
  - Controls which network requests (images, XHRs, etc) are allowed to be made (via web view directly).
  - [Raymond Camden](http://www.raymondcamden.com/2015/05/25/important-information-about-cordova-5, dated May of 2015), posted some relevant information on this

    > I began to check on this and look at the different permutations.

    > If you do not include the plugin and do not include the CSP, you have no access to anything.

    > If you do not include the plugin and do include the CSP, you have no access to anything.

    > If you include the plugin and a CSP, you have access to what CSP gives you access to.

    > If you include the plugin and do not include a CSP, your access falls back to the access tag in config.xml, which is probably * (i.e. everything allowed).

  - some of the stuff appears as "Voodoo", like `gap:`
  - [Simon Mac Donald](http://www.google.com/url?q=http%3A%2F%2Fhi.im%2Fsimonmacdonald&sa=D&sntz=1&usg=AFQjCNEfbJmJ0IyPjk2hlk8PEZ5oZM8WNQ) [Adds](https://groups.google.com/d/msg/phonegap/DrYOdMrTssM/votSwdBvCwAJ)
    > The `gap:` is used as a protocol like `http:` for the iOS side to communicate from JS to native. Basically when Cordova iOS sees `gap:` it intercepts the request and uses it to do the bridging of the two layers. At least that is my understanding of it but it's been awhile since I dove into that area.

  - **DANGEROUS, BUT WORKING**
  - `<meta http-equiv="Content-Security-Policy" content="default-src *; style-src 'self' 'unsafe-inline'; script-src 'self' 'unsafe-inline' 'unsafe-eval'">`
  - Additional keywords and what they mean [CSP from Mozilla](https://developer.mozilla.org/en-US/docs/Web/Security/CSP/CSP_policy_directives#Keywords) 
  - Wait KIDS! There is a whole [website that support CSP](http://content-security-policy.com/)

### What you should watch for ###

1. web view
  - each platform has it's own library, as should be expected
  - each has it's own bugs, we need to be proactive
  - we draw clear barrier between web view and the internet 
2. inappbrowser
  - does NOT have access to the hardware on the mobile device
  - The InAppBrowser is not subject to the whitelist, nor is opening links in the system browser.
  - *conflicting* when using the `target` = `_self`: Opens in the Cordova WebView if the URL is in the white list, otherwise it opens in the InAppBrowser.
  - it is affect by `white-list` sometimes, but mostly by `CSP`
3. openwindow()
  - this can be a major security issues, use it carefully

### Samples ###

[DN: I may put a sample set of tags in here if I can work out what is happening. Rob]

### Ionic Issues ###

https://groups.google.com/forum/#!topic/phonegap/W8zAKXowrJk

###Security bugs###

-[draft](security-issues.md)
- Android, iOS, Window

###Unannounced changes###

- *Need add stories to these*, **maybe**
- *Phonegap Build* changes the default compiler from *2.7.0* to *cli-5.2.0* the last week of Sept.
- *Cordova* moves the *plugin respository* on the week of Oct 5.

###Documentation Issues###
- The white-list Guides are incomplete and have errors.
- Documentation contradicts itself
- It is hard to find versions for things
  - [Cordova/PhoneGap Version Confusion](http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/) - Outdated, does not reflect new system with dashes
  - Online NPM version are not up to date.
  - Here is an example. [npm](https://www.npmjs.com/package/cordova-plugin-whitelist) undated, says 1.0.0; [blog](http://cordova.apache.org/news/2015/06/22/plugins-release.html) - June 22, 2015, says 1.1.0
  - Note: the author is the same for both


