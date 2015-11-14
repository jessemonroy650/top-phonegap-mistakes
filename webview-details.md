## WebView Details ##
Date: 2015-10-25

Some of these things are for merging with [webview](webview.md)

## iOS ##

Technical Q&A QA1630: Using UIWebView to display select document types
Using UIWebView to display select document types
https://developer.apple.com/library/ios/qa/qa1630/_index.html#//apple_ref/doc/uid/DTS40008749

*iPhone OS 2.2.1 supports the following document types:*

- Excel (.xls)
- Keynote (.key.zip)
- Numbers (.numbers.zip)
- Pages (.pages.zip)
- PDF (.pdf)
- Powerpoint (.ppt)
- Word (.doc

*iPhone OS 3.0 supports these additional document types:*

- Rich Text Format (.rtf)
- Rich Text Format Directory (.rtfd.zip)
- Keynote '09 (.key)
- Numbers '09 (.numbers)
- Pages '09 (.pages)

Developing Web Content for Safari
https://developer.apple.com/library/ios/documentation/AppleApplications/Reference/SafariWebContent/Introduction/Introduction.html#//apple_ref/doc/uid/TP40002051

Creating Compatible Web Content
https://developer.apple.com/library/ios/documentation/AppleApplications/Reference/SafariWebContent/CreatingContentforSafarioniPhone/CreatingContentforSafarioniPhone.html#//apple_ref/doc/uid/TP40006482-SW1

*Use Security Features*

- SSL 2, SSL 3, and TLS with many popular cipher suites
- RSA keys up to 4096
- HTTPS
- **Not available** on iOS is Diffie-Hellman protocol, DSA keys, and self-signed certificates.

*Use Supported iOS Rich Media MIME Types*
**NEED make table for**

*Don?t Use Unsupported iOS Technologies*
**NEED make table for**


### security content of iOS 9.1 ###

https://support.apple.com/en-us/HT205370
- **Accelerate Framework**
- CVE-2015-5940 : Apple
- **CFNetwork**
- CVE-2015-7023 : (et, al.)
- **CoreGraphics**
- CVE-2015-5925 : Apple
- CVE-2015-5926 : Apple
- **OpenGL**
- CVE-2015-5924 : Apple
- **WebKit**
- CVE-2015-5928 : Apple
- CVE-2015-5929 : Apple
- CVE-2015-5930 : Apple
- CVE-2015-6981
- CVE-2015-6982
- CVE-2015-7002 : Apple
- CVE-2015-7005 : Apple
- CVE-2015-7012 : Apple
- CVE-2015-7014

## Android ##
WebView android
_Class Overview_

Zoom cupcake
Mediaquery -webkit-device-pixel-ratio Eclair

In order to support inline HTML5 video in your application you need to have hardware acceleration turned on.

WebChromeClient (+stuff) to support Full Screen (things)

WRAP_CONTENT is legacy parameter.

_Cookie and Window Management_

The standard behavior for an Activity is to be destroyed and recreated, when the device orientation or any other configuration changes. This will cause the WebView to reload the current page. If you don't want that, you can set your Activity to handle the orientation and keyboardHidden changes, and then just leave the WebView alone. It'll automatically re-orient itself as appropriate. Read Handling Runtime Changes for more information about how to handle configuration changes during runtime.

_(...) support different screen densities_

 Starting with API level ECLAIR, WebView supports DOM, CSS, and meta tag features to help you (as a web developer) target screens with different screen densities.

_Summary_
_Constants_
"geo:0,0?q="
"mailto:"
"tel:"
_Public Constructors_
_Public Methods_