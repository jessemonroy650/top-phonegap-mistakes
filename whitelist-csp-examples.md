## Whitelist CSP Examples ##
Date: 2015-10-28

<!-- Good default declaration:
    * gap: is required only on iOS (when using UIWebView) and is needed for JS->native communication
    * https://ssl.gstatic.com is required only on Android and is needed for TalkBack to function properly
    * Disables use of eval() and inline scripts in order to mitigate risk of XSS vulnerabilities. To change this:
        * Enable inline JS: add 'unsafe-inline' to default-src
        * Enable eval(): add 'unsafe-eval' to default-src
-->
<meta http-equiv="Content-Security-Policy" 
      content="default-src 'self' data: gap: https://ssl.gstatic.com; 
               style-src 'self' 'unsafe-inline'; 
               media-src *">

<!-- Enable all requests, inline styles, and eval() -->
<meta http-equiv="Content-Security-Policy" 
      content="default-src *; 
               style-src 'self' 'unsafe-inline'; 
               script-src 'self' 'unsafe-inline' 'unsafe-eval'">

<!-- My Extension, if any different -->
<meta http-equiv="Content-Security-Policy" 
      content="default-src *; 
               style-src 'self' 'unsafe-inline' 'unsafe-eval'; 
               script-src 'self' 'unsafe-inline' 'unsafe-eval';">

| directive   | usage |
|-------------|-------|
| base-uri    | unclear
| child-src   | used, if it contains value, otherwise 'default-src'
| connect-src | used, if it contains value, otherwise 'default-src'
| default-src | the follow directives use this directive as a fallback
child-src, connect-src, font-src, img-src, media-src, object-src, script-src, style-src 

| font-src    | used, if it contains value, otherwise 'default-src'
| form-action | used, if it contains value, "acts" as if *fatal error* and report violation
| frame-ancestors | used, if it contains value, otherwise value is treated as "*".
the follow HTML elements are affected by this directive
frame, iframe, object, embed or applet 

| frane-src   | is deprecated
| img-src     | used, if it contains value, otherwise 'default-src'
| media-src   | used, if it contains value, otherwise 'default-src'
| object-src  | used, if it contains value, otherwise 'default-src'
overlaps with 'frame-ancestors' and 'plugin-types'
| plugin-types | restricts plugins via MIME type
| report-uri  |
| sandbox     |
| source-src  | used, if it contains value, otherwise 'default-src'
'unsafe-inline' and 'unsafe-eval' are required to over-ride the default setting, regardless of 'default-src'

| style-src  | used, if it contains value, otherwise 'default-src'
'unsafe-inline' and 'unsafe-eval' are required to over-ride the default setting, regardless of 'default-src'



