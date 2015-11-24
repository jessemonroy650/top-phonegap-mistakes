# whitelist-access-examples #
Date: 2015-11-16
Last Update: 2015-11-16


http://www.w3.org/TR/widgets-access/

***Selected Sub-Sections***

2. Definitions

> To grant access means that the user agent authorizes widget execution scopes to retrieve one or more network resources via the user agent. 

    > Some schemes (e.g. mailto:) may be handled by third-party applications and are therefore not controlled by the access mechanism defined in this specification. Similarly, policies defined using this specification do not apply to opening content in external applications. 

> A network resource is a retrievable resource of any media type that is identified by a URI that has a DNS or IP as its authority component [URI]. 

    > This deliberately excludes some schemes (e.g. `sms:`, `tel:`) from being controlled by the means provided by this specification. 

5. Policy

> In the ***default policy***, a user agent must deny access to network resources external to the widget by default, whether this access is requested through APIs (e.g. `XMLHttpRequest`) or through markup (e.g. `iframe`, `script`, `img`). 

6. The `access` Element
6.1 Attributes

- origin - An IRI attribute that defines the specifics of the access request that is made. Only the scheme and authority components can be present in the IRI that this attribute contains ([URI], [RFC3987]). Additionally, an author can use the special value of U+002A ASTERISK (*). This special value provides a means for an author to request from the user agent unrestricted access to network resources. 
- subdomains - A boolean attribute that indicates whether or not the host component part of the access request applies to subdomains (as defined in [RFC1034]) of domain in the origin attribute. The default value when this attribute is absent is false, meaning that access to subdomains is not requested. 