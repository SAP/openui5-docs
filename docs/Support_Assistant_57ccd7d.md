<!-- loio57ccd7d7103640e3a187ed55e1d2c163 -->

| loio |
| -----|
| 57ccd7d7103640e3a187ed55e1d2c163 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/57ccd7d7103640e3a187ed55e1d2c163) | [demo kit latest release](https://sdk.openui5.org/topic/57ccd7d7103640e3a187ed55e1d2c163)</div>

## Support Assistant

The Support Assistant enables developers to check whether their apps are built according to the OpenUI5 best practices and guidelines.

***

### Goals

The tool aims to reduce maintenance and consulting times and to streamline OpenUI5 app development. It uses a set of predefined rules to check all aspects of an application, for example, accessibility, performance, data binding, usability. With a simple click, you can check the current state of your app. After execution, you can analyze the results and apply corrective measures based on the outcome.

Check out the Support Assistant highlights video for an overview of its main functionalities:

  

***

### Getting Started

The Support Assistant can be started using a URL or a Technical Information Dialog.

***

#### From a URL Parameter

The Support Assistant is enabled with the following URL parameter: `sap-ui-support=true`. The tool then appears as a toolbar in the footer of the app.

> ### Tip:  
> If you want to run the Support Assistant in a separate window, use the parameter `sap-ui-support=true,window` 

   
  
<a name="loio57ccd7d7103640e3a187ed55e1d2c163__fig_c11_3j1_k1b"/>Support Assistant Toolbar

 ![](images/loioc9ec61c44d7d45caba4fb3b31a094557_HiRes.png "Support Assistant Toolbar ") 

***

#### From the Technical Information Dialog

You can also start the Support Assistant from the Technical Information Dialog.

1.  Open the Technical Information Dialog by using the following [shortcut](Keyboard_Shortcuts_for_OpenUI5_Tools_154844c.md):  [Ctrl\] + [Shift\] + [Alt\] / [Option\] + [P\]  

2.  Choose *Activate Support Assistant*.


Starting the Support Assistant from here allows you to run it with a different OpenUI5 version. You can find more details on this topic in [Running the Support Assistant on an Older OpenUI5 Version](Running_the_Support_Assistant_on_an_Older_OpenUI5_Version_473201b.md).

Selecting *Rules* will show you the available rulesets. You can then select your rules and start the analysis of the app.

***

<a name="loio57ccd7d7103640e3a187ed55e1d2c163__section_zxz_jh3_rz"/>

### Persisting Rules and Settings

All scopes and temporary rules can be stored in the local storage of your browser. This will allow you to continue with your work even after you have closed the browser window. To enable this feature, choose *Settings* \(![](images/loio24b9cee6f45340778480ea25e80bf0e5_HiRes.png)\) on the banner and select the checkbox *I agree to use local storage persistency for*.

> ### Tip:  
> You can delete your already persisted data by choosing *Delete Persisted Data*.

***

### Features

-   To learn more about rules and rule management see: [Rules Management](Rules_Management_3fc864a.md)

-   To learn more about result processing and reporting see: [Results and Analysis](Results_and_Analysis_f09fab1.md)

-   To learn more about creating your own rules see: [Rule Development Guide](Rule_Development_Guide_cd356da.md)


-   **[Using the Support Assistant](Using_the_Support_Assistant_12572ab.md "The user interface of the Support Assistant allows you to view the available rules and
		load additional rulesets for an active application. You can also run an analysis and view
		the issues identified. The results are available in the form of a consolidated report,
		generated as an HTML document.")**  
The user interface of the Support Assistant allows you to view the available rules and load additional rulesets for an active application. You can also run an analysis and view the issues identified. The results are available in the form of a consolidated report, generated as an HTML document.
-   **[Rule Development Guide](Rule_Development_Guide_cd356da.md "The Support Assistant allows you to create custom rules and rulesets and test them on
		your apps.")**  
The Support Assistant allows you to create custom rules and rulesets and test them on your apps.

**Related Information**  


[Step 3: Support Assistant](Step_3_Support_Assistant_35f08e1.md "In this tutorial step, we will have a closer look at Support Assistant. You can use this tool to check whether your app is built according to the best practices with predefined rules.")

