# HOW TO apply the Cordova/Phonegap the whitelist system #
Date: 2015-10-28<br>
Last Update: 2015-11-09

***If you have any questions, I am usually in the [Google Group for Phonegap](https://groups.google.com/forum/#!forum/phonegap)**

This blog post is one page. It has three (3) parts.

1. *The Breakdown.* - the four big parts of the `whitelist` system
2. *Turning It All Off.* - turn off security, get the job done.
3. *Lucy, Esplain Youself.* - 5+ pages with references, examples, and  tips

As such, I want to thank *Rob Willett* for his invaluable assitance and advice. If you find errors, they are mine. If you have praise, send some luv to Rob.

*Note:* From here forward I will use **Cordova** to mean *Cordova CLI*, *Phonegap CLI*, and *Phonegap Build*. If there is a difference, I will try to make it abundantly clear. If you did not know there is a difference, [read this](https://github.com/jessemonroy650/top-phonegap-mistakes/blob/master/new-to-Phonegap.md)

##The breakdown.##

For the whitelist system used with *Cordova*, there is actually four (4) unrelated systems in place. 

1. [legacy-whitelist plugin](https://www.npmjs.com/package/cordova-plugin-legacy-whitelist) (avoid) was the previous `whitelist` system. It is provided for backwards compatibilty only.
2. [whitelist plugin](https://www.npmjs.com/package/cordova-plugin-whitelist) (Cordova's) is the new `whitelist` system. It is required as of *Cordova Tools 4.0.0*. It has three (3) parts.
3. [W3's CSP](http://www.w3.org/TR/CSP2/) (Content Security Policy Level 2) is a whitelist system that is implemented webpage by webpage. It is required as of *Cordova Tools 5.0.0*. It has sixteen (16) parts.
4. [Apple's ATS](https://web.archive.org/web/20150905111538/https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/) (App Transport Security)  is a whitelist system exclusive to iOS. It required as of *iOS9*. It is implemented in the `Info.plist`

To walk throught the various different systems would be tedious. As such, there are at least five (5) documents that directly support this blog. However, let's cut to the chase.

<p>As such,*the code that follows* ***turns off ALL whitelist systems***. *This means your app is not secured against attacks. It is up to <u>you</u> to secure your App.* Below that, you can ***turn on and apply ALL the whitelist system***, complete with detailed *explanations, directions, examples, and tips*.

##Turning It All Off##

**before 4.0.0**
- **Recommended: For development only.**
- The easiest way to *turn it all off* is to develop with a version before 4.0.0.
- For *Phonegap Build* ONLY use: `<preference name="phonegap-version" value="3.7.0" />` 
- For *Cordova/Phonegap CLI* See the outdated, but useful: [Cordova/PhoneGap  Version Confusion](http://devgirl.org/2014/11/07/cordovaphonegap-version-confusion/) 
- **After following these directions, you should now have full access and be completely insecure.**


**after 4.0.0**
- **Recommended: For production applications.**
- Start by adding the [`whitelist`](https://www.npmjs.com/package/cordova-plugin-whitelist) plugin. **required**
-  - *Phonegap Build* Only `<gap:plugin name=cordova-plugin-whitelist source=npm>`
-  - *Phonegap CLI* `cordova add plugin cordova-plugin-whitelist`
- Then to disable the `whitelist` system, add to `config.xml`
- **DANGEROUS, BUT WORKING**
```
    <allow-navigation href="*" />
    <allow-intent href="*" />
    <access origin="*" />
```

- To disable the `CSP` system, add this to every webpages that needs internet or network access, inline code ([Javascript](http://www.quirksmode.org/js/events_early.html) 
or [style](http://matthewjamestaylor.com/blog/adding-css-to-html-with-link-embed-inline-and-import)), or `eval()`.
- **DANGEROUS, BUT WORKING**
```
    <meta http-equiv="Content-Security-Policy" 
              content="default-src *; 
                       style-src 'self' 'unsafe-inline' 'unsafe-eval'; 
                       script-src 'self' 'unsafe-inline' 'unsafe-eval';">
```

- To disable Apple's `ATS` for iOS9, add to the `Info.plist`.
- **CAUTION:** Your app maybe rejected, unless you have a good reason for using this. [SEE](whitelist-ats-examples.md#appRejected). Alternatives [available](whitelist-ats-examples.md).
```
    <key>NSAppTransportSecurity</key>
         <dict>
         <key>NSAllowsArbitraryLoads</key>
         <true/>
         </dict>
```
###You should now have full access, and be completely insecure.###

- [ATS Examples](whitelist-ats-examples.md)

----

## Lucy, Esplain Youself ##

No security system is straight forward. Security systems tend to be compromises of caution and the real world. Jim Dennis, reminds me that, *"Security is a matter of policy. As an administrator (or developer), it is your job to enfore policy, not define security."*

The Cordova `whitelist` system is about how best to apply your real-world policies over a hybrid application. As such, sacrifices and compromises are every where. The link below is a document that walks through much of the Cordova `whitelist` system.

[new-whitelist-system.md](new-whitelist-system.md) &ndash; NOT FINISHED, in rough state. About 75% done.

### Deciding What You Need ###

Often I think someone at Microsoft designed this, but then I realize that the entire thing was the product of multiple committes, working indepently, with no real design criteria &ndash; then, this all makes sense.

As there are three (3) seperate systems and they do not talk about each other, it is difficult to decide how they relate to each other. The matrix on the next page is a series of questions and decision tables that help make you make choices. This matrix is infact an expert system. It will not write your code, but it will tell you what you need to write, and what you do not need to write.

[whitelist-matrix.md](whitelist-matrix.md) &ndash; NOT FINISHED, in rough state. About 85% done.

### Examples ###

Examples for each part. If you have any you'd like to lend, please email me or create an issue.

[whitelist-examples.md](whitelist-examples.md) &ndash; NOT FINISHED, in raw state. About 10% done.

[whitelist-csp-examples.md](whitelist-csp-examples.md) &ndash; NOT FINISHED, in rough state. About 60% done.

[whitelist-ats-examples.md](whitelist-ats-examples.md) &ndash; ALMOST FINISHED, in good state. About 90% done. Need more examples, some comments.


***If you have any questions, I am usually in the [Google Group for Phonegap](https://groups.google.com/forum/#!forum/phonegap)**


### <a name=annoyances>Annoyances in creating this document</a> ###

Before any of this was implemented, all the members of the various teams shared the same [fever dream](https://answers.yahoo.com/question/index?qid=20080201212121AA2xedD). As a result, today we have the various systems to deal with.

- It is NOT helpful that the Cordova Website continues to change and move pages.
- It is NOT helpful that the Cordova team is weak in communications. (Please remember they all volunteer for this, and help is needed.)
- It is NOT helpful that Apple's removes important documents. Like [this one](https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/index.html#//apple_ref/doc/uid/TP40016240) that is widely referenced. Guess what Apple, there is [this thing called archive.org](https://web.archive.org/web/20150905111538/https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/)
- It is NOT helpful that both Google and Apple proclaim that the world must use HTTPS to talk to them. Thank you Homeland f#ck US
- It is NOT helpful that the press [contrives issue](http://recode.net/2015/08/27/google-tells-developers-how-to-get-around-apples-new-security-rules-so-they-can-keep-selling-ads/) between Google and Apple.


