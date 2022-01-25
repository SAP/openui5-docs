<!-- loio8b49fc198bf04b2d9800fc37fecbb218 -->

| loio |
| -----|
| 8b49fc198bf04b2d9800fc37fecbb218 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8b49fc198bf04b2d9800fc37fecbb218) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8b49fc198bf04b2d9800fc37fecbb218)</div>

## Tutorials

Set up your development environment and go through our tutorials. They introduce you to all major development paradigms of OpenUI5 using practical examples in an interactive format. The demo apps show OpenUI5 in action.

***

<a name="loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_prerequisites"/>

### Prerequisites and Setup

-   You should be familiar with JavaScript.

-   Set up your [Development Environment](Development_Environment_7bb04e0.md).

-   Set up a folder where you would place the application content. We will refer to this folder as the “app folder”.


***

<a name="loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_path"/>

### Learning Path

![](loio024b7d89525741ae98661d3b7caf319d_LowRes.png)

-   [Quick Start](Quick_Start_592f36f.md)
-   [Walkthrough](Walkthrough_3da5f4b.md)
-   [Troubleshooting](Troubleshooting_5661952.md)
-   [Data Binding](Data_Binding_e531093.md)
-   [OData V4](OData_V4_bcdbde6.md)
-   [Navigation and Routing](Navigation_and_Routing_1b6dcd3.md)
-   [Testing](Testing_291c912.md)
-   [OData V2 Mock Server](OData_V2_Mock_Server_3a9728e.md)
-   [Worklist App](Worklist_App_6a6a621.md)
-   [Flexible Column Layout App](Flexible_Column_Layout_App_c4de2df.md)

***

> ### Tip:  
> **Learn with openSAP:**
> 
> The openSAP course [Developing Web Apps with SAPUI5](https://open.sap.com/courses/ui51) introduces you to the main concepts of SAPUI5.
> 
> The JavaScript exercises for each unit will give you the technical background needed to develop your own responsive Web apps. We’ll start from scratch with the very basics and lots of hands-on coding. As we go through the weeks of this course, you’ll learn more about the powerful development concepts and truly master SAPUI5.
> 
> The openSAP course [Evolved Web Apps with SAPUI5](https://open.sap.com/courses/ui52) for more experienced SAPUI5 developers and ambitious beginners introduces more advanced scenarios and concepts.

***

<a name="loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_download"/>

### Downloading Code for a Tutorial Step

To download the code from the Demo Kit, follow these steps:

1.  Choose the link in the *Coding* section of the tutorial step you want to work on or find the code in the *Samples* section of the Demo Kit \(filter by "*Tutorial*" to get a list of the tutorials that are available\).

2.  Choose the icon with the *Show source code for this sample* tooltip in the right-hand part of the header bar to display all files included in this sample.

3.  Choose the *Download* button. A `zip` file is downloaded to your local machine.

4.  Extract or upload the `zip` file to your development environment.

5.  Adjust the project configuration files to match your development environment as described below.

6.  Test the project by calling one of the HTML pages in your development environment and make sure that the app is displaying the features exactly as shown in the preview of the step.


***

<a name="loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_adaptation"/>

### Adapting Code to Your Development Environment

You might have to adapt parts of the coding to your local development environment to make the app work. Please check the following settings carefully:

-   **Project Path and Deployment**

    All tutorials assume that the app is deployed and can be accessed under a certain path on a web server. You will not be able to run the app without a Web server as the browser does not allow you to load the required resources locally due to security restrictions.

-   **OpenUI5 Resources**

    You can either download and deploy the runtime to your \(local\) Web server or reference the CDN version located at `https://openui5.hana.ondemand.com/resources/sap-ui-core.js`. Some development environments such as the SAP Web IDE also provide a local runtime for testing purposes. If you download the code from the samples in the Demo Kit, you will have to adapt the **resource path in the bootstrap section** of all HTML pages included in the project. In the tutorial code, we assume that OpenUI5 can be accessed from the `/resources` path of the server.

-   **Accessing Remote Services**

    Browsers typically prevent accessing remote resources due to the Cross-Origin Resource Sharing \(CORS\) policy. If you would like to call a real service or remote resources, you will have to either configure the development environment or the remote server to accept these requests. This strongly depends on the development environment and is described in more detail below.


***

<a name="loio8b49fc198bf04b2d9800fc37fecbb218__tutorials_troubleshooting"/>

### Troubleshooting

If you get stuck, check the [Troubleshooting](Troubleshooting_615d9e4.md) section under *Essentials*, or refer to the [Troubleshooting tutorial](Troubleshooting_5661952.md).

If you can't fix the problem, try downloading the solution of the previews or current step. This should get your project fixed again, just don’t forget to check the resource path and the project configuration files again.

***

<a name="loio8b49fc198bf04b2d9800fc37fecbb218__section_fbp_hjc_tkb"/>

### See OpenUI5 in Action - Our Demo Apps

If you want to see some practical examples for OpenUI5 apps, check out our [Demo Apps](https://openui5.hana.ondemand.com/#/demoapps). These are fully-functional apps that showcase certain floorplans, control libraries, or other OpenUI5 features. You can also download the source code of each demo app to find out how everything works together. Feel free to explore!

-   **[Development Environment](Development_Environment_7bb04e0.md "This part of the documentation introduces you to some common and recommended use cases for the installation, configuration, and setup
		of OpenUI5 development environments.")**  
This part of the documentation introduces you to some common and recommended use cases for the installation, configuration, and setup of OpenUI5 development environments.
-   **[Quick Start](Quick_Start_592f36f.md "Unleash your OpenUI5 skills with this simple three-step tutorial. We start
		with a simple &quot;Hello World&quot; example, and convert it to a minimalist two-page app.")**  
Unleash your OpenUI5 skills with this simple three-step tutorial. We start with a simple "Hello World" example, and convert it to a minimalist two-page app.
-   **[Walkthrough](Walkthrough_3da5f4b.md "In this tutorial we will introduce you to all major development paradigms of OpenUI5.")**  
In this tutorial we will introduce you to all major development paradigms of OpenUI5.
-   **[Troubleshooting](Troubleshooting_5661952.md "In this tutorial, we will show you some tools that will help you if you run into
		problems with your OpenUI5
		app.")**  
In this tutorial, we will show you some tools that will help you if you run into problems with your OpenUI5 app.
-   **[Data Binding](Data_Binding_e531093.md "In this tutorial, we will explain the concepts of data binding in OpenUI5. ")**  
In this tutorial, we will explain the concepts of data binding in OpenUI5.
-   **[OData V4](OData_V4_bcdbde6.md "In this tutorial, we explore how features of OData V4 can be used in OpenUI5. We write a small app that consumes data from an OData V4 service to understand how to access, modify, aggregate, and filter data in an OData V4 model.")**  
In this tutorial, we explore how features of OData V4 can be used in OpenUI5. We write a small app that consumes data from an OData V4 service to understand how to access, modify, aggregate, and filter data in an OData V4 model.
-   **[Navigation and Routing](Navigation_and_Routing_1b6dcd3.md "OpenUI5 comes with a powerful routing API that helps you control the state of your
		application efficiently. This tutorial will illustrate all major features and APIs related to navigation and routing in OpenUI5 apps by creating a simple and easy to understand mobile app. It represents a set of
		best practices for applying the navigation and routing features of OpenUI5 to your
		applications.")**  
OpenUI5 comes with a powerful routing API that helps you control the state of your application efficiently. This tutorial will illustrate all major features and APIs related to navigation and routing in OpenUI5 apps by creating a simple and easy to understand mobile app. It represents a set of best practices for applying the navigation and routing features of OpenUI5 to your applications.
-   **[Testing](Testing_291c912.md "In this tutorial we will test application functionality with the testing tools that are delivered with OpenUI5. At different steps of this tutorial you will write tests using QUnit,
		OPA5, and the OData V2 mock server. Additionally, you will learn about testing strategies, Test Driven Development (TDD), and much more. ")**  
In this tutorial we will test application functionality with the testing tools that are delivered with OpenUI5. At different steps of this tutorial you will write tests using QUnit, OPA5, and the OData V2 mock server. Additionally, you will learn about testing strategies, Test Driven Development \(TDD\), and much more.
-   **[OData V2 Mock Server](OData_V2_Mock_Server_3a9728e.md "In this tutorial, we will explore some advanced features of the OData V2 mock server. ")**  
In this tutorial, we will explore some advanced features of the OData V2 mock server.
-   **[Worklist App](Worklist_App_6a6a621.md "In this tutorial we will build an app using OpenUI5 that, for example, a
		shop owner can use to manage his product stock levels.")**  
In this tutorial we will build an app using OpenUI5 that, for example, a shop owner can use to manage his product stock levels.
-   **[Flexible Column Layout App](Flexible_Column_Layout_App_c4de2df.md "In this tutorial, we showcase how to structure your OpenUI5 app using the layout
		patterns that comply with the SAP Fiori design guidelines.")**  
In this tutorial, we showcase how to structure your OpenUI5 app using the layout patterns that comply with the SAP Fiori design guidelines.
-   **[Demo Apps](Demo_Apps_a3ab54e.md "With the Demo Kit, we deliver some demo apps that show you how you can use the
		various features and controls of OpenUI5.")**  
With the Demo Kit, we deliver some demo apps that show you how you can use the various features and controls of OpenUI5.
-   **[Best Practices for App Developers](Best_Practices_for_App_Developers_28fcd55.md "In this section, we have compiled a set of best practice recommendations to help you develop high-quality OpenUI5 apps.")**  
In this section, we have compiled a set of best practice recommendations to help you develop high-quality OpenUI5 apps.

**Related Information**  


[Developing Apps with SAP Fiori Tools](https://help.sap.com/viewer/3343ff76a027486c829f8aa5b0fde28f/DEV_SAPUI5_ABAP/en-US/a460a7348a6c431a8bd967ab9fb8d918.html "SAP Fiori tools is a set of extensions for SAP Business Application Studio and Visual Studio Code that makes it faster and easier to develop basic SAP Fiori apps.") :arrow_upper_right:

[Demo Apps](Demo_Apps_a3ab54e.md "With the Demo Kit, we deliver some demo apps that show you how you can use the various features and controls of OpenUI5.")

