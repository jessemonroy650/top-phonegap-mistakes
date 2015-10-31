## Phonegap Whitelist Examples ##
Date: 2015-10-28




**Access By Default**

| directive        | Controls         | `file:` | `http(s):` | iframe | Controls<br>other plugins |
|------------------|------------------|---------|------------|--------|---------------|
| allow-navigation | webview          |  Yes    |    No      |   No   |     No        |
| allow-intent     | `window.open()`  |  No     |    No      |   No   |  inappbrowser |
| access origin    | network (cordova)|  Yes    |    No<sup>¥</sup>      |   No   |     Yes       |

- ¥ = Cordova (CLI/SDK) Applications, by default, have this turn on. **NOT CONFIRMED**