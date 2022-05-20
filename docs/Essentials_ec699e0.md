<!-- loioec699e0817fb46a0817b0fa276a249f8 -->

| loio |
| -----|
| ec699e0817fb46a0817b0fa276a249f8 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/ec699e0817fb46a0817b0fa276a249f8) | [demo kit latest release](https://sdk.openui5.org/topic/ec699e0817fb46a0817b0fa276a249f8)</div>

## Essentials

This chapter and its sections describe the development concepts of OpenUI5, such as the Model View Controller, data binding, and components. Use this section as a reference.

***

<a name="loioec699e0817fb46a0817b0fa276a249f8__section_jdv_3zg_yz"/>

### OpenUI5 Architecture

 ![OpenUI5 Architecture Overview](images/loio99b4be76a3f94db18172e67e730fb7fb_LowRes.png) 

OpenUI5 is a client UI technology based on JavaScript, CSS and HTML5.

Apps developed with OpenUI5 run in a browser on any device \(mobile, tablet or desktop PC\).

When users access an OpenUI5 app, a request is sent to the respective server to load the application into the browser. The view accesses the relevant libraries. Usually the model is also instantiated and business data is fetched from the database.

Depending on the environment in which OpenUI5 is used, the libraries or your applications can be stored, for example, on an SAP NetWeaver Application Server or an SAP Business Technology Platform, and business data can be accessed, for example, using the OData model through a SAP Gateway.

***

### Artifacts in the Framework

The top-level structural unit is called a **library**. Libraries are the main artifacts in the extensibility concept. They bundle a set of controls and related types and make them consumable by Web applications. There are predefined and standard libraries, like `sap.m`, with many commonly used controls. At the same time, it treats custom UI libraries as first-class citizens, making it easy for you to write and use your own controls alongside the predefined ones.

A UI **element** is the basic building block of our user interfaces; it is a reusable entity with properties, events, methods, and relations. The most important relations are aggregations to other UI elements, and in this way a tree structure of elements can be created.

From a developer's point of view, a **control** \(e.g. `Button`, `Label`, `TextField`, or `Table`\) is the most important artifact. It is an object which controls the appearance and user interaction of a rectangular screen region. It is a special kind of user interface element which can be used as the root of such a tree structure. In this way, it serves as an entry point, especially for rendering. Besides controls, there are also other **non-control elements**, which cannot be used as the root of such a tree structure, but only as a dependent part within it \(e.g. `TableRow`, `TableCell`\).

**Data types** are first-class entities in the meta model. This allows reuse of types across libraries and extensibility of the type system. The core library \(technically, this is the `sap.ui.core` library\) already defines a core set of types that can be used in other libraries.

-   **[Bootstrapping: Loading and Initializing](Bootstrapping_Loading_and_Initializing_a04b0d1.md "To use OpenUI5 features
		in your HTML page, you have to load and initialize the SAPUI5 library.")**  
To use OpenUI5 features in your HTML page, you have to load and initialize the SAPUI5 library.
-   **[Structuring: Components and Descriptor](Structuring_Components_and_Descriptor_dc9e11c.md "OpenUI5 provides Components as independent and reusable parts of UI5
		applications. They facilitate the encapsulation of closely related parts of an application, thus enabling developers to structure and maintain
		their applications more easily.")**  
OpenUI5 provides Components as independent and reusable parts of UI5 applications. They facilitate the encapsulation of closely related parts of an application, thus enabling developers to structure and maintain their applications more easily.
-   **[Model View Controller \(MVC\)](Model_View_Controller_MVC_91f2334.md "The Model View Controller (MVC) concept is used in OpenUI5 to separate the
		representation of information from the user interaction. This separation facilitates development and the changing of parts independently.")**  
The Model View Controller \(MVC\) concept is used in OpenUI5 to separate the representation of information from the user interaction. This separation facilitates development and the changing of parts independently.
-   **[Data Binding](Data_Binding_68b9644.md "You use data binding to bind UI elements to data sources to keep the data in sync and
		allow data editing on the UI.")**  
You use data binding to bind UI elements to data sources to keep the data in sync and allow data editing on the UI.
-   **[Reusing UI Parts: Fragments](Reusing_UI_Parts_Fragments_36a5b13.md "Fragments are light-weight UI parts (UI sub-trees) which can be reused, defined similar
		to views, but do not have any controller or other behavior code involved.")**  
Fragments are light-weight UI parts \(UI sub-trees\) which can be reused, defined similar to views, but do not have any controller or other behavior code involved.
-   **[XML Templating](XML_Templating_5ee619f.md "The XML templating concept enables you to use an XML view as a template. This
		template is transformed by an XML preprocessor on the source level, the XML DOM, at runtime
		just before an OpenUI5 control
		tree is created from the XML source.")**  
The XML templating concept enables you to use an XML view as a template. This template is transformed by an XML preprocessor on the source level, the XML DOM, at runtime just before an OpenUI5 control tree is created from the XML source.
-   **[Working with Controls](Working_with_Controls_91f0a22.md "Controls are used to define the appearance and behavior of screen areas.")**  
Controls are used to define the appearance and behavior of screen areas.
-   **[Declarative Support](Declarative_Support_91f1301.md "Declarative programming allows you to define the UI within the HTML document as
		elements.")**  
Declarative programming allows you to define the UI within the HTML document as elements.
-   **[Error, Warning, and Info Messages](Error_Warning_and_Info_Messages_62b1481.md "
		OpenUI5 provides a central place
		for storing and managing info, warning, and error messages.")**  
 OpenUI5 provides a central place for storing and managing info, warning, and error messages.
-   **[Routing and Navigation](Routing_and_Navigation_3d18f20.md "OpenUI5 offers hash-based
        navigation, which allows you to build single-page apps where the navigation is done by
        changing the hash. In this way the browser does not have to reload the page; instead there
        is a callback to which the app and especially the affected view can react. A hash string is
        parsed and matched against patterns which will then inform the handlers.")**  
OpenUI5 offers hash-based navigation, which allows you to build single-page apps where the navigation is done by changing the hash. In this way the browser does not have to reload the page; instead there is a callback to which the app and especially the affected view can react. A hash string is parsed and matched against patterns which will then inform the handlers.
-   **[Modules and Dependencies](Modules_and_Dependencies_91f23a7.md "The OpenUI5 framework has
		built-in support for modularizing comprehensive JavaScript applications. That means, instead
		of defining and loading one large bundle of JavaScript code, an application can be split
		into smaller parts which then can be loaded at runtime at the time when they are needed.
		These smaller individual files are called modules.")**  
The OpenUI5 framework has built-in support for modularizing comprehensive JavaScript applications. That means, instead of defining and loading one large bundle of JavaScript code, an application can be split into smaller parts which then can be loaded at runtime at the time when they are needed. These smaller individual files are called modules.
-   **[Optimizing Applications](Optimizing_Applications_2f492c4.md "OpenUI5 supports several
		means of optimizing the loading time for applications.")**  
OpenUI5 supports several means of optimizing the loading time for applications.
-   **[Adapting to Operating Systems And Devices](Adapting_to_Operating_Systems_And_Devices_50eadaa.md "No need to worry about device specifics! OpenUI5 apps run on smartphones,
		tablets, and desktops. The UI controls automatically adapt themselves to each device's
		capabilities and make the most of the available real estate. supports several functions to
		adapt to operating systems and devices.")**  
No need to worry about device specifics! OpenUI5 apps run on smartphones, tablets, and desktops. The UI controls automatically adapt themselves to each device's capabilities and make the most of the available real estate. supports several functions to adapt to operating systems and devices.
-   **[Testing](Testing_7cdee40.md "OpenUI5 provides several testing options, like to unit and integration tests
		and the OData V2 mock server.")**  
OpenUI5 provides several testing options, like to unit and integration tests and the OData V2 mock server.
-   **[Theming](Theming_497c27a.md "OpenUI5 is an HTML UI
		library, therefore styling is done using Cascading Style Sheets (CSS). This allows for
		creating an impressive visual experience using a widely known standard technology which is
		well-accepted on the market.")**  
OpenUI5 is an HTML UI library, therefore styling is done using Cascading Style Sheets \(CSS\). This allows for creating an impressive visual experience using a widely known standard technology which is well-accepted on the market.
-   **[Localization](Localization_91f217c.md "The framework concepts for text localization in OpenUI5 are aligned with the general
		concepts of the Java platform. ")**  
The framework concepts for text localization in OpenUI5 are aligned with the general concepts of the Java platform.
-   **[Accessibility](Accessibility_322f55d.md "Accessibility features are essential for the usability of each application and essential
		for users with disabilities. In an ongoing approach, OpenUI5 controls aim to comply
		with various accessibility standards such as screen reader support, high contrast theming,
		and keyboard handling.")**  
Accessibility features are essential for the usability of each application and essential for users with disabilities. In an ongoing approach, OpenUI5 controls aim to comply with various accessibility standards such as screen reader support, high contrast theming, and keyboard handling.
-   **[Drag and Drop](Drag_and_Drop_3ddb6cd.md "Drag and drop allows you to easily move, rearrange, and restructure items, for example,
		in a list or hierarchy structure.")**  
Drag and drop allows you to easily move, rearrange, and restructure items, for example, in a list or hierarchy structure.
-   **[Troubleshooting](Troubleshooting_615d9e4.md "This section describes the various tools that are available for troubleshooting apps
		developed with OpenUI5")**  
This section describes the various tools that are available for troubleshooting apps developed with OpenUI5

