<!-- loio91f292806f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f292806f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f292806f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f292806f4d1014b6dd926db0e91070)</div>

## XML View

The XML view type is defined in an XML file. The file name either ends with `.view.xml` or as an XML string. The file name and the folder structure together specify the name of the view that equals the OpenUI5 module name.

> ### Example:  
> For `resources/sap/hcm/Address.view.xml`, the view name is `sap.hcm.Address`. The application uses this view name for displaying an instance of this view. If you define the XML view by means of an XML string, no file or define/require is needed.
> 
> The file looks as follows:
> 
> ``` xml
> 
> <mvc:View controllerName="sap.hcm.Address" xmlns="sap.m" xmlns:mvc="sap.ui.core.mvc">
>    <Panel>
>       <Image src="http://www.sap.com/global/ui/images/global/sap-logo.png"/>
>       <Button text="Press Me!"/>
>    </Panel>
> </mvc:View>
> ```

Nest the XML tags analogous to the nesting sequence of OpenUI5 controls and add the property values as attributes \(see [Namespaces in XML Views](Namespaces_in_XML_Views_2421a2c.md)\).

Each control or element is represented by an XML tag with the name of the control. If you, for example, want to create an instance of a `sap.m.Button`, you use the `<Button>` tag with the `sap.m` namespace. You can create a context binding for the control by using the `objectBinding` or `binding` attributes. For more information, see [Context Binding \(Element Binding\)](Context_Binding_Element_Binding_91f05e8.md).

-   **[Namespaces in XML Views](Namespaces_in_XML_Views_2421a2c.md "The names of the OpenUI5 control libraries and the related subpackages are mapped to XML
		namespaces.")**  
The names of the OpenUI5 control libraries and the related subpackages are mapped to XML namespaces.
-   **[Aggregation Handling in XML Views](Aggregation_Handling_in_XML_Views_19eabf5.md "In XML views, aggregated child controls can be added as child tags. ")**  
In XML views, aggregated child controls can be added as child tags.
-   **[Control Properties and Associations in XML Views](Control_Properties_and_Associations_in_XML_Views_5ee3be4.md "")**  

-   **[Using Native HTML in XML Views](Using_Native_HTML_in_XML_Views_be54950.md "The use of native HTML in XML views depends on the XHTML feature set.")**  
The use of native HTML in XML views depends on the XHTML feature set.
-   **[Using CSS Style Sheets in XML Views](Using_CSS_Style_Sheets_in_XML_Views_b564935.md "Style sheets are included in XML views in the same way as plain HTML. To add further
		CSS classes to OpenUI5 controls,
		use the class attribute.")**  
Style sheets are included in XML views in the same way as plain HTML. To add further CSS classes to OpenUI5 controls, use the `class` attribute.
-   **[Handling Events in XML Views](Handling_Events_in_XML_Views_b0fb4de.md "XML views use event handlers as attributes: The attribute name is the event name, such
		as &quot;press&quot; for a button, and the attribute value is the event handler name.")**  
XML views use event handlers as attributes: The attribute name is the event name, such as "press" for a button, and the attribute value is the event handler name.
-   **[Preprocessing XML Views](Preprocessing_XML_Views_48b81b9.md "Applying preprocessing to views enables you to use features like XML templating. This
		feature is currently only enabled for XML views. On an abstract level, preprocessing means
		that a view can be modified during runtime before it is rendered. This makes it possible to
		use the templating syntax, as it is interpreted by the preprocessor. It also makes it
		possible to apply user customization.")**  
Applying preprocessing to views enables you to use features like XML templating. This feature is currently only enabled for XML views. On an abstract level, preprocessing means that a view can be modified during runtime before it is rendered. This makes it possible to use the templating syntax, as it is interpreted by the preprocessor. It also makes it possible to apply user customization.
-   **[XML View Cache](XML_View_Cache_3d85d5e.md "To be able to speed up processing times of XML views that make heavy use of the preprocessor feature, you can use the view cache to store its
		processed XML source. Then according network requests for the source and all preprocessor runs that modify the XML source are skipped and the source is
		taken from the cache.")**  
To be able to speed up processing times of XML views that make heavy use of the preprocessor feature, you can use the view cache to store its processed XML source. Then according network requests for the source and all preprocessor runs that modify the XML source are skipped and the source is taken from the cache.
-   **[Require Modules in XML View and Fragment](Require_Modules_in_XML_View_and_Fragment_b11d853.md "Modules can be required in XML views and fragments and assigned to aliases which can be
		used as variables in properties, event handlers, and bindings.")**  
Modules can be required in XML views and fragments and assigned to aliases which can be used as variables in properties, event handlers, and bindings.

**Related Information**  


[API Reference: `sap.ui.core.mvc.XMLView`](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.core.mvc.XMLView.create)

