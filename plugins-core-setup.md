# Core Plugins Setup#
Date: 2015-11-18<br>
Last Update: 2015-11-25

**NOTE:** - 2015-11-24 - A [recent update to Phonegap Build](http://phonegap.com/blog/2015/11/19/config_xml_changes_part_two) required a change, which makes this more universal. Meaning it's good for CLI.

ADDED: 2015-11-24 - [still more changes coming](http://community.phonegap.com/nitobi/topics/correct-syntax-for-pulling-plugin-from-github-via-npm#reply_16351151)<br>
NOTE - 2015-11-26 - [`<plugin />` defaults to npm and `<gap:plugin />` (not recommended) defaults to pgb](http://community.phonegap.com/nitobi/topics/failed-to-build-android#reply_16369060)<br>
NOTE - 2015-11-28 - [The Latest plugin version are not applied, even though the were release on](https://cordova.apache.org/news/2015/11/24/plugins-release.html) Nov 24, 2015<br>

**Phonegap Build**

- http://docs.build.phonegap.com/en_US/configuring_plugins.md.html#Plugins
- http://docs.build.phonegap.com/en_US/configuring_plugins.md.html#plugin-params

**Cordova/Phonegap**

- [Cordova/PhoneGap Version Confusion](http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/) dated but useful

**Where to get the names and version**

- If you are using *Cordova/Phonegap CLI or SDK*, the latest plugins, as released by Cordova, are usable. 
- If you are using *Cordova/Phonegap Build*, you may have to use one version before the latest version. (There is a rule for this.)

You can always find the latest plugins list on the [Cordova Blog](https://cordova.apache.org/blog/) and look for *Plugins Release*.

**To version or not to version.**

- **Set** the version, your code will always work. Then, make the changes at your pace, not those of the Cordova "core" team.
- **Do not set** the version, get the latest and greatest. However, as versions change so does the chance for you code to break.

**Versions set**
```
<plugin name="cordova-plugin-battery-status" source="npm" spec="1.1.0" />
<plugin name="cordova-plugin-camera"         source="npm" spec="1.2.0" />
<plugin name="cordova-plugin-console"        source="npm" spec="1.0.1" />
<plugin name="cordova-plugin-contacts"       source="npm" spec="1.1.0" />
<plugin name="cordova-plugin-device"         source="npm" spec="1.0.1" />
<plugin name="cordova-plugin-device-motion"  source="npm" spec="1.1.1" />
<plugin name="cordova-plugin-device-orientation" source="npm" spec="1.0.1" />
<plugin name="cordova-plugin-dialogs"        source="npm" spec="1.1.1" />
<plugin name="cordova-plugin-file"           source="npm" spec="2.1.0" />
<plugin name="cordova-plugin-file-transfer" source="npm" spec="1.2.0" />
<plugin name="cordova-plugin-geolocation"    source="npm" spec="1.0.1" />
<plugin name="cordova-plugin-globalization"  source="npm" spec="1.0.1" />
<plugin name="cordova-plugin-inappbrowser"   source="npm" spec="1.0.1" />
<plugin name="cordova-plugin-legacy-whitelist" source="npm" spec="1.1.0" />
<plugin name="cordova-plugin-media"          source="npm" spec="1.0.1" />
<plugin name="cordova-plugin-media-capture"  source="npm" spec="1.0.1" />
<plugin name="cordova-plugin-network-information" source="npm" spec="1.0.1" />
<plugin name="cordova-plugin-splashscreen"   source="npm" spec="2.1.0" />
<plugin name="cordova-plugin-statusbar"      source="npm" spec="1.0.0" />
<plugin name="cordova-plugin-test-framework" source="npm" spec="1.0.1" />
<plugin name="cordova-plugin-vibration"      source="npm" spec="1.2.0" />
<plugin name="cordova-plugin-whitelist"      source="npm" spec="1.1.0" />
```

**NO Versions set**
```
<plugin name="cordova-plugin-battery-status" source="npm" />
<plugin name="cordova-plugin-camera"         source="npm" />
<plugin name="cordova-plugin-console"        source="npm" />
<plugin name="cordova-plugin-contacts"       source="npm" />
<plugin name="cordova-plugin-device"         source="npm" />
<plugin name="cordova-plugin-device-motion"  source="npm" />
<plugin name="cordova-plugin-device-orientation" source="npm" />
<plugin name="cordova-plugin-dialogs"        source="npm" />
<plugin name="cordova-plugin-file"           source="npm" />
<plugin name="cordova-plugin-file-transfer" source="npm" />
<plugin name="cordova-plugin-geolocation"    source="npm" />
<plugin name="cordova-plugin-globalization"  source="npm" />
<plugin name="cordova-plugin-inappbrowser"   source="npm" />
<plugin name="cordova-plugin-legacy-whitelist" source="npm" /> <!-- NEW -->
<plugin name="cordova-plugin-media"          source="npm" />
<plugin name="cordova-plugin-media-capture"  source="npm" />
<plugin name="cordova-plugin-network-information" source="npm" />
<plugin name="cordova-plugin-splashscreen"   source="npm" />
<plugin name="cordova-plugin-statusbar"      source="npm" /> <!-- NEW -->
<plugin name="cordova-plugin-test-framework" source="npm" /> <!-- NEW -->
<plugin name="cordova-plugin-vibration"      source="npm" />
<plugin name="cordova-plugin-whitelist"      source="npm" /> <!-- NEW -->
```

Source: https://cordova.apache.org/news/2015/06/22/plugins-release.html<br>
NOT APPLIED YET: https://cordova.apache.org/news/2015/11/24/plugins-release.html<br>

### Related Articles ###

- [Checking for platform and plugin updates in your Cordova project](http://www.raymondcamden.com/2015/11/04/checking-for-platform-and-plugin-updates-in-your-cordova-project) - November 4, 2015
- [PhoneGap Developer's Guide to the iOS Status Bar](http://devgirl.org/2014/07/31/phonegap-developers-guid/) - July 31, 2014



