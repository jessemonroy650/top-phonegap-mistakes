# What is a *Cordova/Phonegap Plugin*? #
Date: 2016-02-29<br>
Last Update: 2016-02-29

If you have worked in software development for a while, you are familiar the concept of "plugins". However, what exactly is in a plugin varies from software platform to platform.

In short, the ''Cordvoa/Phonegap Plugin'' is
- a library of system calls
- written in the native language 
- which has a "bridge" from the native language to Javascript
- and is stored in repositories for ease of use.

## The System Calls ##

The system calls can be any software of service on the device, such as:

- displaying a text messge in a window (like Toast)
- accessing the hardware (like the GPS)
- accessing a network (like the Internet)
- login into facebook (or Twitter)
- connecting to online adversting companies (like Urban Airship)
- access local databases (like indexedDB or SQLite)

## native language ##

- Java (android) 
- Objective C (iOS)
- C# (Windows)
- C/C++ (others)

## The Javascript bridge ##

In short, each platform (Android, iOS, Windows, etc) has code in the webview that can be call with Javascript. The code is then sent to the native "middle-man" which then calls the system with your request. The code is now filtered, but you should take reasonable precautions - like understanding the [whitelist system](https://github.com/jessemonroy650/top-phonegap-mistakes/blob/master/the-whitelist-system.md)

## The repositories ##

There are two sets of libraries to platform.

One set is refered to as the "core" plugins. These are written and maintained by the Cordova team. The other set is know as 3rd-party plugins. These are written by other people. The 3rd-party plugins are maintained and fixed by the authors - which also handle any questions regarding their plugins.

For *Phonegap Build*, a cloud-based build service by Adobe/Phonegap, these are the links to the respositories.

- ["Core" plugins](https://build.phonegap.com/plugins/core/)
- [3rd-party plugins](https://build.phonegap.com/plugins/)

For *Cordova/Phonegap CLI and SDK (including IDEs)*, these are the links to the respositories.

- ["Core" plugins](http://cordova.apache.org/docs/en/6.x/cordova/plugins/pluginapis.html)
- [3rd-party plugins](http://cordova.apache.org/plugins/)

## Documentation ##

- [PGB Documentation](http://docs.build.phonegap.com/en_US/configuring_plugins.md.html#Plugins)
- [Cordova Documentation](http://cordova.apache.org/docs/en/6.x/plugin_ref/plugman.html)
