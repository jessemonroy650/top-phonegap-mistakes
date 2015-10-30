## Cordova/Phonegap the whitelist system ##

MOVED the original to [whitelist-system.md](whitelist-system.md)

Originally I wanted to do this as one blog post, but as the issues grew and the complexity increased, it appeared the best strategey is to have several pages.

Note: from here forward I will use Cordova to mean *Cordova CLI*, *Phonegap CLI*, and *Phonegap Build*. If there is a difference I will try to make it abundantly clear.

### Here is the breakdown. ###

For the whitelist system used with *Cordova*, there is actually four (4) unrelated systems in place. 

1. [legacy-whitelist plugin](https://www.npmjs.com/package/cordova-plugin-legacy-whitelist) (avoid)
2. [whitelist plugin](https://www.npmjs.com/package/cordova-plugin-whitelist) (Cordova's)
3. [W3's CSP](http://www.w3.org/TR/CSP2/) (Content Security Policy Level 2)
4. [Apple's ATS](https://web.archive.org/web/20150905111538/https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/) (App Transport Security)

- *legacy-whitelist plugin* was the previous `whitelist` system. It is provide for backwards compatibilty only.
- *whitelist plugin* is the new `whitelist` system. It is required as of *Cordova Tools 4.0.0*. It has three (3) parts.
- *W3's CSP* is a whitelist system that is implemented page by page. It is required as of *Cordova Tools 5.0.0*. It has sixteen (16) parts.
- ***Apple's ATS*** is a whitelist system exclusive to iOS. It required as of *iOS9*. It is implement in the `Info.plist`




### Annoyances in creating this document ###
- It is NOT helpful that the Cordova Website continues to change and move pages.
- It is NOT helpful that Apple's removes important documents. Like [this one](https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/index.html#//apple_ref/doc/uid/TP40016240) that is widely referenced. Guess what Apple, there is [this thing called archive.org](https://web.archive.org/web/20150905111538/https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/)
- It is NOT helpful that both Google and Apple proclaim that the world must use HTTPS to talk to them. Thank you Homeland f#ck US
- It is NOT helpful that the press [contribes issue](http://recode.net/2015/08/27/google-tells-developers-how-to-get-around-apples-new-security-rules-so-they-can-keep-selling-ads/) between Google and Apple.





