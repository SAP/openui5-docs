<!-- loio91f393916f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f393916f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f393916f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f393916f4d1014b6dd926db0e91070)</div>

## Writing a Control Renderer

OpenUI5 provides three classes for control rendering: `sap.ui.core.Control`, `sap.ui.core.RenderManager`, and `sap.ui.core.Renderer`.

***

<a name="loio91f393916f4d1014b6dd926db0e91070__section_B946B1C4760F4A619D34055C49017F77"/>

### Control Class \(`sap.ui.core.Control`\)

The control class contains the control for rendering. A control consists of properties, events, aggregations, associations, and methods. They define the behavior of the control. The appearance and data of the control is determined by properties, associations, and aggregations. The `get...` methods of the control are used to access this information during the execution of the `render()` method:

-   Accessing properties:

    ``` js
    
    // var oValue = oControl.get<Property>();
    // for example for the 'text'-property
    var oValue = oControl.getText();
    ```

-   Accessing 1..1 aggregations

    ``` js
    
    // var oAggregation = oControl.get<Aggregation>();
    // for example for content-aggregation
    var oAggregation = oControl.getContent();
    ```

-   Accessing 1..n aggregrations:

    ``` js
    
    // var aAggregations = oControl.get<Aggregation>s();
    // for example for rows-aggregation
    var aAggregations = oControl.getRows();
    ```

-   Accessing associations:

    ``` js
    
    // var sAssociatedControlId = oControl.get<Association>();
    // for example labelFor-association
    var sAssociatedControlId = oControl.getLabelFor();
    ```


***

<a name="loio91f393916f4d1014b6dd926db0e91070__section_EE2A2957C19D4C6DA8E0AE811D87623A"/>

### RenderManager Class \(`sap.ui.core.RenderManager`\)

The render manager class collects pieces of HTML and injects the generated markup into the DOM. The `RenderManager` determines and loads the corresponding renderer and delegates the control rendering to the renderer. The `RenderManager` also provides, amongst others, the following helper functions for rendering:

|Method|Description|
|------|-----------|
|`write()`|Writes string information to the HTML|
|`writeControlData()` |Writes the ID and the recognition data of the control to the HTML|
|`renderControl()` |Converts the specified control into HTML representation and adds it to the HTML; used for rendering child controls|

For more information, see [sap.ui.core.RenderManager](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.RenderManager.html).

***

<a name="loio91f393916f4d1014b6dd926db0e91070__section_A9C3AEFF8AC94677BAE58BFF59FAE84A"/>

### Renderer Class \(`sap.ui.core.Renderer`\)

The renderer class is the base class for control renderers. The `Renderer` implements the static `render` method that is called when a control is added to the DOM. To render a control, the `RenderManager` executes the `render` method on the corresponding `Renderer` of the respective control and passes the reference to itself and to the control.

For notepad controls, the renderer class is normally not directly used, the "renderer" method is directly part of the control implementation and will be added to a renderer class behind the scenes.

**Related information**  


[Prevention of Cross-site Scripting](Prevention_of_Cross-site_Scripting_4de64e2.md)

