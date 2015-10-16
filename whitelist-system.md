## Cordova/Phonegap the white-list system ##

Can you spell disaster? 

- **FOREWARNED.** *This document is NOT all inclusive, nor does  it cover every exception. This blog entry is a road map to understanding. It is intended for professionals. If you are new to programming and mobile in particular, you will find this confusing and frustrating.* **FOREWARNED.**

[Multiple security bugs](security-issues.md) have perhaps influence this `white-list`. It is a result of this, or becuase of this, that the `white-list` system was not completely documented. Add to that the back to back *unannounced changes* to the Cordova system, and I feel like I am catching a falling knife &ndash; without a handle!!

**What Reading is Below**

- security bugs
- unannounced changes
- Documentation Issues
- How it Works
- What you should watch for

###security bugs###

-[draft](security-issues.md)
- Android, iOS, Window

###unannounced changes###

- *Need add stories to these*, **maybe**
- *Phonegap Build* changes the default compiler from *2.7.0* to *cli-5.2.0* the last week of Sept.
- *Cordova* moves the *plugin respository* on the week of Oct 5.

###Documentation Issues###
- The white-list Guides are incomplete and have errors.
- Documentation contradicts itself
- It is hard to find versions for things
  - [Cordova/PhoneGap Version Confusion](http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/) - Outdated, does not reflect new system with dashes
  - Online NPM version are not up to date.
  - Here is an example. [npm](https://www.npmjs.com/package/cordova-plugin-whitelist) says 1.0.0 , [blog](http://cordova.apache.org/news/2015/06/22/plugins-release.html) - June 22, 2015) says 1.1.0
  - Note: the author is the same for both


### How it Works ###

- *TO explain this clearly, I'm going to have to do a matix.*

1. Version controls when you need to use it
  - Starting with Cordova 4.0.0 the white-list is required
  - After 5.0.0, there are additional rules which [Raymond Camden](http://www.raymondcamden.com/2015/05/25/important-information-about-cordova-5, dated May of 2015) alludes to
  - The alternative is this quick fix &ndash; but know that this *quick fix* removes all needs for `white-list`. This creates a [security issue](http://www.androidauthority.com/google-webview-security-582363/) which you may not want to by pass.
  - **QUICK FIX** Add this to your `config.xml` **for PHONEGAP BUILD ONLY** <br />
  - `<preference name="phonegap-version" value="3.7.0" />`
  - For *Cordova/Phonegap CLI* see [Cordova/PhoneGap Version Confusion](http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/) - Outdated, but useful
2. white-list
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
3. CSP (in the webpage)
  - Filters at the webpage level
  - `<meta http-equiv="Content-Security-Policy" content=(...) />`
  - Controls which network requests (images, XHRs, etc) are allowed to be made (via webview directly).
  - [Raymond Camden](http://www.raymondcamden.com/2015/05/25/important-information-about-cordova-5, dated May of 2015), posted some relevent information on this

    > I began to check on this and look at the different permutations.

    > If you do not include the plugin and do not include the CSP, you have no access to anything.

    > If you do not include the plugin and do include the CSP, you have no access to anything.

    > If you include the plugin and a CSP, you have access to what CSP gives you access to.

    > If you include the plugin and do not include a CSP, your access falls back to the access tag in config.xml, which is probably * (i.e. everything allowed).

  - **DANGEROUS, BUT WORKING**
  - `<meta http-equiv="Content-Security-Policy" content="default-src *; style-src 'self' 'unsafe-inline'; script-src 'self' 'unsafe-inline' 'unsafe-eval'">`
  - Additional keywords and what they mean [CSP from Mozilla](https://developer.mozilla.org/en-US/docs/Web/Security/CSP/CSP_policy_directives#Keywords) 

4. [plugin](https://www.npmjs.com/package/cordova-plugin-whitelist)
  - The one you want is `cordova-plugin-whitelist`
  - *Phonegap CLI* `cordova add plugin cordova-plugin-whitelist@1.1.0`
  - *Phonegap Build* `<gap:plugin name=cordova-plugin-whitelist version=1.0.1 source=npm>`

### What you should watch for ###

1. webview
  - each platform has it's own library, as should be expected
  - each has it's own bugs, we need to be proactive
  - we draw clear barrier between webview and the internet 
2. inappbrowser
  - does NOT have access to the hardware on the mobile device
  - The InAppBrowser is not subject to the whitelist, nor is opening links in the system browser.
  - *conflicting* when using the `target` = `_self`: Opens in the Cordova WebView if the URL is in the white list, otherwise it opens in the InAppBrowser.
  - ?it is affect by `white-list` sometimes, but mostly by `CSP`?
3. openwindow()
  - this can be a major security issues, use it carefully





