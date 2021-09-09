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

-   **[ARIA Attribute Mapping](ARIA_Attribute_Mapping_3e9c010.md "Navigation with the keyboard and screen reader have to both work properly at the same
		time. In order for this to happen, you need to use the correct ARIA attributes and to map
		them to their HTML counterparts. ")**  
Navigation with the keyboard and screen reader have to both work properly at the same time. In order for this to happen, you need to use the correct ARIA attributes and to map them to their HTML counterparts.
-   **[Keyboard Usage of ARIA Role Mapped Controls](Keyboard_Usage_of_ARIA_Role_Mapped_Controls_e6cd547.md "Screen readers offer list features, that ease the app navigation, by grouping and
		extracting all elements with similar behaviors. This leads to additional requirements when
		creating OpenUI5 controls.
		Control developers need to make sure that their controls are marked with the correct ARIA
		role.")**  
Screen readers offer list features, that ease the app navigation, by grouping and extracting all elements with similar behaviors. This leads to additional requirements when creating OpenUI5 controls. Control developers need to make sure that their controls are marked with the correct ARIA role.
-   **[ARIA Mapping for Tooltips and Textual Alternatives](ARIA_Mapping_for_Tooltips_and_Textual_Alternatives_f9e14b3.md "Tooltips and semantic colors are important aspects in apps. They have to be interpreted
		correctly by the screen reader and require some special ARIA labeling. ")**  
Tooltips and semantic colors are important aspects in apps. They have to be interpreted correctly by the screen reader and require some special ARIA labeling.
-   **[ARIA Event Handling](ARIA_Event_Handling_79a9c51.md "When the UI of an application is changing or loading information, these state
		transitions and updates need to be passed on to the screen reader as well. You need to set
		the correct ARIA attributes (for example, aria-live or aria-busy) for the corresponding
		areas in your application. ")**  
When the UI of an application is changing or loading information, these state transitions and updates need to be passed on to the screen reader as well. You need to set the correct ARIA attributes \(for example, aria-live or aria-busy\) for the corresponding areas in your application.
-   **[ARIA Labeling](ARIA_Labeling_f38c21c.md "Proper labeling of all UI elements is needed in order to ensure the screen reader
		announces everything correctly. Here we describe the available options and how and when they
		should be used. ")**  
Proper labeling of all UI elements is needed in order to ensure the screen reader announces everything correctly. Here we describe the available options and how and when they should be used.
-   **[Best Practices for ARIA Labeling](Best_Practices_for_ARIA_Labeling_3169195.md "Sometimes the UI and the control usage may not allow standard ARIA labeling. Here we
		introduce some best practices on handling the labels in these cases. ")**  
Sometimes the UI and the control usage may not allow standard ARIA labeling. Here we introduce some best practices on handling the labels in these cases.

