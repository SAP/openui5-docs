<!-- loio23cfd955f58142389fa7c9097e11559c -->

| loio |
| -----|
| 23cfd955f58142389fa7c9097e11559c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/23cfd955f58142389fa7c9097e11559c) | [demo kit latest release](https://sdk.openui5.org/topic/23cfd955f58142389fa7c9097e11559c)</div>

## Developing Apps

Create apps with rich user interfaces for modern web business applications, responsive across browsers and devices, based on HTML5.

***

![](images/loio71f8bf5edae54fad91ea855da95f2f97_LowRes.png)

***

<a name="loio23cfd955f58142389fa7c9097e11559c__section_ovf_25f_qbb"/>

### Project Setup

Before you start developing apps with OpenUI5, you start by setting up the development environment of your choice. You can find our recommendations under [Development Environment](Development_Environment_7bb04e0.md).

After that, you define the project setup. If you work in a team, we recommend using a continuous integration setup as described under [Continuous Integration: Ensure Code Quality](Continuous_Integration_Ensure_Code_Quality_fe7a158.md). If you work alone, you should at the very least set up an automated testing environment.

***

<a name="loio23cfd955f58142389fa7c9097e11559c__section_znq_f5f_qbb"/>

### Development

When faced with developing an app, you have several ways to get started ranging from app templates or a make-em-completely-from-scratch approach. But which approach is right for your situation? In most cases, it's your level of expertise or need for flexibility and freedom that will decide.

If you're skilled at coding and want the freedom and flexibility, you can build an app completely from scratch. In the chapters in this section, you will find some guidance on how to deal with crucial concepts such as accessibility, security, device adaptation.

Be sure to check out information about things that you really should avoid doing while coding: [Coding Issues to Avoid](Coding_Issues_to_Avoid_3877872.md).

***

<a name="loio23cfd955f58142389fa7c9097e11559c__section_vp3_n5f_qbb"/>

### Packaging and Deployment

How you deploy your app when you're finished depends on the tools you use and the platform where your app is going to run. See the related documentation for details.

For example, it's quite easy to deploy an app to SAP Business Technology Platform with SAP Business Application Studio. For more information about SAP Business Application Studio, see the documentation on the SAP Help Portal at [SAP Business Application Studio](https://help.sap.com/viewer/product/SAP%20Business%20Application%20Studio/Cloud/en-US).

> ### Note:  
> For more information about packaging apps, read the blog post [Optimizing OpenUI5/SAPUI5 Apps](https://blogs.sap.com/2015/02/18/optimizing-openui5-apps/).

-   **[Continuous Integration: Ensure Code Quality](Continuous_Integration_Ensure_Code_Quality_fe7a158.md "This section describes the setup of a development project where multiple developers
		work together on the same code.")**  
This section describes the setup of a development project where multiple developers work together on the same code.
-   **[App Overview: The Basic Files of Your App](App_Overview_The_Basic_Files_of_Your_App_28b59ca.md "We recommend creating at least three files for your app: the descriptor
			(manifest.json), the component (Component.js),
		and the main view of the app (App.view.xml).")**  
We recommend creating at least three files for your app: the descriptor \(`manifest.json`\), the component \(`Component.js`\), and the main view of the app \(`App.view.xml`\).
-   **[App Initialization: What Happens When an App Is Started?](App_Initialization_What_Happens_When_an_App_Is_Started_d2f5869.md "When a user starts an app (in the SAP Fiori launchpad (FLP) or using an HTML page),
		several steps will be performed in the background.")**  
When a user starts an app \(in the SAP Fiori launchpad \(FLP\) or using an HTML page\), several steps will be performed in the background.
-   **[Folder Structure: Where to Put Your Files](Folder_Structure_Where_to_Put_Your_Files_003f755.md "The details described here represent a best practice for structuring an application
		that features one component, one OData service and less than 20 views. If you're building an
		app that has more components, OData services and views, you may have to introduce more
		folder levels than described here.")**  
The details described here represent a best practice for structuring an application that features one component, one OData service and less than 20 views. If you're building an app that has more components, OData services and views, you may have to introduce more folder levels than described here.
-   **[Device Adaptation: Using Device Models for Your App](Device_Adaptation_Using_Device_Models_for_Your_App_8dbd35e.md "Depending on the capabilities of the device on which the app is running, the
		functionality and the design of the application might differ. By introducing a local JSON
		model holding the device-dependent data, we can bind properties of our views to the device's
		capabilities.")**  
Depending on the capabilities of the device on which the app is running, the functionality and the design of the application might differ. By introducing a local JSON model holding the device-dependent data, we can bind properties of our views to the device's capabilities.
-   **[Performance: Speed Up Your App](Performance_Speed_Up_Your_App_408b40e.md "If a web app has performance issues, finding the cause can be both a time-consuming
		and nerve-consuming task. To help you avoid and solve performance issues in your app, here
		are some good practices we've discovered while dealing with OpenUI5 apps. ")**  
If a web app has performance issues, finding the cause can be both a time-consuming and nerve-consuming task. To help you avoid and solve performance issues in your app, here are some good practices we've discovered while dealing with OpenUI5 apps.
-   **[Stable IDs: All You Need to Know](Stable_IDs_All_You_Need_to_Know_f51dbb7.md "Stable IDs are IDs for controls, elements, or components that you set yourself in the
		respective id property or attribute as opposed to IDs that are generated by
			OpenUI5. Stable means
		that the IDs are concatenated with the application component ID and do not have any
		auto-generated parts.")**  
Stable IDs are IDs for controls, elements, or components that you set yourself in the respective `id` property or attribute as opposed to IDs that are generated by OpenUI5. *Stable* means that the IDs are concatenated with the application component ID and do not have any auto-generated parts.
-   **[Reacting on User Input Events](Reacting_on_User_Input_Events_c75861e.md "User input events can either be handled automatically by the framework or manually by the application.")**  
User input events can either be handled automatically by the framework or manually by the application.
-   **[Whitespaces Concept](Whitespaces_Concept_37deb0b.md "Whitespace characters represent the empty space between all the characters that you can
		see on the screen.")**  
Whitespace characters represent the empty space between all the characters that you can see on the screen.
-   **[Coding Issues to Avoid](Coding_Issues_to_Avoid_3877872.md "This section lists some of the most important issues that should be avoided when
		creating applications using OpenUI5, split into different categories for reasons of
		simplicity.")**  
This section lists some of the most important issues that should be avoided when creating applications using OpenUI5, split into different categories for reasons of simplicity.
-   **[Securing Apps](Securing_Apps_91f3d87.md "The following section provides information about security aspects of OpenUI5. The information is
        intended for OpenUI5 application
        and control developers, as well as to system administrators running applications based on
            OpenUI5.")**  
The following section provides information about security aspects of OpenUI5. The information is intended for OpenUI5 application and control developers, as well as to system administrators running applications based on OpenUI5.
-   **[Right-to-Left Support](Right_to_Left_Support_8d7b286.md "OpenUI5 application
		developers need to be aware of how applications behave when right-to-left (RTL)
		directionality is selected. Changing the directionality has a big impact on text-displaying
		controls, images and the alignment of the whole application.")**  
OpenUI5 application developers need to be aware of how applications behave when right-to-left \(RTL\) directionality is selected. Changing the directionality has a big impact on text-displaying controls, images and the alignment of the whole application.
-   **[Accessibility](Accessibility_03b914b.md "In this guide we cover the most important accessibility aspects for application
		development, based on OpenUI5.")**  
In this guide we cover the most important accessibility aspects for application development, based on OpenUI5.

