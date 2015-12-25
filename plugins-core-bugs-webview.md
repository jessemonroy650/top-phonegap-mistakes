# Core Bugs For Webviews #
Date: 2015-12-24<br>
Last Update: 2015-12-24

- [Setup for Cordova "core" plugins](plugins-core-setup.md)
- [Repositories &amp; Bugs](bugs.md)
- [List of "core" plugins](http://cordova.apache.org/docs/en/5.4.0/cordova/plugins/pluginapis.html)

## Summary by Platforms ##

\# of bugs | platform name
-----------|------------
22 | [webview android](https://issues.apache.org/jira/browse/CB-9615?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20text%20~%20%22webview%20android%22%20ORDER%20BY%20priority%20DESC)
17 | [webview ios](https://issues.apache.org/jira/browse/CB-7958?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20text%20~%20%22webview%20ios%22%20ORDER%20BY%20priority%20DESC)
6  | [webview event](https://issues.apache.org/jira/browse/CB-7958?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20text%20~%20%22webview%20event%22%20ORDER%20BY%20priority%20DESC)
65 | Total [webview](https://issues.apache.org/jira/browse/CB-9914?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20text%20~%20webview%20ORDER%20BY%20priority%20DESC)

## Summary by Priority ##

\# of bugs | by priority
-----------|------------
0  | [webview priority:Blocker](https://issues.apache.org/jira/issues/?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20priority%20%3D%20Blocker%20AND%20text%20~%20%22webview%22%20ORDER%20BY%20priority%20DESC)
1  | [webview priority:Critical](https://issues.apache.org/jira/issues/?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20priority%20%3D%20Critical%20AND%20text%20~%20%22webview%22%20ORDER%20BY%20priority%20DESC)
46 | [webview priority:Major](https://issues.apache.org/jira/issues/?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20priority%20%3D%20Major%20AND%20text%20~%20%22webview%22%20ORDER%20BY%20priority%20DESC)
17 | [webview priority:Minor](https://issues.apache.org/jira/issues/?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20priority%20%3D%20Minor%20AND%20text%20~%20%22webview%22%20ORDER%20BY%20priority%20DESC)
0  | [webview priority:Trivial](https://issues.apache.org/jira/issues/?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20priority%20%3D%20Trivial%20AND%20text%20~%20%22webview%22%20ORDER%20BY%20priority%20DESC)

## Android Bugs ##

\# of bugs | Last Created | Earliest Created | platform, by priority - **Sorted by Created**
-----------|--------------|------------------|----------------------------------------------
0  | - | - | [webview android priority:Blocker](https://issues.apache.org/jira/issues/?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20priority%20%3D%20Blocker%20AND%20text%20~%20%22webview%20android%22%20ORDER%20BY%20created%20DESC%2C%20priority%20DESC)
1  | 04/Sep/15 | 04/Sep/15 | [webview android priority:Critical](https://issues.apache.org/jira/browse/CB-9615?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20priority%20%3D%20Critical%20AND%20text%20~%20%22webview%20android%22%20ORDER%20BY%20created%20DESC%2C%20priority%20DESC)
13 | 09/Dec/15 | 14/Nov/12 | [webview android priority:Major](https://issues.apache.org/jira/browse/CB-8736?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20priority%20%3D%20Major%20AND%20text%20~%20%22webview%20android%22%20ORDER%20BY%20created%20DESC%2C%20priority%20DESC)
8  | 19/Aug/15 | 06/Aug/13 | [webview android priority:Minor](https://issues.apache.org/jira/browse/CB-9516?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20priority%20%3D%20Minor%20AND%20text%20~%20%22webview%20android%22%20ORDER%20BY%20created%20DESC%2C%20priority%20DESC)
0  | - | - | [webview android priority:Trivial](https://issues.apache.org/jira/issues/?jql=project%20%3D%20CB%20AND%20issuetype%20%3D%20Bug%20AND%20status%20%3D%20Open%20AND%20priority%20%3D%20Trivial%20AND%20text%20~%20%22webview%20android%22%20ORDER%20BY%20created%20DESC%2C%20priority%20DESC)


### Android Webview Major Bugs ###

- [CB-10167](https://issues.apache.org/jira/browse/CB-10167) - not select multiple image from gallary using cordova
- [CB-9998](https://issues.apache.org/jira/browse/CB-9998) - CLONE - Data URIs do not work on Android
- [CB-9751](https://issues.apache.org/jira/browse/CB-9751) - Outdated documentation on embedding Android WebViews
- [CB-9503](https://issues.apache.org/jira/browse/CB-9503) - Adding a plugin with a caret version fails to resolve
- [CB-9393](https://issues.apache.org/jira/browse/CB-9393) - Embedded use case is undocumented for Cordova-Android 4.0.x
- [CB-9182](https://issues.apache.org/jira/browse/CB-9182) - WebResourceResponse is being deprecated, and needs to be updated
- [CB-8976](https://issues.apache.org/jira/browse/CB-8976) - platforms/android/build.gradle modifies android versionCode
- [CB-8736](https://issues.apache.org/jira/browse/CB-8736) - Android WebGL feature check returns incorrect result on some devices
- [CB-8080](https://issues.apache.org/jira/browse/CB-8080) - After migrating to 3.6.3 from 3.4.0, Appium (Android) tests fail because of open dialog
- [CB-6838](https://issues.apache.org/jira/browse/CB-6838) - Battery Plugin needs to be deprecated or fixed
- [CB-6665](https://issues.apache.org/jira/browse/CB-6665) - Can't access cookies in response/request headers for Android WebView
- [CB-5705](https://issues.apache.org/jira/browse/CB-5705) - Add after-install hook for plugman
- [CB-1847](https://issues.apache.org/jira/browse/CB-1847) - weinre: client c-2: weinre: invocation exception on WeinreClientEventsImpl.connectionCreated(): TypeError: Cannot call method 'indexOf' of undefined






