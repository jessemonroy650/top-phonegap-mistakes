## Cordova Browser Platform ##
Last Update: 2015-10-10

In theory you can develop on your browser with this, and fine tune on your mobile device. However, in practice this is one of the worst documented elements of the Cordova system. This is evidence by by it's omittance from the *[Cordova Platform Guide](http://cordova.apache.org/docs/en/latest/guide/platforms/index.html)*, and the lack of any pertinent information in the [github README.md](https://github.com/apache/cordova-browser).

### Releases ###

There are only two (2) release for *Browser platform*, 4.0.0 and 3.6.0.

#### 4.0.0 ####

- [Tools Release: September 9th, 2015](https://cordova.apache.org/news/2015/09/09/tools-release.html)

    - [Cordova Browser ~4.0.0](https://github.com/apache/cordova-browser/blob/master/RELEASENOTES.md#400-aug-13-2015)
    - pinned browser@~4.0.0, windows@~4.1.0, blackberry10@~3.8.0, webos@~3.7.0 (cordova-lib)
    - [CB-9549](https://issues.apache.org/jira/browse/CB-9549) Removes excess JS files from browserified app
    - [CB-9505](https://issues.apache.org/jira/browse/CB-9505) Correct plugin modules loading within browserify flow. This closes #126 (cordova-js)

#### 3.6.0 ####

- [Apache Cordova CLI 4.0 Release](https://cordova.apache.org/announcements/2014/10/16/cordova-4.html) - 16 Oct 2014

> We have also released Cordova-Browser 3.6.0, (...) - Initial support for Cordova-Browser platform. (...)

> **New Platform: Cordova Browser**

> We have just released Browser as a platform. Add it to your projects with cordova platform add browser. This feature is intended for development purposes. We are working on adding browser support to our core plugins. Ray Camden has put together detailed blog post outlining which plugins we currently support at

> **What's new in Cordova-Browser**

>    - Update JS snapshot to version 3.6.0
>    - added initial Windows run support
>    - No longer need to kill Chrome for macOS
>    - added create.bat for Windows support


### Articles ###

* *Quick tip for Cordova and the Browser platform ? Setting a custom port* -  October 22, 2015
* http://www.raymondcamden.com/2015/10/22/quick-tip-for-cordova-and-the-browser-platform

* *Browser as a platform for your PhoneGap/Cordova apps* - September 24, 2014
* http://www.raymondcamden.com/2014/9/24/Browser-as-a-platform-for-your-PhoneGapCordova-apps

> Working with a limited number of plugins as of 
 - Camera
 - Device
 - Device Motion (Accelerometer)
 - Device Orientation (Compass)
 - Network Information

### Mention of *browser platform* Blog by Blog ###
other than pinned 

- [Plugins Release](https://cordova.apache.org/news/2015/11/24/plugins-release.html) - 24 Nov 2015
    - [CB-9426](https://issues.apache.org/jira/browse/CB-9426) Fix exception when using device motion plugin on browser platform.
    - [CB-9426](https://issues.apache.org/jira/browse/CB-9426) Fix exception when using device orientation plugin on browser platform
    - override resolveLocalFileSystemURL by webkitResolveLocalFileSystemURL for browser platform add .project into git ignore list
    - [CB-9167](https://issues.apache.org/jira/browse/CB-9167) Fix crash on browser window close 
    - [CB-7965](https://issues.apache.org/jira/browse/CB-7965) Add cordova-plugin-statusbar support for browser platform
    - Fixed browser platform to pass tests and combined tests (plugin:vibration - no issue number)
    - Removed call to add proxy and renamed browser file (plugin:vibration - no issue number)
    - [CB-7966](https://issues.apache.org/jira/browse/CB-7966) Add cordova-plugin-vibration support for browser platform

- [Tools Release: November 6th, 2015](https://cordova.apache.org/news/2015/11/06/tools-release.html) - 06 Nov 2015
    - [CB-9587](https://issues.apache.org/jira/browse/CB-9587) Check if browser platform added properly before creating parser.
    - [CB-9604](https://issues.apache.org/jira/browse/CB-9604) Fix error adding browser platform with PlatformApi polyfill.

- [Tools Release: August 13th, 2015](https://cordova.apache.org/news/2015/08/13/tools-release.html)
    - Browserify flag for adding plugins at build time vs run time has all tests passings. Please try it out via --browserify. EX. cordova run android --browserify.
    - [CB-9420](https://issues.apache.org/jira/browse/CB-9420) Fixes malformed require calls in browserify bundle. This closes #270
    - [CB-9429](https://issues.apache.org/jira/browse/CB-9429) Enables jsdom/browser tests for browserify.
    - Fixed issues with data transforms when using browserify (cordova-js)
    - [CB-7953](https://issues.apache.org/jira/browse/CB-7953) Add cordova-plugin-battery-status support for browser platform

- [Tools Release: June 10, 2015](https://cordova.apache.org/news/2015/06/10/tools-release.html)
    - [CB-8441](https://issues.apache.org/jira/browse/CB-8441) cordova prepare --browserify now supports 3rd party plugins to build your cordova.js at run time! Try it out!
    - [CB-8965](https://issues.apache.org/jira/browse/CB-8965) copy platform specific js into platform_www when adding new platforms for browserify workflow
    - [CB-6865](https://issues.apache.org/jira/browse/CB-6865) added browserify support for plugins with any id (cordova-js)
    - updated browserify dependency to 10.1.3 (cordova-js)

- [Tools Release: April 21, 2015](https://cordova.apache.org/news/2015/04/21/tools-release.html)
    - [CB-8223](https://issues.apache.org/jira/browse/CB-8223) Adds configparser module for exposing config.xml in the Browser platform (cordova-js)

- [Plugins Release and Moving plugins to npm: April 21, 2015](https://cordova.apache.org/announcements/2015/04/21/plugins-release-and-move-to-npm.html)
    - [CB-7964](https://issues.apache.org/jira/browse/CB-7964) browser Add support (splashscreen)
    - [CB-7956](https://issues.apache.org/jira/browse/CB-7956) Browser Add support (file)
    - [CB-7957](https://issues.apache.org/jira/browse/CB-7957) Browser Add support (file-transfer)
    - [CB-8683](https://issues.apache.org/jira/browse/CB-8683) Updated tizen and Browser specific references of old id to new id (globalization)
    - [CB-7960](https://issues.apache.org/jira/browse/CB-7960) Browser Add support (globalization)
    - [CB-7961](https://issues.apache.org/jira/browse/CB-7961) Browser Add support (inappbrowser)
    - [CB-8432](https://issues.apache.org/jira/browse/CB-8432) Correct styles for Browser wrapper to display it correctly on some pages (inappbrowser)
    - [CB-8683](https://issues.apache.org/jira/browse/CB-8683) Updated WP and Browser specific references of old id to new id (inappbrowser)
    - [CB-7962](https://issues.apache.org/jira/browse/CB-7962) Adds Browser platform support (media)
    - [CB-7963](https://issues.apache.org/jira/browse/CB-7963) Browser Add support (media-capture)
    - [CB-8185](https://issues.apache.org/jira/browse/CB-8185) Use navigator.onLine as connection information source on Browser platform (network-information)
    - [CB-7964](https://issues.apache.org/jira/browse/CB-7964) browser Add support (splashscreen)

- [Tools Release: March 02, 2015](https://cordova.apache.org/news/2015/03/02/tools-release.html)
    - [CB-8472](https://issues.apache.org/jira/browse/CB-8472) Can't find config.xml error installing browser platform after plugin (cordova-lib)
    - [CB-8223](https://issues.apache.org/jira/browse/CB-8223) Expose config.xml in the Browser platform (cordova-lib)

- [Plugins Release: February 10, 2015](https://cordova.apache.org/news/2015/02/10/plugins-release.html)
    - browser: Fixed a bug that caused an "cannot call method of undefined" error if the browser's user agent wasn't recognized (plugin:device - no issue number)
    - [CB-7955](https://issues.apache.org/jira/browse/CB-7955) Add support "browser" platform (dialogs)

- [Tools Release: January 09, 2015](https://cordova.apache.org/news/2015/01/09/tools-release.html)
    - [CB-8158](https://issues.apache.org/jira/browse/CB-8158) Added hasModule check to browserify code (cordova-lib)
    - browserify: updated require to use symbollist (cordova-lib)

- [Plugins Release: December 9, 2014](https://cordova.apache.org/news/2014/12/09/plugins-release.html)
    - Browser Changing device.platform to always report the platform as "browser". (device - no issue number)

- [Apache Cordova CLI 4.0 Release](https://cordova.apache.org/announcements/2014/10/16/cordova-4.html)
    - computeCommitId for browserify workflow fixed to handle cli and non cli workflows (cordova-lib)
    - [CB-7219](https://issues.apache.org/jira/browse/CB-7219) prepare-browserify now supports commitId and platformVersion for cordovajs (cordova-lib)
    - Added tests for browser platform (cordova-lib)

- [Plugins Release: September 22, 2014](https://cordova.apache.org/news/2014/09/22/plugins-release.html)
    - Added plugin support for the browser (device)
    - Added support for the browser (device-motion)
    - Updated doc for browser (device-motion)
    - Add support for the browser (device-orientation)
    - Updated docs for browser (device-orientation)
    - Added support for the browser (network-information)
