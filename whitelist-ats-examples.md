## ATS Examples ##
Date: 2015-10-28

**EXAMPLES COMING. DESCRIPTIONS WILL BE ADDED**


####<a name=bydefault>Access By Default</a>####

####<a name=references>References</a>####

####<a name=usefularticles>Useful Articles</a>####

Cordova 5.3.1 and iOS9 platform - I can't load images and scripts form external sources
http://stackoverflow.com/a/33422392/3255670

Plugin as a solution

    `cordova plugin add cordova-plugin-disable-nsapptransportsecurity`

    https://www.npmjs.com/package/cordova-plugin-disable-nsapptransportsecurity

----

https://medium.com/five-minute-watchkit/how-to-disable-app-transport-security-2c8d5d298160#.aj55jn4us

```
<key>NSAppTransportSecurity</key>
    <dict>
    <key>NSAllowsArbitraryLoads</key>
    <true/>
    </dict>
```