<!-- loio91f292806f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f292806f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f292806f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f292806f4d1014b6dd926db0e91070)</div>

## XML View

The XML view type is defined in an XML file. The file name either ends with `.view.xml` or as an XML string. The file name and the folder structure together specify the name of the view that equals the OpenUI5 module name.

> Note:
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
> 
> 

Nest the XML tags analogous to the nesting sequence of OpenUI5 controls and add the property values as attributes \(see [Namespaces in XML Views](Namespaces_in_XML_Views_2421a2c.md)\).

Each control or element is represented by an XML tag with the name the control. If you, for example, want to create an instance of a `sap.m.Button`, you use tag `<Button>` with namespace `sap.m`. You can create a context binding for the control by using attribute `obejctBinding` or `Binding`. For more information, see [Context Binding \(Element Binding\)](Context_Binding_(Element_Binding)_91f05e8.md).

**Related information**  


[API Reference: `sap.ui.html.xmlview`](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.xmlview)

