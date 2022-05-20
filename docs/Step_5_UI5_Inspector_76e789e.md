<!-- loio76e789ea418a48a1a27916b63a30fb72 -->

| loio |
| -----|
| 76e789ea418a48a1a27916b63a30fb72 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/76e789ea418a48a1a27916b63a30fb72) | [demo kit latest release](https://sdk.openui5.org/topic/76e789ea418a48a1a27916b63a30fb72)</div>

## Step 5: UI5 Inspector

In this tutorial step, we will have a closer look at UI5 Inspector - a plug-in specifically created for analyzing and debugging OpenUI5 code.

With UI Inspector, you can find answers to the following questions, for example:

-   What is the structure of your app?

-   How are the elements related to each other?

-   Which controls are involved when a function is performed?

-   Which data is bound to a specific control and how \(model and path\)?


> ### Note:  
> UI5 Inspector is only available for the Google Chrome browser.

***

<a name="loio76e789ea418a48a1a27916b63a30fb72__section_z4x_bdk_b1b"/>

### Preview

 ![](images/loioe881330405e24b42b064ae6042d85b43_LowRes.gif) 

***

### Opening the Example App and the UI5 Inspector

1.  Download UI5 Inspector from the [Chrome Web Store](https://chrome.google.com/webstore/detail/ui5-inspector/bebecogbafbighhaildooiibipcnbngo?hl=en) and add it to your Chrome browser as a standard extension .

2.  Download the example app with errors from the Demo Kitat [Troubleshooting](https://sdk.openui5.org/entity/sap.ui.core.tutorial.troubleshooting/sample/sap.ui.core.tutorial.troubleshooting.01) and run the app.

3.  Open the *Developer Tools* in Google Chrome by pressing [F12\].

4.  Choose the *UI5* tab on the right side of the developer tools panel.

5.  Choose *Control Inspector*.

    You now see a list of all of the controls that are used in the current view of the app. When you select an entry, you see the properties and their values in the *Properties* area on the right. You can analyze line by line without being overwhelmed by too much information.


***

<a name="loio76e789ea418a48a1a27916b63a30fb72__section_plg_ffk_b1b"/>

### Simulating UI Changes

The app contains a *Do Something* button with meaningless icon \(`sap-icon://action`\) and text. We want to use the `sap-icon://activate` icon instead and change the text. With UI Inspector, we want to simulate how that will effect the UI change.

1.  Right-click the *Do Something* button and from the context menu select *Inspect UI5 Control*.

    The corresponding line in the *Control Inspector* is highlighted and you can view its properties.

2.  Double-click the value for the `icon` property, which is currently `sap-icon://action`.

3.  Replace `action` with `activate` and confirm with [Enter\].

    The icon on the button in the app is updated to show the new icon ![Activate](images/loio997baba218974ca2888824f87d8b1af4_LowRes.png).

4.  Double-click the value for the `text` property and change the value to `Activate`.

5.  The changes that you make in the UI5 Inspector are only temporary, and the icon will be reset to the default when the page is reloaded. To make your change permanent, you have to change the app code.


**Parent topic:** [Troubleshooting](Troubleshooting_5661952.md "In this tutorial, we will show you some tools that will help you if you run into problems with your OpenUI5 app.")

**Next:** [Step 4: Diagnostics Window](Step_4_Diagnostics_Window_04b75ea.md "In this tutorial step, we have a closer look at the Diagnostics window. It offers a wealth of information including comprehensive technical information, a control tree, and debugging features.")

**Previous:** [First-Aid Kit](First_Aid_Kit_38859a8.md "This section contains the most common issues that you might face when developing OpenUI5 apps and how to solve them.")

**Related Information**  


[UI5 Inspector](UI5_Inspector_b24e724.md "The UI5 Inspector is an open source Chrome DevTools extension that helps app developers to inspect, analyze, and support OpenUI5-based apps. It is supported for apps based on OpenUI5 version 1.28 and higher.")

