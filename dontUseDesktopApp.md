**Canned Message**
I need to blog this, so i don't have to repeat this answer again and again.

You cannot use *Phonegap Desktop App* with *Phonegap Build*.

*Phonegap Desktop App* uses *Phonegap CLI*, so if you want to use *Phonegap Desktop App* you need to stay with *Phonegap CLI*.

If you want to use *Phonegap Build*, then forget what you have done and start over  **_OR_**  make [Minor modifications](https://github.com/jessemonroy650/tutorial-html5ui-hide-show/wiki) to move *Phonegap Desktop App* to *Phonegap Build*. To be clear, the difference is minor, but enough to keep tripping you. 

Also, you will not be able to use *Phonegap Developer App* as that is meant to work with *Phonegap Desktop App*. You cannot use either CLI or Build with *Developer App*.

FWIW: I've been trying to get Phonegap to fix this. Here is the [report on the issue.](https://github.com/phonegap/phonegap-docs/issues/137)

Let me know what you want to do. 

Jesse


http://community.phonegap.com/nitobi/topics/how-to-build-for-android-jelly-bean-and-windows-phone-version

<b>Canned Message</b>
I need to blog this, so i don't have to repeat this answer again and again.

You cannot use <i>Phonegap Desktop App</i> with <i>Phonegap Build</i>.

<i>Phonegap Desktop App</i> uses <i>Phonegap CLI</i>, so if you want to use <i>Phonegap Desktop App</i> you need to stay with <i>Phonegap CLI</i>.

If you want to use <i>Phonegap Build</i>, then forget what you have done and start over  <b>_OR_</b>  make <a href=https://github.com/jessemonroy650/tutorial-html5ui-hide-show/wiki>Minor modifications</a> to move <i>Phonegap Desktop App</i> to <i>Phonegap Build</i>. To be clear, the difference is minor, but enough to keep tripping you. 

Also, you will not be able to use <i>Phonegap Developer App</i> as that is meant to work with <i>Phonegap Desktop App</i>. You cannot use either CLI or Build with <i>Developer App</i>.

FWIW: I've been trying to get Phonegap to fix this. Here is the <a href=https://github.com/phonegap/phonegap-docs/issues/137>report on the issue.</a>

Let me know what you want to do. 

Jesse

http://community.phonegap.com/nitobi/topics/inappbrowser-not-to-agreeable-in-android#reply_16677820



- Documentation [Format of STEP 5 is confusing for persons with *English as a second language* #137 ](https://github.com/phonegap/phonegap-docs/issues/137)

- stackoverflow.com/questions/35579052/phonegap-navigator-notification-alert-does-not-work-on-ios



Okay. Sometimes the documentation for Phonegap suffers badly. The Desktop App is one case in point.

When you use <i>Getting Started with Phonegap</i>, the <a href=http://docs.phonegap.com/getting-started/5-going-further/>last step #5</a> reads:
<blockquote>
There are two choices available for building and packaging your applications:
</blockquote>

This means you can choose one or the other. 

Unfortunately, the directions fail at this point.

<b>The Fix</b>

If you are creating with <i>Phonegap Build</i>, you are better off NOT using the CLI (Command Line Interface). With  <i>Phonegap Build</i>, you are only required to have two (2) files - <code>index.html</code> and <code>config.xml</code>. In addition both files must sit in the same directory. 

The blog explains better:
<a href=http://codesnippets.altervista.org/blog/2015/BLOG.2015-06-10.jssnippets.html>An HTML Boilerplate for Phonegap</a>

Make sure you follow link to the <a href=https://github.com/jessemonroy650/Phonegap--Generic-Boilerplate>source code</a>.

Lastly, if you plan on using <i>Phonegap Build</i>, abandon the workflow you have been shown and read the <a href=http://docs.build.phonegap.com/en_US/#googtrans%28en%29>Phonegap Build Documentation<.a>.

I'm sure you have question. Let me know.
Jesse