## Cordova/Phonegap the whitelist system ##

MOVED the original to [whitelist-system.md](whitelist-system.md)

Originally, I wanted to do this as a one blog post, but as the issues grew and the complexity increased, it appeared the best strategey is to have several pages.

Note: From here forward I will use **Cordova** to mean *Cordova CLI*, *Phonegap CLI*, and *Phonegap Build*. If there is a difference, I will try to make it abundantly clear. If you did not know there is a difference, [read this](https://github.com/jessemonroy650/top-phonegap-mistakes/blob/master/new-to-Phonegap.md)

### Here is the breakdown. ###

For the whitelist system used with *Cordova*, there is actually four (4) unrelated systems in place. 

1. [legacy-whitelist plugin](https://www.npmjs.com/package/cordova-plugin-legacy-whitelist) (avoid) was the previous `whitelist` system. It is provided for backwards compatibilty only.
2. [whitelist plugin](https://www.npmjs.com/package/cordova-plugin-whitelist) (Cordova's) is the new `whitelist` system. It is required as of *Cordova Tools 4.0.0*. It has three (3) parts.
3. [W3's CSP](http://www.w3.org/TR/CSP2/) (Content Security Policy Level 2) is a whitelist system that is implemented webpage by webpage. It is required as of *Cordova Tools 5.0.0*. It has sixteen (16) parts.
4. [Apple's ATS](https://web.archive.org/web/20150905111538/https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/) (App Transport Security)  is a whitelist system exclusive to iOS. It required as of *iOS9*. It is implemented in the `Info.plist`

To walk throught the various pieces of the different systems would be tedious. Not that that does not need to be done. However, let's cut to the chase and get back to the original goal &ndash; "a one blog post."<p>As such,*the code that follows* ***turns off ALL the whitelist systems***. *This means your app is not secured against attacks. It is up to you to secure your App.* If you don't, then you probably don't know that the [Night of the Living Dead](https://en.wikipedia.org/wiki/Living_Dead) has three parts.

After the answers below, below that are links to more details explanations and examples.

### Turning It All Off ###

- Add to `config.xml`
- **DANGEROUS, BUT WORKING**
```
    <allow-navigation href="*" />
    <allow-intent href="*" />
    <access origin="*" />
```

- Add to every webpages that need internet or network access
- **DANGEROUS, BUT WORKING**
```
    <meta http-equiv="Content-Security-Policy" 
              content="default-src *; 
                       style-src 'self' 'unsafe-inline' 'unsafe-eval'; 
                       script-src 'self' 'unsafe-inline' 'unsafe-eval';">
```

- Add to the `Info.plist`
- **DANGEROUS, BUT WORKING**
```
    <key>NSAppTransportSecurity</key>
         <dict>
         <key>NSAllowsArbitraryLoads</key>
         <true/>
         </dict>
```

## Lucy, Esplain Youself ##

This sentence to be expanded to describe the link.
[whitelist-system.md](new-whitelist-system.md)

### Deciding What You Need ###

Often I think someone at Microsoft designed this, but then I realize that the entire things was the product of multiple committes working indepently - with no real design criteria, it all makes sense.

The matrix in the next page is a series of decision tables that will walk you through to making the correct choices. It is infact a expert system. It will not write your code, but it will tell you what you need to write, and what you do not need to write.

[whitelist-matrix.md](whitelist-matrix.md) &ndash; NOT FINISHED, in rough state. About 80% done.

### Examples ###

Examples for each part. If you have any you'd like to lend, please email me or create an issue.

[whitelist-examples.md](whitelist-examples.md) &ndash; NOT STARTED, not even close.

[whitelist-csp-examples.md](whitelist-csp-examples.md) &ndash; NOT FINISHED, in rough state. About 40% done.

[whitelist-ats-examples.md](whitelist-ats-examples.md) &ndash; JUST STARTED, in raw state. About 10% done.

<a name=annoyances>
### Annoyances in creating this document ###
</a>

Before any of this was implemented, all the members of the various team shared the same [fever dream](https://answers.yahoo.com/question/index?qid=20080201212121AA2xedD). As a result, today we have the various systems to deal with.

The resulting blog post and reference pages is a two-plus (2+) week effort. There were a <a href=#annoyances>number of annoyance</a> that extened the process.

- It is NOT helpful that the Cordova Website continues to change and move pages.
- It is NOT helpful that the Cordova team is weak in communications. (Please remember they all volunteer for this, and help is needed.)
- It is NOT helpful that Apple's removes important documents. Like [this one](https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/index.html#//apple_ref/doc/uid/TP40016240) that is widely referenced. Guess what Apple, there is [this thing called archive.org](https://web.archive.org/web/20150905111538/https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/)
- It is NOT helpful that both Google and Apple proclaim that the world must use HTTPS to talk to them. Thank you Homeland f#ck US
- It is NOT helpful that the press [contrives issue](http://recode.net/2015/08/27/google-tells-developers-how-to-get-around-apples-new-security-rules-so-they-can-keep-selling-ads/) between Google and Apple.





