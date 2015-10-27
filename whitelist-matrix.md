## White-list Matrix ##
Date: 2015-10-26


### First Decision Table ###

| Your Version of *Cordova/Phonegap Tools* <sup>¢</sup> | support | notes |
|----------------------------------|---------|-------|
| 2.x | Not support | deprecated |
| 3.x | Available   |  - |
| 4.x | Required    | white-list, plugin |
| 5.x<sup>¥</sup> | Required    | white-list, plugin, CSP |
| 5.x<sup>¥</sup> | Required    | white-list, plugin, CSP |
| Any above &amp; iOS9<sup>§</sup> | Required | Apple's ATS<sup>£</sup> |

- ¢ = Cordova and Phonegap versions do NOT align, but are close. This version is not the \*pinned* version, learn if yo do not know.
- ¥ = This include cli-5.1.0 and cli.5.2.0
- £ = ATS requires &ndash; if you are using Apple's SSL, the server you connect to [run TLSv1.2](http://ste.vn/2015/06/10/configuring-app-transport-security-ios-9-osx-10-11/)
- § = iOS9 is officially not supported until *Cordova iOS 4.0.0* is released