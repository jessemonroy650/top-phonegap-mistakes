## White-list Matrix ##
Date: 2015-10-26


### First Decision Table ###

| Your Version of Cordova/Phonegap | support | notes |
|----------------------------------|---------|-------|
| 2.x | Not support | deprecated |
| 3.x | Available   |  - |
| 4.x | Required    | white-list, plugin |
| 5.x<sup>¥</sup> | Required    | white-list, plugin, CSP |
| 5.x<sup>¥</sup> | Required    | white-list, plugin, CSP |
| and iOS9 | Required | Apple's ATS<sup>£</sup> |

¥ = This include cli-5.1.0 and cli.5.2.0
£ = ATS requires &ndash; if you are using Apples SSL, the server you connect to [run TLSv1.2](http://ste.vn/2015/06/10/configuring-app-transport-security-ios-9-osx-10-11/)