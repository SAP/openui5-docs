<!-- loiof71563ccd2294cf0a59d16b62be0f7eb -->

| loio |
| -----|
| f71563ccd2294cf0a59d16b62be0f7eb |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f71563ccd2294cf0a59d16b62be0f7eb) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f71563ccd2294cf0a59d16b62be0f7eb)</div>

## What's New in OpenUI5 1.81

With this release OpenUI5 is upgraded from version 1.80 to 1.81.

***

<a name="loiof71563ccd2294cf0a59d16b62be0f7eb__section_yxw_pxt_zcb"/>

### New Features

|**Consuming SAP Icon Font in a Non-UI5 Environment**

You can now consume the predefined `SAP-icons` icon font in an environment where OpenUI5 isn't available. An example for integration is given [here](Icon_and_Icon_Pool_21ea0ea.md#loio21ea0ea94614480d9a910b2e93431291__section_whp_y2l_mmb).

|
|**Incompatible jQuery Security Fix**

We have added a jQuery security fix to OpenUI5, which may introduce incompatibilities to existing application or library code.

For checking and, if required, fixing your applications and libraries, see [these instructions](https://github.com/SAP/openui5/blob/master/docs/self_closing_tags_fix_instructions.md).

|
|**Special URL Prefixes in App Descriptor**

Inside the app descriptor, you can now use special URLs prefixed with `ui5://`. These URLs are resolved automatically during component startup, before any models are created.

One common use case is the resolution of local annotation files. By default the local annotation files are resolved relative to the manifest. When using a `ui5://` URL, you can enforce a different resolution, for example to a server-absolute URL.

Find more details about the usage of such URL prefixes and an example in the [documentation](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__section_rmc_3xj_mmb).

|

***

<a name="loiof71563ccd2294cf0a59d16b62be0f7eb__section_qwl_pb5_zcb"/>

### Improved Features

|**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The following methods are now public:
    -   `sap.ui.model.odata.v4.ODataListBinding#getGroupId`,
    -   `sap.ui.model.odata.v4.ODataListBinding#getUpdateGroupId`,
    -   `sap.ui.model.odata.v4.ODataContextBinding#getGroupId`,
    -   `sap.ui.model.odata.v4.ODataContextBinding#getUpdateGroupId`,
    -   `sap.ui.model.odata.v4.ODataPropertyBinding#getGroupId`,
    -   `sap.ui.model.odata.v4.ODataPropertyBinding#getUpdateGroupId`,
    -   `sap.ui.model.odata.v4.ODataMetaModel#getMetaPath`.
-   The `requestUI5Type` and `getUI5Type` methods now have an additional parameter to pass any format options to be taken into account.
-   You can now use the `sap.ui.model.odata.v4.Context#requestSideEffects` method on bindings with the `$$aggregation` binding parameter.
-   We have introduced the new `sap.ui.model.odata.v4.Context#setKeepAlive` method for row contexts of list bindings. With this new method, you can extend the lifetime of the context, so that it does not get destroyed when the corresponding entity is no longer part of the list, for example, due to filtering or sorting of the list. Note that the `refresh`, `requestSideEffects`, and `delete` methods are currently not supported for kept-alive contexts.
-   The OData V4 model now supports the `metadataUrlParams` parameter. The `sap-context-token` URL parameter can only be used for the request of the root metadata.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

|

***

<a name="loiof71563ccd2294cf0a59d16b62be0f7eb__section_rqn_wd5_zcb"/>

### Improved Controls

|**`sap.f.GridContainer`**

We have enhanced the keyboard handling capabilities of the Grid Container. You can now navigate to the item below or above using the [Down Arrow\] and [Up Arrow\]. If you reach any of the borders of the Grid Container, the `borderReached` event will be fired.

You can now perform drag-and-drop operations using  [Ctrl\] + [Arrow Keys\]  simultaneously. If your Grid Container is configured for drag and drop \(has `sap.ui.core.dnd.DropInfo` and `sap.f.dnd.GridDragInfo`\), then you will receive similar events as if you were dragging with a mouse.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer%23methods/focusItem) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainerDragAndDrop).

|
|**`sap.m.Button`**

Visualization of shortcut hints on focus and hover is now available. For example,  [Ctrl\] + [S\]  is displayed for the Save button to help the user to find the correct shortcut. This is done by adding a command to a button. This new feature is available for the standalone `sap.m.Button` as well as for composite controls like `sap.ui.comp.smarttable.SmartTable` and `sap.ui.comp.smartfilterbar.SmartFilterBar`. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.core.sample.Commands/sample/sap.ui.core.sample.Commands).

|
|**`sap.m.DatePicker`, `sap.m.DateTimePicker`, and `sap.m.TimePicker`**

We have aligned the visualization of the full-screen dialog in mobile view for these controls.

|
|**`sap.m.MessageView`**

The grouping functionality in the `sap.m.MessageView` shows the messages in the order they were added to the control, or provided in the model. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.MessageView). 

|
|**`sap.m.PlanningCalendar`**

-   We have introduced the option to add a third text row and multiple alternatives to display the appointment text. The third text row is available using the new `description` property of the `sap.ui.unified.CalendarAppointment` control. To specify the display of the appointment text, you can use the new `appointmentHeight` property of `sap.m.PlanningCalendar`.
-   The new `appointmentRoundWidth` \(experimental\) property allows developers to avoid cell overlapping by rounding \(up or down\) the width of the appointments by half of a column. The `appointmentRoundWidth` has preset values `HalfColumn` or `None` \(default\) and can only be applied when the calendar interval type is `day` and the view shows more than 20 days.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar%23controlProperties) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarAppointmentSizes).

|
|`**sap.ui.integration.widgets.Card**`

-   Developers who are defining data requests in `sap.ui.integration.Extension` \(Experimental\) can now specify the content type of the data in the expected response \(XML along JSON are supported\). You do this by using the `dataType` property of the `request` object. For more information, see the [Card Extension](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/extension) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/gettingData) in the Card Explorer.
-   We have added support for the text badge \(experimental\), which can be used to display concise and important information that attracts the user's attention. Typical usage of the text badge is, for example, to show a new card in the user’s home page. For more information, see the [Text Badge](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/badge) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/badge) in the Card Explorer.
-   We have introduced a new `visible` property in the manifest for the Table Card and the Object Card, to allow the card author to dynamically control the visibility of the columns in the Table Card and visibility of the groups and group items of the Object Card. For more information, see the [Table Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/table) section and the [Object Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/object) sections in the Card Explorer.
-   The Adaptive Cards are no longer in experimental state. We have also added an example of how to use the extension mechanism of the Adaptive Cards.For more information, see the [Adaptive Cards](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) section and the [Submit with Extension](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/extension) sample in the Card Explorer.

|
|**`sap.ui.unified.Calendar`**

We have added a new property to the `DateTypeRange` class, called `secondaryType`. It allows developers to set any special day as a non-working day, using a single object. This new property is of type `CalendarDayType` and accepts only `None` and `NonWorkingDay` values, which can be combined with other `CalendarDayType` objects. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.unified.DateTypeRange).

|
|**`sap.ui.unified.FileUploader`**

We have added a new `httpRequestMethod` \(experimental\) property to enable the file upload with both HTTP POST and HTTP PUT request methods according to the data service requirements. This new property accepts enumeration of type `sap.ui.unified.FileUploaderHttpRequestMethod`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.unified.FileUploader).

|

***

<a name="loiof71563ccd2294cf0a59d16b62be0f7eb__section_r5v_3h5_zcb"/>

### Demo Kit Improvements

|**Samples**

We have added a new *Pattern* category in the *Samples* section of the Demo Kit app. The samples added in this category aim to improve the representation of more complex scenarios, such as layouts and floorplans.

![](loio5004e443d73749a48ba7926a0c0d6f69_HiRes.png)

|

