<!-- loio91f3df4a6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f3df4a6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/91f3df4a6f4d1014b6dd926db0e91070) | [demo kit latest release](https://sdk.openui5.org/topic/91f3df4a6f4d1014b6dd926db0e91070)</div>

## Third-Party Libraries

For the third party libraries shipped with OpenUI5, security-related issues have to be observed.

OpenUI5 ships with third-party libraries. jQuery is mandatory as OpenUI5 is based on it, and datajs is needed in case OData services should be used.

***

<a name="loio91f3df4a6f4d1014b6dd926db0e91070__section_FD6FE9D65C134965999FB56394A8BCAF"/>

### jQuery

jQuery does not have any security-related documentation on their site, but they are known to be aware of security and usually reacting quickly in case security issues are found within their library.

OpenUI5 includes jQuery together with their own libraries, so also has the possibility to add custom security fixes to jQuery, if necessary.

***

<a name="loio91f3df4a6f4d1014b6dd926db0e91070__section_7AA7F9054B57493C9612B142FBBF5404"/>

### datajs

datajs does not have any security-related documentation on their site.

OpenUI5 includes the datajs library and can add custom security fixes, if necessary.

***

<a name="loio91f3df4a6f4d1014b6dd926db0e91070__section_C7A8739DF3A140429D4B601B47145DF6"/>

### Libraries Included by the Application

Applications based on OpenUI5 are allowed from a technical point of view to include arbitrary custom libraries within their application. OpenUI5 can, of course, not give any statement about the security of third-party libraries and can not ensure security of third-party libraries. The application has full responsibility for doing a security assessment of third-party libraries before using them and for embedding and using them in a secure manner.

