<!-- loio91f3d8706f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f3d8706f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f3d8706f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f3d8706f4d1014b6dd926db0e91070)</div>

## Securing Apps

The following section provides information about security aspects of OpenUI5. The information is intended for OpenUI5 application and control developers, as well as to system administrators running applications based on OpenUI5.

OpenUI5 is a client-side JavaScript library, so while the library itself is designed and tested to be secure, it cannot ensure the application to be secure. Unlike WebDynpro, where the application is built against an abstract programming model and the framework handles the HTML rendering, JavaScript code and communication with the browser, in OpenUI5 the application controls the HTML output and provides its own JavaScript code. This code is executed on the client and it handles client/server communication.

While this brings a lot of freedom and possibilities for the application, it comes with a lot of responsibility with regards to security. Application developers need to understand the security threats and actively prohibit exploitation. Also important is the correct configuration of the used HTTP server.

Moreover, common security mechanisms, which are usually taken for granted, like user authentication, session handling, authorization handling, or encryption are not part of OpenUI5 and need to be handled by the server-side framework and/or custom code of the application.

***

### Further Reading

OpenUI5 is not bound to any server implementation or server-side programming language and can, thus, be used with SAP NetWeaver AS for ABAP, Java, HANA XS Engine, or any standard web server. Therefore, the corresponding Security Guides also apply to OpenUI5.

> Note:
> We highly recommend that you implement SAP Note [1582870](https://launchpad.support.sap.com/#/notes/1582870) for ABAP XSS escaping support.
> 
> 

