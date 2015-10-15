## Cordova/Phonegap the white-list system ##

Can you spell disaster? 

- **FOREWARNED.** *This document is NOT all inclusive, nor does  it cover every exception. This blog entry is a road map to understanding. It is intended for professionals. If you are new to programming and mobile in particular, you will find this confusing and frustrating.* **FOREWARNED.**

[Multiple security bugs](security-issues.md) have perhaps influence this `white-list`. It is a result of this, or becuase of this, that the system was not completely documented. Add to that the back to back [unannounced changes](unannounced-changes.md) to the system, and I feel like I am catching a falling knife &ndash; without a handle!!

- security bugs
- unannounced changes
- Documentation Issues
- How it Works
- What you should watch for

###security bugs###

-[draft](security-issues.md)
- Android, iOS, Window

###unannounced changes###

- *Need add stories to these*, *maybe**
- *Phonegap Build* changes the default compiler from *2.7.0* to *cli-5.2.0* the last week of Sept.
- *Cordova* moves the *plugin respository* on the week of Oct 5.

###Documentation Issues###
- The white-list Guides are incomplete and have errors.
- Documentation contradicts itself
- It is hard to find versions for things
  - [Cordova/PhoneGap Version Confusion](http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/) - Outdated, does not reflect new system with dashes
  - NPM version are not up to date.
  - [Latest Plugin Release](http://cordova.apache.org/news/2015/06/22/plugins-release.html) - June 22, 2015

### How it Works ###

- *TO explain this clearly, I'm going to have to do a matix.*

1. white-list
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
2. CSP (in the webpage)
  - Filters at the webpage level
  - `<meta http-equiv="Content-Security-Policy" content=(...) />`
  - Controls which network requests (images, XHRs, etc) are allowed to be made (via webview directly).
  - **DANGEROUS, BUT WORKING**
  - `<meta http-equiv="Content-Security-Policy" content="default-src *; style-src 'self' 'unsafe-inline'; script-src 'self' 'unsafe-inline' 'unsafe-eval'">`
3. [plugin](https://www.npmjs.com/package/cordova-plugin-whitelist)
  - The one you want is `cordova-plugin-whitelist`
  - *Phonegap CLI* `cordova add plugin cordova-plugin-whitelist@1.0.1`
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
3. openwindow
  - this can be a major security issues, use it carefully





