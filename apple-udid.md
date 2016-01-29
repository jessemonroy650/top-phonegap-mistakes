## Apple UDID ##
Date: 2016-01-26<br>
Last Update: 2016-01-26


https://developer.apple.com/library/prerelease/ios/documentation/Foundation/Reference/NSUUID_Class/index.html

http://www.wikihow.com/Obtain-the-Identifier-Number-%28UDID%29-for-an-iPhone,-iPod-or-iPad

http://www.telerik.com/blogs/how-to-add-ios-devices-to-your-developer-profile

----

<a href=https://developer.apple.com/library/mac/documentation/IDEs/Conceptual/AppDistributionGuide/MaintainingProfiles/MaintainingProfiles.html>Maintaining Identifiers, Devices, and Profiles</a>

Scroll down to: 
<i>Locating Device IDs Using Xcode</i>
and
<i>Locating iOS Device IDs Using iTunes (iOS, tvOS)</i>

----

###APPs cannot access UDID March 21, 2013###

- *Apple Will No Longer Approve Apps Using Unique Device Identifier (UDID) Beginning May 1, Must Also Support iPhone 5 and Retina Display*
- http://www.macrumors.com/2013/03/21/apple-will-no-longer-approve-apps-using-unique-device-identifier-udid-beginning-may-1/

> Starting May 1, the App Store will no longer accept new apps or app updates that access UDIDs. Please update your apps and servers to associate users with the Vendor or Advertising identifiers introduced in iOS 6. You can find more details in the UIDevice Class Reference.

- *Apple iOS UDID Banned & Localytics' Commitment to Privacy*
- http://info.localytics.com/company-news/apple-ios-udid-banned

> The deprecation of UDID made it clear that Apple was looking to make it more difficult for mobile apps to backtrack to an individual. After the deprecation of UDID a couple mobile applications not only continued to use UDID but passed the value in the clear which was not taken well by Apple and many of those applications started to be rejected from the App Store. (sic)

- *Apple sets May 1 deadline for UDID, iPhone 5 app changes*
- http://www.macworld.com/article/2031573/apple-sets-may-1-deadline-for-udid-iphone-5-app-changes.html

> On Thursday, Apple informed iOS App developers that as of May 1, the App Store will stop accepting new apps or app updates that access a device's unique identifier or fail to support Retina devices and the iPhone 5. 


- *Privacy concerns as some Apple iPhone apps transmit UDIDs*
- http://www.macworld.com/article/1154595/iphone_udid.html

> Eric Smith, Assistant Director of Information Security and Networking at Bucknell University in Lewisburg, Pa., discovered 68 percent of the 57 top applications in the App Store sent out UDID information, back to a remote server, owned either by the application developer or an advertising partner.

----

###Phonegap Issue CB-49###

- *UUID replacement*
- https://issues.apache.org/jira/browse/CB-49
- Resolved: 23/Mar/12 22:26 

**References**

- *Apple Sneaks A Big Change Into iOS 5: Phasing Out Developer Access To The UDID*
- http://techcrunch.com/2011/08/19/apple-ios-5-phasing-out-udid/

> This is a big deal, especially for any mobile ad networks, game networks or any app which relies on the UDID to identify users. Many apps and mobile ad networks, for instance, uses the UDID or a hashed version to keep track of who their users are and what actions they have taken. App publishers are now supposed to create their own unique identifiers to keep track of users going forward, which means they may have to throw all of their historical user data out the window and start from scratch.

