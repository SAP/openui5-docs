<!-- loio5531aef1adc8462392a5b8fe1178606e -->

| loio |
| -----|
| 5531aef1adc8462392a5b8fe1178606e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5531aef1adc8462392a5b8fe1178606e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5531aef1adc8462392a5b8fe1178606e)</div>

## What's New in OpenUI5 1.68

With this release OpenUI5 is upgraded from version 1.67 to 1.68.

***

<a name="loio5531aef1adc8462392a5b8fe1178606e__section_yxw_pxt_zcb"/>

### New Features

| **Format Option `parseKeepsEmptyString`** The format option `parseKeepsEmptyString` for `sap.ui.model.odata.type.String` is now available. This format option is set to `true` by `sap.ui.model.odata.v4.AnnotationHelper.format`, this means, the changed behavior applies automatically if templating is used with `v4.AnnotationHelper.format`.|
| **New Semantic Rendering With `RenderManager`** The `RenderManager` class provides a new way of semantic rendering for controls. It allows for an easier and more efficient type of rendering by updating only the required parts of the DOM structure and no longer requires any plain JavaScript updates in the custom setters of the controls. To enable this type of rendering, set the `apiVersion` property of the control renderer to *2*. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.RenderManager). |
|`**sap.ui.integration.widgets.Card**`Using our newly developed tool - Card Explorer - you can explore and learn more about the UI Integration Cards. You can find the Card Explorer in the tool section of the Demo Kit. ![](loio2bcad31f5feb43f58aaa93271a469e0f_LowRes.png) For more information, see [Card Explorer](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/index.html).|

***

<a name="loio5531aef1adc8462392a5b8fe1178606e__section_qwl_pb5_zcb"/>

### Improved Features

| **OpenUI5 OData V4 Model** The new version of the OpenUI5 OData V4 model introduces the following features: -   Overloads of bound functions are now supported if the same function name is used for different binding parameter types.

-   The original error or unbound message is now available as `technicalDetails.originalMessage` in the Message in the message model. This can be used to transport additional information.

-   It is now possible to use `auto-$expand/$select` with value help models by setting parameter `bAutoExpandSelect` of method `requestValueListInfo` of the `v4.ODataPropertyBinding` or the `v4.ODataMetaModel` respectively.


 > Note:
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing freestyle and Fiori elements applications. Double check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).
> 
> 

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).|

***

<a name="loio5531aef1adc8462392a5b8fe1178606e__section_rqn_wd5_zcb"/>

### Improved Controls

| **`sap.f.DynamicPage`** You can now change the background color of the `DynamicPage` control by using the new `backgroundDesign` property.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPage). |
|**`sap.f.GridContainer` \(Experimental\)**We have enhanced the drag and drop functionality. With the new version, we introduced a drop indicator that mimics the size of the dragged item and shows the potential drop position inside the grid. The indicator pushes away other grid items, showing the correct arrangement calculated by the grid’s auto-placement algorithm. The API for the enhanced drag and drop is consistent with the default drag and drop API. This allows you to configure complex behavior. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainerDragAndDrop).|
| **`sap.m.DatePicker`** The options displayed in the picker now depend on the display format. For example, if the set `displayFormat` is `MM-y` or `yyyy`, the picker directly displays years with months or only years and the user no longer needs to select a specific day.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.DatePicker/sample/sap.m.sample.DatePicker). |
|**`sap.m.SelectDialog`, `sap.m.TableSelectDialog`**Application developers can now customize the text of the confirmation button for the controls. If no specific value is set, the text of the button is set to `Select`. For more information, see the API Reference \([sap.m.SelectDialog](https://openui5.hana.ondemand.com/#/api/sap.m.SelectDialog), [sap.m.TableSelectDialog](https://openui5.hana.ondemand.com/#/api/sap.m.TableSelectDialog)\).|
|**`sap.m.SelectDialog`**We have introduced a new API method called `clearSelection` that allows removing all selections from the `sap.m.SelectDialog` and its internally used list \(`sap.m.List`\). For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SelectDialog) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.SelectDialog).|

***

<a name="loio5531aef1adc8462392a5b8fe1178606e__section_r5v_3h5_zcb"/>

### Demo Kit Improvements

| **API Reference** To improve the visualization of borrowed *Properties*, *Aggregations*, and *Associations*, we added a checkbox that enables you to switch them on and off. Initially, the borrowed entities aren't displayed.  ![](loio33559e63a1064c56969fabd0e43426d8_HiRes.gif) 

 |
| **Web Page Title** The web page title is now updated dynamically to reflect the currently open tab. The differentiation is between the main pages of the Demo Kit app – *Documentation*, *API Reference*, *Samples*, *Demo Apps*, and *Tools*.|

