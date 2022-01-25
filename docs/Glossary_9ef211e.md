<!-- loio9ef211e569ed4f819af904ba360ea7f6 -->

| loio |
| -----|
| 9ef211e569ed4f819af904ba360ea7f6 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9ef211e569ed4f819af904ba360ea7f6) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9ef211e569ed4f819af904ba360ea7f6)</div>

## Glossary

List of terms used in OpenUI5.


<table>
<tr>
<th valign="top">

Term



</th>
<th valign="top">

Meaning



</th>
<th valign="top">

Source/Comments



</th>
<th valign="top">

Link



</th>
</tr>
<tr>
<td valign="top">

SAPUI5 ABAP repository



</td>
<td valign="top">

Used to store SAPUI5 apps, components, and libraries; based on the Business Server Page \(BSP\) repository of the ABAP server.

A SAPUI5 application stored in the ABAP repository can be deployed and executed in a browser directly. It is connected to the ABAP transport system.



</td>
<td valign="top">

SAPUI5 only



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

aggregation



</td>
<td valign="top">

An **aggregation** is a special relation between two UI element types. It is used to define the parent-child relationship within the tree structure. The parent end of the aggregation has cardinality 0..1, while the child end may have 0..1 or 0..\*. The element's API offers convenient and consistent methods to deal with aggregations \(e.g. to get, set, or remove target elements\). Examples are table rows and cells, or the content of a table cell.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Essentials](Essentials_ec699e0.md)



</td>
</tr>
<tr>
<td valign="top">

association



</td>
<td valign="top">

An **association** is a type of relation between two UI element types which is independent of the parent-child relationship within the tree structure. Directed outgoing associations to a target of cardinality 0..1 are supported. They represent a loose coupling only and are thus implemented by storing the target element instance's ID. The most prominent example is the association between a label and its field.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Essentials](Essentials_ec699e0.md)



</td>
</tr>
<tr>
<td valign="top">

ARIA



</td>
<td valign="top">

*WAI-ARIA, the Accessible Rich Internet Applications Suite, defines a way to make Web content and Web applications more accessible to people with disabilities. It especially helps with dynamic content and advanced user interface controls developed with Ajax, HTML, JavaScript, and related technologies.* \(Quote from w3c.org\)



</td>
<td valign="top">

`w3c.org`



</td>
<td valign="top">

[W3C ARIA](https://www.w3.org/WAI/intro/aria)



</td>
</tr>
<tr>
<td valign="top">

asynchronous \(async\) processing



</td>
<td valign="top">

In contrast to synchronous processing this processing mode does not keep the browser thread busy but does the processing in the background and continues with the next task. Code can be executed asynchronously and a callback function is triggered when a certain condition is met. Similarly, a file can be loaded asynchronously. Asynchronous processing is highly recommended for performance reasons and to not freeze the UI.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

asynchronous module definition \(AMD\)



</td>
<td valign="top">

A mechanism for defining a module in a way that modules and their dependencies can be loaded asynchronously.



</td>
<td valign="top">

`requirejs.org`



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

bootstrap



</td>
<td valign="top">

To use the OpenUI5 features in your web page, you have to load and initialize – or "bootstrap" – the OpenUI5 runtime in your HTML page.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Bootstrapping: Loading and Initializing](Bootstrapping_Loading_and_Initializing_a04b0d1.md)



</td>
</tr>
<tr>
<td valign="top">

BPMN



</td>
<td valign="top">

*A standard Business Process Model and Notation \(BPMN\) will provide businesses with the capability of understanding their internal business procedures in a graphical notation and will give organizations the ability to communicate these procedures in a standard manner. Furthermore, the graphical notation will facilitate the understanding of the performance collaborations and business transactions between the organizations.*



</td>
<td valign="top">

`bpmn.org`



</td>
<td valign="top">

[BPMN.org](http://www.bpmn.org)



</td>
</tr>
<tr>
<td valign="top">

\(application\) cache buster



</td>
<td valign="top">

A cache buster allows the application to notify the browser to refresh the resources only when the application resources have been changed. Otherwise the resources can always be fetched from the browser's cache. The application cache buster is a special mechanism to extend this function to application resources



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Cache Buster for OpenUI5](Cache_Buster_for_OpenUI5_91f0809.md)

[Application Cache Buster](Application_Cache_Buster_ff7aced.md)



</td>
</tr>
<tr>
<td valign="top">

cache busting: single application resources



</td>
<td valign="top">

Cache busting on the level of a single app, component, or library in the SAPUI5 ABAP repository



</td>
<td valign="top">

SAPUI5 only



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

cache busting; multiple application resources



</td>
<td valign="top">

Cache busting on the level of multiple apps, components, or libraries in the SAPUI5 ABAP repository



</td>
<td valign="top">

SAPUI5 only



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

clickjacking



</td>
<td valign="top">

Clickjacking, or UI redressing, tricks the user into triggering actions within an application by redirecting clicks. This is done, for example, by using an invisible iFrame which is positioned above a fake UI. When the user clicks on something on the fake UI, the content of the invisible iFrame handles the click.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Browser Security](Browser_Security_91f3b66.md)



</td>
</tr>
<tr>
<td valign="top">

composite control



</td>
<td valign="top">

Composite controls are intended for reuse within control development and allow you to include existing controls in a complex control.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Standard Composite Controls](Standard_Composite_Controls_c1512f6.md)



</td>
</tr>
<tr>
<td valign="top">

content density



</td>
<td valign="top">

The devices used to run apps that are developed with SAPUI5 run on various different operating systems and have very different screen sizes. SAPUI5 contains different content densities for certain controls that allow your app to adapt to the device in question, allowing you to display larger controls for touch-enabled devices and a smaller, more compact design for devices that are operated by mouse.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Content Densities](Content_Densities_e54f729.md)



</td>
</tr>
<tr>
<td valign="top">

control



</td>
<td valign="top">

UI elements that can be used independently.

From a developer's point of view, a **control** \(e.g. `Button`, `Label`, `TextField`, or `Table`\) is the most important artifact. It is an object which controls the appearance and user interaction of a rectangular screen region. It is a special kind of user interface element which can be used as the root of such a tree structure. In this way, it serves as an entry point, especially for rendering. Besides controls, there are also other **non-control elements**, which cannot be used as the root of such a tree structure, but only as a dependent part within it \(e.g. `TableRow`, `TableCell`\).



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[More About Controls](More_About_Controls_3ec6808.md)

[Samples](https://openui5.hana.ondemand.com/explored.html)

[API Reference](https://openui5.hana.ondemand.com/#docs/api/index.html)

[Essentials](Essentials_ec699e0.md)



</td>
</tr>
<tr>
<td valign="top">

controller



</td>
<td valign="top">

An application unit containing the active part of the application. It is the logical interface between a model and a view, and corresponds to the model view controller \(MVC\) concept.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Controller](Controller_121b8e6.md)



</td>
</tr>
<tr>
<td valign="top">

Cross-Site Scripting \(XSS\)



</td>
<td valign="top">

Cross-site scripting is about injecting script code into a web page, which is then executed in the context of the page. Therefore it can access any information which is currently displayed on the screen. Additionally, XSS attacks can access session information contained in cookies, or send new requests to the server within the current session, or even try to exploit browser vulnerabilities to get full access to the machine that the browser is running on.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Cross-Site Scripting](Cross_Site_Scripting_91f0bd3.md)



</td>
</tr>
<tr>
<td valign="top">

data binding



</td>
<td valign="top">

A technique that binds two data sources together in order to keep them in sync. All changes in one data source are automatically reflected in the other; the involved layers are the view and the model.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Data Binding](Data_Binding_68b9644.md)



</td>
</tr>
<tr>
<td valign="top">

data type



</td>
<td valign="top">

**Data types** are first-class entities in the meta model. This allows reuse of types across libraries and extensibility of the type system. The core library \(technically, this is the `sap.ui.core` library\) already defines a core set of types that can be used in other libraries.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Essentials](Essentials_ec699e0.md)



</td>
</tr>
<tr>
<td valign="top">

Demo Kit



</td>
<td valign="top">

The Demo Kit is the OpenUI5 software development kit \(SDK\). The Demo Kit is your one-stop shop for all information about OpenUI5: documentation, API reference, samples, demo apps.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

diagnostics



</td>
<td valign="top">

A diagnostics window is available in OpenUI5 applications.

To open it, use the following [shortcut](Keyboard_Shortcuts_for_OpenUI5_Tools_154844c.md):  [Ctrl\] + [Shift\] + [Alt\] /[Option\][S\] 



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Diagnostics](Diagnostics_6ec18e8.md#loio6ec18e80b0ce47f290bc2645b0cc86e6)



</td>
</tr>
<tr>
<td valign="top">

distribution layer



</td>
<td valign="top">

Contains the control libraries and theme libraries; the SAPUI5 distribution layer is delivered to customers via the MIME repository.



</td>
<td valign="top">

SAPUI5 only



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Document Object Model \(DOM\)



</td>
<td valign="top">

*The Document Object Model is a platform- and language-neutral interface that will allow programs and scripts to dynamically access and update the content, structure and style of documents. The document can be further processed and the results of that processing can be incorporated back into the presented page.* \(Quote from w3c.org\)



</td>
<td valign="top">

`w3c.org`



</td>
<td valign="top">

[W3C DOM](http://www.w3.org/DOM/)



</td>
</tr>
<tr>
<td valign="top">

element



</td>
<td valign="top">

A \(UI\) **element** is the basic building block of our user interfaces; it is a reusable entity with properties, events, methods, and relations. The most important relations are aggregations to other UI elements, and in this way a tree structure of elements can be created.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Essentials](Essentials_ec699e0.md)



</td>
</tr>
<tr>
<td valign="top">

SAP Fiori



</td>
<td valign="top">

SAP Fiori is the user experience \(UX\) for SAP software that applies modern design principles. SAP solutions are using the SAP Fiori UX to provide a personalized, responsive, and simple user experience.



</td>
<td valign="top">

SAP Fiori



</td>
<td valign="top">

[http://www.sap.com/fiori](http://www.sap.com/fiori)

[http://help.sap.com/fiori](http://help.sap.com/fiori)

[https://experience.sap.com/fiori/](https://experience.sap.com/fiori/)



</td>
</tr>
<tr>
<td valign="top">

SAP Fiori launchpad



</td>
<td valign="top">

SAP Fiori launchpad is a shell that hosts SAP Fiori apps, and provides the apps with services such as navigation, personalization, embedded support, and application configuration.



</td>
<td valign="top">

SAP Fiori



</td>
<td valign="top">

[http://help.sap.com/fiori](http://help.sap.com/fiori)



</td>
</tr>
<tr>
<td valign="top">

event



</td>
<td valign="top">

An **event** has a name as well as any number of parameters. The element's API offers support to manage event subscriptions.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Essentials](Essentials_ec699e0.md)



</td>
</tr>
<tr>
<td valign="top">

JAWS Screen Reader



</td>
<td valign="top">

*JAWS, Job Access With Speech, is the world's most popular screen reader, developed for computer users whose vision loss prevents them from seeing screen content or navigating with a mouse. JAWS provides speech and Braille output for the most popular computer applications on your PC.*



</td>
<td valign="top">

Freedom Scientific



</td>
<td valign="top">

[Freedom Scientific JAWS](http://www.freedomscientific.com/Products/Blindness/JAWS)



</td>
</tr>
<tr>
<td valign="top">

jQuery



</td>
<td valign="top">

JavaScript library that is packaged with OpenUI5.

*jQuery is a fast, small, and feature-rich JavaScript library. It makes things like HTML document traversal and manipulation, event handling, animation, and Ajax much simpler with an easy-to-use API that works across a multitude of browsers.* \(Quote from jquery.com\)



</td>
<td valign="top">

`jquery.com`



</td>
<td valign="top">

[jQuery Home Page](https://jquery.com/)



</td>
</tr>
<tr>
<td valign="top">

library



</td>
<td valign="top">

The top-level structural unit is called a **library**. Libraries are the master artifacts in the extensibility concept. They bundle a set of controls and related types and make them consumable by Web applications. There are predefined and standard libraries, like `sap.m`, with many commonly used controls. At the same time, it treats custom UI libraries as first-class citizens, making it easy for you to write and use your own controls alongside the predefined ones.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Essentials](Essentials_ec699e0.md)



</td>
</tr>
<tr>
<td valign="top">

mock server



</td>
<td valign="top">

A mock server is a mocking framework for HTTP and HTTPS that is used to simplify integration testing and to decouple development teams by allowing them to develop against a service that is incomplete or unstable. The mock server included with OpenUI5 mimics OData V2 back-end calls. Mock server functionality for OData V4 is included with CAP Node.js.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Mock Server](Mock_Server_69d3cbd.md)



</td>
</tr>
<tr>
<td valign="top">

model



</td>
<td valign="top">

Data provider for the application where the model instance is assigned to the UI and the controls are bound to the model. Various model types are available; the model type used depends on the data format available on the server side.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Models](Models_e1b6259.md)



</td>
</tr>
<tr>
<td valign="top">

MVC concept



</td>
<td valign="top">

A UI programming model that separates the layout \(view\) from the content \(model\) and the behavior \(controller\). The MVC concept is used by the framework to model the architecture of the applications.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Model View Controller \(MVC\)](Model_View_Controller_MVC_91f2334.md)



</td>
</tr>
<tr>
<td valign="top">

notepad control



</td>
<td valign="top">

A control that is defined on the fly without a library definition or running generation steps.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Developing Controls](Developing_Controls_8dcab00.md)



</td>
</tr>
<tr>
<td valign="top">

OData model



</td>
<td valign="top">

A model implementation for the Open Data \(OData\) Web Protocol format.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[OData V2 Model](OData_V2_Model_6c47b2b.md#loio6c47b2b39db9404582994070ec3d57a2)

[OData V4 Model](OData_V4_Model_5de13cf.md)



</td>
</tr>
<tr>
<td valign="top">

property



</td>
<td valign="top">

A **property** has a name and an associated data type. It has a well-defined default value expressed as a literal of that data type. Properties are accessible to application code via the element's API as getters and setters, but are also used by a control's renderer in a read-only way.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Essentials](Essentials_ec699e0.md)



</td>
</tr>
<tr>
<td valign="top">

SAPUI5 repository upload and download reports



</td>
<td valign="top">

Alternative for the team repository provider, with similar functionality.



</td>
<td valign="top">

SAPUI5 only



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

right-to-left \(RTL\) text directionality



</td>
<td valign="top">

*The `dir` attribute is used to set the base direction of text for display. It is essential for enabling HTML in right-to-left scripts such as Arabic, Hebrew, Syriac, and Thaana. Numerous different languages are written with these scripts, including Arabic, Hebrew, Pashto, Persian, Sindhi, Syriac, Dhivehi, Urdu, Yiddish, etc.* \(Quote from w3c.org\)



</td>
<td valign="top">

`w3c.org`



</td>
<td valign="top">

[HTML Text Directionality](http://www.w3.org/TR/html4/struct/dirlang.html)



</td>
</tr>
<tr>
<td valign="top">

resource model



</td>
<td valign="top">

Used to bind texts of a control to language-dependent resource bundle properties.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Resource Model](Resource_Model_91f122a.md#loio91f122a36f4d1014b6dd926db0e91070)



</td>
</tr>
<tr>
<td valign="top">

single SAPUI5 repository



</td>
<td valign="top">

The SAPUI5 ABAP repository consists of *n* single SAPUI5 repositories, each represented by an individual BSP application \(with specific characteristics\) in the BSP repository.



</td>
<td valign="top">

SAPUI5 only



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

SAP Fiori elements



</td>
<td valign="top">

App developers can use SAP Fiori elements to create SAP Fiori applications based on OData services and annotations requiring no JavaScript UI coding. An app based on SAP Fiori elements uses predefined template views and controllers that are provided centrally, so no application-specific view instances are required. The SAPUI5 runtime interprets metadata and annotations of the underlying OData service and creates the corresponding views for the SAP Fiori app at startup.

The predefined view templates and controllers ensure UI design consistency across similar apps. Additionally, the metadata-driven development model significantly reduces the amount of frontend code per app, so the developer can focus on the business logic.

SAP Fiori elements comprise templates for "List Report", "Object Page", and "Overview Page".



</td>
<td valign="top">

SAPUI5 only



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

scalable vector graphics \(SVG\)



</td>
<td valign="top">

*SVG is a markup language for describing two-dimensional graphics applications and images, and a set of related graphics script interfaces* \(Quote from w3c.org\)



</td>
<td valign="top">

`w3c.org`



</td>
<td valign="top">

[W3C SVG](https://www.w3.org/Graphics/SVG/)



</td>
</tr>
<tr>
<td valign="top">

synchronous \(sync\) processing



</td>
<td valign="top">

Synchronous processing will keep the current browser thread until the task is finished. The UI is not updated and no other tasks can be done in parallel. Consider using asynchronous processing for loading files and executing long-running code.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

SAPUI5 text repository



</td>
<td valign="top">

Part of the SAPUI5 ABAP repository; only to be used as a fallback mechanism if translation using properties files is not possible



</td>
<td valign="top">

SAPUI5 only



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

view



</td>
<td valign="top">

An application unit containing the control definitions for the user interface layer in the application, or in other words: defines how the user interface looks like.



</td>
<td valign="top">

SAPUI5/OpenUI5



</td>
<td valign="top">

[Views](Views_91f27e3.md)



</td>
</tr>
</table>

