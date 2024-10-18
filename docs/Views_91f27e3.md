<!-- loio91f27e3e6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f27e3e6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/91f27e3e6f4d1014b6dd926db0e91070) | [demo kit latest release](https://sdk.openui5.org/topic/91f27e3e6f4d1014b6dd926db0e91070)</div>

## Views

The view in the Model-View-Controller \(MVC\) concept is responsible for defining and rendering the UI. OpenUI5 supports predefined view types.

The following predefined view types are available:

-   **XML view**, a file or string in XML format

-   **Typed view**, constructed in a programmatic manner


> ### Note:  
> We recommend using XML views unless you need the dynamics possible by the programmatic nature of Typed Views. The declarative approach used by XML views comes with many benefits; for example, the code is often more readable and easier to support.
> 
> Throughout this documentation, the code examples mainly use XML views.

-   **[XML View](XML_View_91f2928.md "The XML view type is defined in an XML file, with a file name ending in .view.xml. The file name and the folder structure
		together specify the name of the view that equals the OpenUI5 module name. ")**  
The XML view type is defined in an XML file, with a file name ending in `.view.xml`. The file name and the folder structure together specify the name of the view that equals the OpenUI5 module name.
-   **[Typed View](Typed_View_e6bb33d.md "A view can also be defined by extending the sap.ui.core.mvc.View class. Such a view is referred to as a typed view. This
		means the view definition represents its own view class.")**  
A view can also be defined by extending the `sap.ui.core.mvc.View` class. Such a view is referred to as a typed view. This means the view definition represents its own view class.
-   **[Instantiating Views](Instantiating_Views_68d0e58.md "To instantiate views asychronously, OpenUI5 provides the factory
		method View.create defined in module
		sap/ui/core/mvc/View.")**  
To instantiate views asychronously, OpenUI5 provides the factory method `View.create` defined in module `sap/ui/core/mvc/View`.
-   **[JSON View \(deprecated\)](JSON_View_deprecated_91f2852.md "The JSON view type is defined in a file. The file name has to either end with .view.json or as a JSON string. The file
		name and the folder structure together specify the name of the view that equals the OpenUI5 module name within the modularization concept.")**  
The JSON view type is defined in a file. The file name has to either end with `.view.json` or as a JSON string. The file name and the folder structure together specify the name of the view that equals the OpenUI5 module name within the modularization concept.
-   **[View Cloning \(deprecated\)](View_Cloning_deprecated_a575619.md "For normal controls, view cloning bases on control settings that are described by OpenUI5 metadata, such as
		properties, aggregations, associations, and event handlers. The clone operation collects
		these settings and creates a new instance.")**  
For normal controls, view cloning bases on control settings that are described by OpenUI5 metadata, such as properties, aggregations, associations, and event handlers. The clone operation collects these settings and creates a new instance.

**Related Information**  


[API Reference](https://sdk.openui5.org/api/sap.ui.core.mvc.View)

