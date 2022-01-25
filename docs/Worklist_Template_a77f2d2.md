<!-- loioa77f2d29299247f8a3e30226507b1765 -->

| loio |
| -----|
| a77f2d29299247f8a3e30226507b1765 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a77f2d29299247f8a3e30226507b1765) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a77f2d29299247f8a3e30226507b1765)</div>

## Worklist Template

The **SAP Fiori Worklist Application** template implements a typical worklist floorplan, one of the patterns that is specified by the SAP Fiori design guidelines.

A worklist displays a collection of items to be processed by the user and usually involves reviewing details of a list item and taking action. If the data needs to be organized into columns or the overview of the items is more important than showing the item details directly, this template can be used as a starting point. For more information about worklist floorplans, see the  [SAP Fiori Design Guidelines](https://experience.sap.com/fiori-design-web/).

> ### Note:  
> You have two options: You can use this template to build an **app for the SAP Fiori launchpad \(FLP\)** or to build **standalone apps**.
> 
> -   If the app runs in FLP it also contains additional features like *Save as Tile* or *Share in SAP Jam* that depend on FLP at runtime. This app cannot be run standalone, meaning no `index.html` file is created but only files for testing the app in the FLP sandbox.
> 
> -   Only standalone apps contain an `index.html` file that is used to start the app.

   
  
<a name="loioa77f2d29299247f8a3e30226507b1765__fig_rgl_qbz_1t"/>Screenshot of the Worklist App

 ![](loio2c7e3b552825426d8840c83a6b0b029e_HiRes.png "Screenshot of the Worklist App") 

The *Worklist* view is the main view that is initially displayed in this app. When a user clicks or taps an item in the table, the *Object* view is displayed, showing more details for the selected item. We use the semantic `FullscreenPage` control as the page for both. A `SemanticPage` is an enhanced `sap.m.Page` that contains controls with a semantic meaning and displays them according to the SAP Fiori Design Guidelines, for example. For more details about semantic controls, see the [sample](https://openui5.hana.ondemand.com/#/entity/sap.m.semantic.SemanticPage) in the Demo Kit.

The table in the *Worklist* view displays a header area that shows the current amount of items in the worklist and a search field. The number of items are updated automatically and the search filters for a preconfigured column of the table.

> ### Note:  
> As the use cases for apps using a worklist pattern differ greatly, we only show a basic scenario in our template as a starting point for your individual development activities. For more information, see [How Do I Enhance the Template?](Worklist_Template_a77f2d2.md#loioa77f2d29299247f8a3e30226507b1765__section_EnhanceTemplate)

***

<a name="loioa77f2d29299247f8a3e30226507b1765__section_els_xvw_k1b"/>

### Where Can I Find the Worklist Template?

You can find the template in the following places:

-   **SAP Fiori Worklist Application** \(for OData V2 models\) and **SAP Fiori Worklist Application - OData V4** \(for OData V4 models\) templates in SAP Web IDE

    For more information about SAP Web IDE, see the documentation for SAP Web IDE on the SAP Help Portal at [https://help.sap.com/viewer/p/SAP\_Web\_IDE](https://help.sap.com/viewer/p/SAP_Web_IDE).

    > ### Caution:  
    > SAP Web IDE is no longer available via SAP Business Technology Platform trial accounts. Any references to SAP Web IDE in this documentation are only relevant for you if you have access to SAP Web IDE through a productive SAP BTP account. Please consider SAP Business Application Studio as an alternative. See [App Development Using SAP Business Application Studio](App_Development_Using_SAP_Business_Application_Studio_6bbad66.md).

-   **Worklist Template** under [Demo Apps](https://openui5.hana.ondemand.com/#demoapps.html).

-   `openui5-worklist-app` in the [SAP Repository on GitHub](https://github.com/SAP)

    For more information on how to clone or download the template from GitHub, refer to the template documentation on [GitHub](https://github.com/SAP/openui5-worklist-app/blob/master/README.md) .


***

### Tutorial

See the [Worklist App](Worklist_App_6a6a621.md) tutorial for an example of how this application can be extended. The result of this tutorial can be seen as the *Manage Products* app in the *Demo Apps* section of the Demo Kit.

***

<a name="loioa77f2d29299247f8a3e30226507b1765__section_EnhanceTemplate"/>

### How Do I Enhance the Template?

In our template, we use a simple layout that you can use as a basis for enhancements. For example, if you want to use an object page with a dynamic header, you can use one of the page-type [Object Page Layout samples](https://openui5.hana.ondemand.com/#/sample/sap.uxap.sample.ObjectPageDynamicHeader/preview). All you have to do is replace the relevant content in the template with the content from the sample.

You can find more information about the possibilities of object pages at [SAP Fiori Design Guidelines - Object Page](https://experience.sap.com/fiori-design-web/object-page/).

-   **[Navigation](Navigation_106d2e9.md "The navigation flow of the Worklist app is very simple as it only contains two main
		views and the not found pages that are displayed as a message to the
		user in case of navigation errors.")**  
The navigation flow of the Worklist app is very simple as it only contains two main views and the *not found* pages that are displayed as a message to the user in case of navigation errors.
-   **[Busy Indication](Busy_Indication_5cb1169.md "The Worklist app implements a busy indication concept as specified by the SAP Fiori
		Design Guidelines.")**  
The Worklist app implements a busy indication concept as specified by the SAP Fiori Design Guidelines.
-   **[Model Instantiation](Model_Instantiation_c2f4684.md "The app configures several data models that are used throughout the app to update the
		views or to store additional configuration options.")**  
The app configures several data models that are used throughout the app to update the views or to store additional configuration options.
-   **[Send Email](Send_Email_af1db3c.md "The Send Email feature is a sharing option that can be found in
		the share menu of each view.")**  
The **Send Email** feature is a sharing option that can be found in the share menu of each view.
-   **[Testing](Testing_7bd4e6e.md "The templates include basic testing features, unit tests as well as integration tests
		for a basic test coverage of the initial app. The tests are written independently of the
		actual data displayed in the app.")**  
The templates include basic testing features, unit tests as well as integration tests for a basic test coverage of the initial app. The tests are written independently of the actual data displayed in the app.
-   **[Device Adaptation](Device_Adaptation_979f571.md "The following section outlines the best practices for ensuring your worklist apps adapt
		to different kinds of devices in the best way possible.")**  
The following section outlines the best practices for ensuring your worklist apps adapt to different kinds of devices in the best way possible.
-   **[Stable IDs](Stable_IDs_03b2007.md "Setting stable IDs is crucial if your app is used in
		combination with certain functions.")**  
Setting stable IDs is crucial if your app is used in combination with certain functions.

**Related Information**  


[Demo Apps](Demo_Apps_a3ab54e.md "With the Demo Kit, we deliver some demo apps that show you how you can use the various features and controls of OpenUI5.")

[Development Environment](Development_Environment_7bb04e0.md "This part of the documentation introduces you to some common and recommended use cases for the installation, configuration, and setup of OpenUI5 development environments.")

[Worklist App](Worklist_App_6a6a621.md "In this tutorial we will build an app using OpenUI5 that, for example, a shop owner can use to manage his product stock levels.")

