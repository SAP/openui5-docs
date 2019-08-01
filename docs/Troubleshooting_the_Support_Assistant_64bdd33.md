<!-- loio64bdd33d236340908fe2659162492b39 -->

| loio |
| -----|
| 64bdd33d236340908fe2659162492b39 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/64bdd33d236340908fe2659162492b39) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/64bdd33d236340908fe2659162492b39)</div>

## Troubleshooting the Support Assistant

There are certain scenarios in which the Support Assistant does not behave as expected. In this section you can find tips on how to recognize and resolve some of these cases.

***

|Support Assistant Behavior|Root Cause|Solution|
|--------------------------|----------|--------|
|What does it mean when the following errors appear in the browser console? “Access to XMLHttpRequest at <URL\> from origin <ORIGIN\> has been blocked by the CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.”|This usually happens when serving OpenUI5 from a different origin. The Support Assistant tries to load support rule definitions from there, but cannot load them - a 404 response is sent by the origin server. The issue is usually caused by missing or misconfigured CORS headers on the 404 response specifically. Besides some support rules not being loaded, this should not affect normal operation of Support Assistant.| OpenUI5 library owners are encouraged to provide a `.supportrc` as specified by Support Assistant documentation to avoid causing 404 responses. For more information, see [Create a Ruleset for a Library](Create_a_Ruleset_for_a_Library_b5a5135.md) and [Content Security Policy](Content_Security_Policy_fe1a6db.md).|
|When you choose a custom location, you get an error message: 'The syntax of the location address is incorrect. The correct syntax is ... '.|URL doesn't match the protocol of the application.|If the application is HTTP, the location should also be HTTP. If it is HTTPS, the location should be HTTPS. Also, the URL should end in sap/ui/support/.|

