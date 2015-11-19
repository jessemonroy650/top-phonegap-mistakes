## This is to clarify ##
Last update: 2015-11-06
Date: 2015-11-06


Currently, among developers new to *Cordova/Phonegap* there is a great deal of confusion with regards to three configuration elements.

1. `<preference>`
2. `<feature>`
3. `<platform>`

There are three factors that contribute to this. 

1. The documentation has issues.
-- It's old.
-- It's out of date.
-- It has errors.
-- It has not kept up with changes.
-- On *Phonecap Build*, You can override the setting with [config-file](http://phonegap.com/blog/2014/01/30/customizing-your-android-manifest-and-ios-property-list-on-phonegap-build/)

2. Developers new to *Cordova* are unaware that there are 5 different system.
- Cordova CLI
- Cordova SDK
- Phonegap CLI
- Phonegap SDK
- Phonegap Build

3. Example Code in the field is woofully out of sync with what is currently happening.

Even if we put that all aside and just look at the documentation, it is a challenge.

| element        | Notes |
|----------------|-------|
| `<preference>` | See below |
| `<feature>`    | If you work directly in an SDK and are using the platform-specific `config.xml` file as source, you use the `<feature>` tag to enable device-level APIs and external plugins. Otherwise this is not used for *Cordova/Phonegap CLI* or *Phonegap Build*. |
| `<platform>`   | Used with *Cordova/Phonegap CLI* to set the `<preference>` and `<icon>` for a particular platform. |

So far not too bad. 

However, `<preference>` is the worst of the pack

There is only one preference that, in theory, works across all platforms, and that is `fullscreen`.

https://issues.apache.org/jira/browse/CB-8635?jql=project%20%3D%20CB%20AND%20resolution%20%3D%20Unresolved%20AND%20text%20~%20%22fullscreen%22%20ORDER%20BY%20priority%20DESC


----

Sources:
- Cordova CLI [The config.xml File](http://cordova.apache.org/docs/en/5.4.0/config_ref/index.html)
- Phonegap Build [Configuring - Preferences](http://docs.build.phonegap.com/en_US/configuring_preferences.md.html#Preferences)
- [iOS Configuration](http://cordova.apache.org/docs/en/5.1.1/guide/platforms/ios/config.html)
- [Android Configuration](http://cordova.apache.org/docs/en/5.1.1/guide/platforms/android/config.html)
- [BlackBerry 10 Configuration](http://cordova.apache.org/docs/en/5.1.1/guide/platforms/blackberry10/config.html)

| element        | Notes |
|----------------|-------|
| `<preference>` | See below |
| `<feature>`    | If you work directly in an SDK and are using the platform-specific `config.xml` file as source, you use the `<feature>` tag to enable device-level APIs and external plugins. Otherwise this is not used for *Cordova/Phonegap CLI* or *Phonegap Build*. |
| `<platform>`   | Used with *Cordova/Phonegap CLI* to set the `<preference>` for a particular platform.<br>It is also supposed to work with icons and splash screens |


### `<preference>` ##

**According to Cordova CLI [The config.xml File](http://cordova.apache.org/docs/en/5.4.0/config_ref/index.html)**

**global**

| preference | platforms |PGB|
|------------|-----------|---|
| fullscreen |   all     | Y |

**Multi-Platform**

| preference                   |PGB| platforms                | Note |
|------------------------------|---|--------------------------|------|
| DisallowOverscroll           | - | Android and iOS          | - |
| BackgroundColor              | - | Android and BlackBerry   | CSS overrides all platforms |
| HideKeyboardFormAccessoryBar | - | iOS and BlackBerry       | - |
| Orientation                  | Y | Android, iOS, WP8, Amazon Fire OS and Firefox OS. | can use with `<platform>` |

**According to [iOS Configuration](http://cordova.apache.org/docs/en/5.1.1/guide/platforms/ios/config.html)**

| preference                        |  Marked MP | Should MP | Note |
|-----------------------------------|------------|-----------|------|
| EnableViewportScale               |     No     |     No    | - | 
| MediaPlaybackRequiresUserAction   |     No     |     No    | - |
| AllowInlineMediaPlayback          |     No     |     No    | - |
| BackupWebStorage                  |     No     |     No    | - |
| TopActivityIndicator              |     No     |     No    | - |
| KeyboardDisplayRequiresUserAction |     No     |     No    | - |
| SuppressesIncrementalRendering    |     No     |     No    | - |
| GapBetweenPages                   |     No     |     No    | - |
| PageLength                        |     No     |     No    | - |
| PaginationBreakingMode            |     No     |     No    | - |
| PaginationMode                    |     No     |     No    | - |
| UIWebViewDecelerationSpeed        |     No     |     No    | - |
| ErrorUrl                          |     No     |     Yes   | Android has. |
| OverrideUserAgent                 |     No     |     Yes   | Android has. |
| AppendUserAgent                   |     No     |     Yes   | Android has. |

**According to [Android Configuration](http://cordova.apache.org/docs/en/5.1.1/guide/platforms/android/config.html)**

| preference                 | Marked MP | Should MP | Note |
|----------------------------|-----------|-----------|------|
| KeepRunning                |     No    |     No    | A similar property on other platforms requires modifying the "configuration-manifest" file. |
| LoadUrlTimeoutValue        |     No    |     No    | - |
| SplashScreen               |     No    |     No    | better control with [cordova-plugin-splashscreen](https://www.npmjs.com/package/cordova-plugin-splashscreen) |
| SplashScreenDelay          |     No    |     No    | better control with [cordova-plugin-splashscreen](https://www.npmjs.com/package/cordova-plugin-splashscreen) |
| InAppBrowserStorageEnabled |     No    |     No    | Assumes [inAppBrowser](https://www.npmjs.com/package/cordova-plugin-inappbrowser) is loaded. |
| LoadingDialog              |     No    |     No    | Dialog box when loading page. |
| LoadingPageDialog          |     No    |     No    | Dialog box when loading page. |
| ErrorUrl                   |     No    |    Yes    | iOS has. |
| ShowTitle                  |     No    |     No    | - |
| LogLevel                   |     No    |     No    | - |
| <s>SetFullscreen</s>       |    (Yes)  |     No    | Deprecated, Use the global 'Fullscreen' |
| AndroidLaunchMode          |     No    |     No    | - |
| DefaultVolumeStream        |     No    |     No    | added in cordova-android 3.7.0, controls vector to hardware |
| OverrideUserAgent          |     No    |    Yes    | iOS has. |
| AppendUserAgent            |     No    |    Yes    | iOS has. |

**[BlackBerry 10 Configuration](http://cordova.apache.org/docs/en/5.1.1/guide/platforms/blackberry10/config.html)**

| preference    | Marked MP | Should MP | Note |
|---------------|-----------|-----------|------|
| ChildBrowser  |     No    |     No    | - |
| PopupBlocker  |     No    |     No    | - |
| WebSecurity   |     No    |    Yes    | - |


### According to PGB (Phonegap Build) ###

| preference                    | platforms | Note |
|-------------------------------|-----------|------|
| phonegap-version              |    All    | This is only for Phonegap Build |
| orientation                   |    All    | - |
| fullscreen                    |    All    | - |
| target-device                 |    iOS    | - |
| prerendered-icon              |    iOS    | - |
| detect-data-types             |    iOS    | - |
| exit-on-suspend               |    iOS    | - |
| deployment-target             |    iOS    | tranlsates to the MinimumOSVersion in the ipa Propertly List. |
| android-minSdkVersion         |  Android  | - |
| android-maxSdkVersion         |  Android  | - |
| android-targetSdkVersion      |  Android  | - |
| android-installLocation       |  Android  | - |
| android-windowSoftInputMode   |  Android  | - |
| android-build-tool            |  Android  | - |
| <s>splash-screen-duration</s> |  Android  | Deprecated, use [SplashScreenDelay](http://docs.phonegap.com/en/3.6.0/guide_platforms_android_config.md.html) or the [cordova-plugin-splashscreen](https://www.npmjs.com/package/cordova-plugin-splashscreen)


###Better alternatives to some preferences###

Plugin: [cordova-plugin-splashscreen](https://www.npmjs.com/package/cordova-plugin-splashscreen)
This has the issue that sometimes you need to use `<platform>`, but not for *Phonegap Build*.

*Phonegap Build* uses `<gap:platform (...)` to decide which platforms to build. It has NO `<platform>`.


It has only two methods:

1. `splashscreen.show()`
2. `splashscreen.hide()`


| preference                  | platforms | Note |
|-----------------------------|-----------|------|
| SplashScreen                | Android, Browser
| SplashScreenDelay           | Android, Browser
| SplashMaintainAspectRatio   | Android
| FadeSplashScreen            | iOS
| FadeSplashScreenDuration    | iOS
| ShowSplashScreenSpinner     | iOS
| SplashScreenBackgroundColor | Browser
| ShowSplashScreen            | Browser
| SplashScreenWidth           | Browser
| SplashScreenHeight          | Browser


####Unapplied Notes####


http://community.phonegap.com/nitobi/topics/phonegap_build_now_supports_all_phonegap_preferences
