<!-- loio656e825c5f1548e6b1d0acb5586f2a2a -->

| loio |
| -----|
| 656e825c5f1548e6b1d0acb5586f2a2a |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/656e825c5f1548e6b1d0acb5586f2a2a) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/656e825c5f1548e6b1d0acb5586f2a2a)</div>

## Screen Reader Support for OpenUI5 Controls

OpenUI5 offers screen reader support in order to aid people with visual impairments. The implementation is based on the ARIA and HTML standards.

***

### General Information

Currently, the following libraries have screen reader support based on the ARIA standard:

-   sap.f

-   sap.m

-   sap.tnt

-   sap.ui.commons

-   sap.ui.core

-   sap.ui.generic

-   sap.ui.layout

-   sap.ui.suite

-   sap.ui.table

-   sap.ui.unified

-   sap.ui.ux3

-   sap.uxap


OpenUI5 controls provide the prerequisites for screen reader support based on the ARIA and HTML standards. All screen readers that implement this standard should work fine. If there are deviations in the interpretation, these need to be addressed to the screen reader vendor. If you need more information on our testing environment, see SAP Note [2564165](https://launchpad.support.sap.com/#/notes/2564165).

> ### Note:  
> -   No screen reader activation settings are necessary since the accessibility mode in OpenUI5 is switched on by default.
> 
> -   With version 1.78 of OpenUI5, we have prevented the automatic insertion of role `application` on the body of the OpenUI5 applications. After the change, a mode-based screen reader will start operating in reading mode as its default mode. For more information, please refer to SAP Note [2925884](https://launchpad.support.sap.com/#/notes/2925884).

