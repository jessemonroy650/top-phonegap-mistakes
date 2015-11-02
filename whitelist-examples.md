## Phonegap Whitelist Examples ##
Date: 2015-10-28

**THERE ARE MORE EXAMPLES COMING. DESCRIPTIONS WILL BE ADDED**

###EXAMPLE 00###
- **DANGEROUS, BUT WORKING**

This goes in the **config.xml**.
```
    <allow-navigation href="*" />
    <allow-intent href="*" />
    <access origin="*" />
```
This goes in the **index.html**.
```
    <meta http-equiv="Content-Security-Policy" 
              content="default-src *; 
                       style-src 'self' 'unsafe-inline' 'unsafe-eval'; 
                       script-src 'self' 'unsafe-inline' 'unsafe-eval';">
```

###EXAMPLE 01###
This is a real world example from *Rob Willett*.

Here only access tags used. They are required by the whitelist plugin. This goes in the **config.xml**.
```
  <access origin="http://cdn.example.domain/*" />
  <access origin="https://cloud.example.domain:9000/*" />
  <access origin="https://capturegps.example.domain:9500/*" />
  <access origin="https://s3-eu-west-1.amazonaws.com/*" />
```


This goes in the <head> section of your **index.html**. Notice that for each access-origin tag in the config.xml file there is at least one entry in the CSP tag.
```
    <meta http-equiv="Content-Security-Policy"
          content="default-src 'self' 'unsafe-eval' gap:  https://s3-eu-west-1.amazonaws.com;
                   connect-src 'self' http://cdn.example.domain https://cloud.example.domain:9000 https://capturegps.example.domain:9500;
                   style-src 'self' 'unsafe-inline';">
```

The gap: flag is needed for when you have the CSP on iOS. The ?unsafe-inline? flags are due to using a JavaScript library that changes the DOM model.

###EXAMPLE 02###



----

####<a name=bydefault>Access By Default</a>####

| directive        | Controls         | `file:` | `http(s):` | iframe | Controls<br>other plugins |
|------------------|------------------|---------|------------|--------|---------------|
| allow-navigation | webview          |  Yes    |    No      |   No   |     No        |
| allow-intent     | `window.open()`  |  No     |    No      |   No   |  inappbrowser |
| access origin    | network (cordova)|  Yes    |    No<sup>¥</sup>      |   No   |     Yes       |

- ¥ = Cordova (CLI/SDK) Applications, by default, have this turn on. **NOT CONFIRMED**

####<a name=references>References</a>####

####<a name=usefularticles>Useful Articles</a>####
