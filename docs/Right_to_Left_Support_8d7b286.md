<!-- loio8d7b2868b8d8441a803a3223754d72fc -->

| loio |
| -----|
| 8d7b2868b8d8441a803a3223754d72fc |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/8d7b2868b8d8441a803a3223754d72fc) | [demo kit latest release](https://sdk.openui5.org/topic/8d7b2868b8d8441a803a3223754d72fc)</div>

## Right-to-Left Support

OpenUI5 application developers need to be aware of how applications behave when right-to-left \(RTL\) directionality is selected. Changing the directionality has a big impact on text-displaying controls, images and the alignment of the whole application.

The default text direction is left-to-right \(LTR\). This can be changed to right-to-left mode \(RTL\) by using one of the following configuration switches:

-   URL parameter `sap-ui-rtl=true`

-   Configuration object: `window["sap-ui-config"].rtl = true;` 

-   Script tag configuration: `data-sap-ui-rtl="true"` 

-   Setting an RTL language as default language for the application.


OpenUI5 then sets the overall page direction to RTL. All OpenUI5 content is then displayed in RTL mode. Self-written controls and content has to be tested separately. If you require manual styles, provide a style specifically for the RTL case by using `html[dir=rtl]`.

-   **[API Properties for Right-to-Left Support in Text-Displaying Controls](API_Properties_for_Right_to_Left_Support_in_Text_Displaying_Controls_7e7cd0a.md "Languages with right-to-left (RTL) text directionality keep the default directionality
		of numeric values and texts in left-to-right (LTR) mode. To ensure correct handling, two API
		properties have been introduced - textDirection and
			textAlign.")**  
Languages with right-to-left \(RTL\) text directionality keep the default directionality of numeric values and texts in left-to-right \(LTR\) mode. To ensure correct handling, two API properties have been introduced - `textDirection` and `textAlign`.

