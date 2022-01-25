<!-- loio91f27e3e6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f27e3e6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f27e3e6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f27e3e6f4d1014b6dd926db0e91070)</div>

## Views

The view in the Model-View-Controller \(MVC\) concept is responsible for defining and rendering the UI. OpenUI5 supports predefined view types.

The following predefined view types are available:

-   **XML view** \(file or string in XML format\); this type supports a mix of XML and plain HTML.

-   **JSON view** \(file or string in JSON format\)

-   **Typed view**, constructed in a programmatic manner

-   **HTML view** \(file or string in HTML format\)


> ### Note:  
> We recommend to use XML views, because XML views force a clear separation of the UI definition from the application logic \(which has to be implemented in the controller\). This makes the code more readable and easier to support.
> 
> Therefore, we concentrate on XML views and only provide examples for XML views throughout this documentation.

***

<a name="loio91f27e3e6f4d1014b6dd926db0e91070__section_fxz_jf5_y4b"/>

### Typed Views

A view can also be defined as a [typed view](Typed_View_e6bb33d.md), representing its own class.

> ### Note:  
> Typed views are available since OpenUI5 1.88

-   **[XML View](XML_View_91f2928.md "The XML view type is defined in an XML file. The file name either ends with
			.view.xml or as an XML string. The file name and the folder structure
		together specify the name of the view that equals the OpenUI5 module name. ")**  
The XML view type is defined in an XML file. The file name either ends with `.view.xml` or as an XML string. The file name and the folder structure together specify the name of the view that equals the OpenUI5 module name.
-   **[JSON View](JSON_View_91f2852.md "The JSON view type is defined in a file. The file name has to either end with
			.view.json or as a JSON string. The file name and the folder structure
		together specify the name of the view that equals the OpenUI5 module name within the
		modularization concept.")**  
The JSON view type is defined in a file. The file name has to either end with `.view.json` or as a JSON string. The file name and the folder structure together specify the name of the view that equals the OpenUI5 module name within the modularization concept.
-   **[Typed View](Typed_View_e6bb33d.md "A view can also be defined by extending the sap.ui.core.mvc.View class. Such a view is referred to as a typed view. This
		means the view definition represents its own view class.")**  
A view can also be defined by extending the `sap.ui.core.mvc.View` class. Such a view is referred to as a typed view. This means the view definition represents its own view class.
-   **[HTML View](HTML_View_9756f47.md "An HTML View is defined by declarative HTML. Like the declarative support, the HTML
		view supports embedded HTML. The view file ends with view.html, for example
			myview.view.html.")**  
An HTML View is defined by declarative HTML. Like the declarative support, the HTML view supports embedded HTML. The view file ends with `view.html`, for example `myview.view.html`.
-   **[Instantiating Views](Instantiating_Views_68d0e58.md "To instantiate views asychronously, OpenUI5 provides the factory
		method View.create defined in module
		sap/ui/core/mvc/View.")**  
To instantiate views asychronously, OpenUI5 provides the factory method `View.create` defined in module `sap/ui/core/mvc/View`.
-   **[View Cloning](View_Cloning_a575619.md "For normal controls, view cloning bases on control settings that are described by OpenUI5 metadata, such as
		properties, aggregations, associations, and event handlers. The clone operation collects
		these settings and creates a new instance.")**  
For normal controls, view cloning bases on control settings that are described by OpenUI5 metadata, such as properties, aggregations, associations, and event handlers. The clone operation collects these settings and creates a new instance.

**Related Information**  


[API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.mvc.View)

