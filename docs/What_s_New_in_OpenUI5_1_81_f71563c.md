<!-- loiof71563ccd2294cf0a59d16b62be0f7eb -->

| loio |
| -----|
| f71563ccd2294cf0a59d16b62be0f7eb |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/f71563ccd2294cf0a59d16b62be0f7eb) | [demo kit latest release](https://sdk.openui5.org/topic/f71563ccd2294cf0a59d16b62be0f7eb)</div>

## What's New in OpenUI5 1.81

With this release OpenUI5 is upgraded from version 1.80 to 1.81.

***

<a name="loiof71563ccd2294cf0a59d16b62be0f7eb__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td valign="top">

**Consuming SAP Icon Font in a Non-UI5 Environment**

You can now consume the predefined `SAP-icons` icon font in an environment where OpenUI5 isn't available. An example for integration is given [here](Icon_and_Icon_Pool_21ea0ea.md#loio21ea0ea94614480d9a910b2e93431291__section_whp_y2l_mmb).



</td>
</tr>
<tr>
<td valign="top">

**Incompatible jQuery Security Fix**

We have added a jQuery security fix to OpenUI5, which may introduce incompatibilities to existing application or library code.

For checking and, if required, fixing your applications and libraries, see [these instructions](https://github.com/SAP/openui5/blob/master/docs/self_closing_tags_fix_instructions.md).



</td>
</tr>
<tr>
<td valign="top">

**Special URL Prefixes in App Descriptor**

Inside the app descriptor, you can now use special URLs prefixed with `ui5://`. These URLs are resolved automatically during component startup, before any models are created.

One common use case is the resolution of local annotation files. By default the local annotation files are resolved relative to the manifest. When using a `ui5://` URL, you can enforce a different resolution, for example to a server-absolute URL.

Find more details about the usage of such URL prefixes and an example in the [documentation](Descriptor_for_Applications_Components_and_Libraries_manifest_json_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__section_rmc_3xj_mmb).



</td>
</tr>
</table>

***

<a name="loiof71563ccd2294cf0a59d16b62be0f7eb__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

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

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.



</td>
</tr>
</table>

***

<a name="loiof71563ccd2294cf0a59d16b62be0f7eb__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.f.GridContainer`**

We have enhanced the keyboard handling capabilities of the Grid Container. You can now navigate to the item below or above using the [Down Arrow\] and [Up Arrow\]. If you reach any of the borders of the Grid Container, the `borderReached` event will be fired.

You can now perform drag-and-drop operations using  [Ctrl\] + [Arrow Keys\]  simultaneously. If your Grid Container is configured for drag and drop \(has `sap.ui.core.dnd.DropInfo` and `sap.f.dnd.GridDragInfo`\), then you will receive similar events as if you were dragging with a mouse.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.GridContainer%23methods/focusItem) and the [Sample](https://sdk.openui5.org/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainerDragAndDrop).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Button`**

Visualization of shortcut hints on focus and hover is now available. For example,  [Ctrl\] + [S\]  is displayed for the Save button to help the user to find the correct shortcut. This is done by adding a command to a button. This new feature is available for the standalone `sap.m.Button` as well as for composite controls like `sap.ui.comp.smarttable.SmartTable` and `sap.ui.comp.smartfilterbar.SmartFilterBar`. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.core.sample.Commands/sample/sap.ui.core.sample.Commands).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.DatePicker`, `sap.m.DateTimePicker`, and `sap.m.TimePicker`**

We have aligned the visualization of the full-screen dialog in mobile view for these controls.



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.MessageView`**

The grouping functionality in the `sap.m.MessageView` shows the messages in the order they were added to the control, or provided in the model. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MessageView). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.PlanningCalendar`**

-   We have introduced the option to add a third text row and multiple alternatives to display the appointment text. The third text row is available using the new `description` property of the `sap.ui.unified.CalendarAppointment` control. To specify the display of the appointment text, you can use the new `appointmentHeight` property of `sap.m.PlanningCalendar`.
-   The new `appointmentRoundWidth` \(experimental\) property allows developers to avoid cell overlapping by rounding \(up or down\) the width of the appointments by half of a column. The `appointmentRoundWidth` has preset values `HalfColumn` or `None` \(default\) and can only be applied when the calendar interval type is `day` and the view shows more than 20 days.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar%23controlProperties) and the [Sample](https://sdk.openui5.org/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarAppointmentSizes).



</td>
</tr>
<tr>
<td valign="top">

<code><b>sap.ui.integration.widgets.Card</b></code>

-   Developers who are defining data requests in `sap.ui.integration.Extension` \(Experimental\) can now specify the content type of the data in the expected response \(XML along JSON are supported\). You do this by using the `dataType` property of the `request` object. For more information, see the [Card Extension](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/extension) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/gettingData) in the Card Explorer.
-   We have added support for the text badge \(experimental\), which can be used to display concise and important information that attracts the user's attention. Typical usage of the text badge is, for example, to show a new card in the user’s home page. For more information, see the [Text Badge](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/badge) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/badge) in the Card Explorer.
-   We have introduced a new `visible` property in the manifest for the Table Card and the Object Card, to allow the card author to dynamically control the visibility of the columns in the Table Card and visibility of the groups and group items of the Object Card. For more information, see the [Table Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/table) section and the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/object) sections in the Card Explorer.
-   The Adaptive Cards are no longer in experimental state. We have also added an example of how to use the extension mechanism of the Adaptive Cards.For more information, see the [Adaptive Cards](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) section and the [Submit with Extension](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/extension) sample in the Card Explorer.



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.unified.Calendar`**

We have added a new property to the `DateTypeRange` class, called `secondaryType`. It allows developers to set any special day as a non-working day, using a single object. This new property is of type `CalendarDayType` and accepts only `None` and `NonWorkingDay` values, which can be combined with other `CalendarDayType` objects. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.DateTypeRange).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.unified.FileUploader`**

We have added a new `httpRequestMethod` \(experimental\) property to enable the file upload with both HTTP POST and HTTP PUT request methods according to the data service requirements. This new property accepts enumeration of type `sap.ui.unified.FileUploaderHttpRequestMethod`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.FileUploader).



</td>
</tr>
</table>

***

<a name="loiof71563ccd2294cf0a59d16b62be0f7eb__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td valign="top">

**Samples**

We have added a new *Pattern* category in the *Samples* section of the Demo Kit app. The samples added in this category aim to improve the representation of more complex scenarios, such as layouts and floorplans.

![](images/loio5004e443d73749a48ba7926a0c0d6f69_HiRes.png)



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.101](What_s_New_in_OpenUI5_1_101_5a18410.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](What_s_New_in_OpenUI5_1_100_5deb78f.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](What_s_New_in_OpenUI5_1_99_5e35c25.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](What_s_New_in_OpenUI5_1_98_7aacb4e.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](What_s_New_in_OpenUI5_1_97_f21858f.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](What_s_New_in_OpenUI5_1_96_b39a11b.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](What_s_New_in_OpenUI5_1_95_1b09465.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What_s_New_in_OpenUI5_1_94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What_s_New_in_OpenUI5_1_93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What_s_New_in_OpenUI5_1_92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What_s_New_in_OpenUI5_1_91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What_s_New_in_OpenUI5_1_90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What_s_New_in_OpenUI5_1_89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What_s_New_in_OpenUI5_1_88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_e315108.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What_s_New_in_OpenUI5_1_86_067e2fb.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What_s_New_in_OpenUI5_1_85_eeb5bd9.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What_s_New_in_OpenUI5_1_84_ccf76b7.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What_s_New_in_OpenUI5_1_82_f081cf0.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_3294c68.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_edf8e35.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_d176be3.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_2ec6b6b.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_b9b0a3f.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_dc3d3ce.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_21fc6cb.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_7b82664.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_25e5326.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_609fd01.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_4e89fee.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_41203fd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_5531aef.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_0968958.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_ebe7fda.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_9d2b189.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What_s_New_in_OpenUI5_1_64_1975e30.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_77e1dcc.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What_s_New_in_OpenUI5_1_62_27eea38.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What_s_New_in_OpenUI5_1_61_de4d50b.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_2a70354.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_b28edde.md "With this release, OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_53b4b5e.md "With this release, OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_f29023e.md "With this release, OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_a09dd79.md "With this release, OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_a844984.md "With this release, OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_2818f80.md "With this release, OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_4cf0986.md "With this release, OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_4768f1a.md "With this release, OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

