## Whitelist Notes for iOS ##
Date: 2015-11-11<br>
Last Update: 2015-11-15T20:45:35 (Mountain Time, USA)

[`The Whitelist System`](the-whitelist-system.md) -> `Whitelist iOS Notes`

There are parts to the whitelist system

1. Cordova `whitelist` plugin
2. W3's `CSP`
3. Apple's `ATS`

| OS version | `whitelist` plugin         |            `CSP`                  | `ATS` |
|------------|----------------------------|------------------------------------|------|
| iOS8     | Does not apply<br>not needed | Applies via UIWebview or WKWebview |  No  |
| iOS9    | `<access>` only | Yes and requires duplicate entries in `<access>` |  Yes |


While the `whitelist` plugin is needed, two of the three elements are not used. `<allow-navigation ()>` and `<allow-intent (...)` are neither used nor enforced. This means you do not need to use these elements, they are effectively ignored.

- Pull Request: [Remove iOS whitelist](https://issues.apache.org/jira/browse/CB-9972)
- [Proposal to Remove the Cordova iOS Native Whitelist](https://github.com/shazron/cordova-discuss/blob/ios-remove-whitelist/proposals/ios-whitelist-removal.md)
- There was [*Consensus on the ML (Mailing List)*](https://github.com/cordova/cordova-discuss/pull/27#issuecomment-155261590) for the Proposal

###Additional Details###

By [shazron](https://github.com/cordova/cordova-discuss/pull/27#issuecomment-154114763):

> CSP applies to iOS 8 and below. Reminder c(ordova)-ios 4 only supports ios 8 and 9 now by consensus on the list.

> Yes, with the proposed change the access tag only applies for iOS 9 and above. The access tag will only apply for ATS which is only available on iOS 9 and above. 

By [csantanapr](https://github.com/cordova/cordova-discuss/pull/27#issuecomment-154134404):

> (..) if "access" tag is present in config.xml it's totally ignored for iOS8 and below, only applicable to iOS9 and higher.

[Paragraph #4](https://github.com/shazron/cordova-discuss/blob/ios-remove-whitelist/proposals/ios-whitelist-removal.md)

> In the last released version of the `cordova-cli`, all `<access>` tags are automatically converted to `ATS` directives in the app's `Info.plist` file. 
