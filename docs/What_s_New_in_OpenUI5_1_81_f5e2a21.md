<!-- loiof5e2a21dd36d4b81a12ad30f5d5db20e -->

| loio |
| -----|
| f5e2a21dd36d4b81a12ad30f5d5db20e |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/f5e2a21dd36d4b81a12ad30f5d5db20e) | [demo kit latest release](https://sdk.openui5.org/topic/f5e2a21dd36d4b81a12ad30f5d5db20e)</div>

## What's New in OpenUI5 1.81

With this release OpenUI5 is upgraded from version 1.80 to 1.81.

***

****


<table>
<tr>
<th valign="top">

Version

</th>
<th valign="top">

Type

</th>
<th valign="top">

Category

</th>
<th valign="top">

Title

</th>
<th valign="top">

Description

</th>
<th valign="top">

Action

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Consuming SAP Icon Font in a Non-UI5 Environment** 

</td>
<td valign="top">

**Consuming SAP Icon Font in a Non-UI5 Environment**

You can now consume the predefined `SAP-icons` icon font in an environment where OpenUI5 isn't available. An example for integration is given [here](Icon_and_Icon_Pool_21ea0ea.md#loio21ea0ea94614480d9a910b2e93431291__section_whp_y2l_mmb).

<sub>New•Feature•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Incompatible jQuery Security Fix** 

</td>
<td valign="top">

**Incompatible jQuery Security Fix**

We have added a jQuery security fix to OpenUI5, which may introduce incompatibilities to existing application or library code.

For checking and, if required, fixing your applications and libraries, see [these instructions](https://github.com/SAP/openui5/blob/master/docs/self_closing_tags_fix_instructions.md).

<sub>New•Feature•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Special URL Prefixes in App Descriptor** 

</td>
<td valign="top">

**Special URL Prefixes in App Descriptor**

Inside the app descriptor, you can now use special URLs prefixed with `ui5://`. These URLs are resolved automatically during component startup, before any models are created.

One common use case is the resolution of local annotation files. By default the local annotation files are resolved relative to the manifest. When using a `ui5://` URL, you can enforce a different resolution, for example to a server-absolute URL.

Find more details about the usage of such URL prefixes and an example in the [documentation](Descriptor_for_Applications_Components_and_Libraries_manifest_json_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__section_rmc_3xj_mmb).

<sub>New•Feature•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V4 Model** 

</td>
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

<sub>Changed•Feature•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.GridContainer`** 

</td>
<td valign="top">

**`sap.f.GridContainer`**

We have enhanced the keyboard handling capabilities of the Grid Container. You can now navigate to the item below or above using the [Down Arrow\] and [Up Arrow\]. If you reach any of the borders of the Grid Container, the `borderReached` event will be fired.

You can now perform drag-and-drop operations using [Ctrl\] + [Arrow Keys\]  simultaneously. If your Grid Container is configured for drag and drop \(has `sap.ui.core.dnd.DropInfo` and `sap.f.dnd.GridDragInfo`\), then you will receive similar events as if you were dragging with a mouse.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.GridContainer%23methods/focusItem) and the [Sample](https://sdk.openui5.org/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainerDragAndDrop).

<sub>Changed•Control•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Button`** 

</td>
<td valign="top">

**`sap.m.Button`**

Visualization of shortcut hints on focus and hover is now available. For example, [Ctrl\] + [S\]  is displayed for the Save button to help the user to find the correct shortcut. This is done by adding a command to a button. This new feature is available for the standalone `sap.m.Button` as well as for composite controls like `sap.ui.comp.smarttable.SmartTable` and `sap.ui.comp.smartfilterbar.SmartFilterBar`. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.core.sample.Commands/sample/sap.ui.core.sample.Commands).

<sub>Changed•Control•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.DatePicker`, `sap.m.DateTimePicker`, and `sap.m.TimePicker`** 

</td>
<td valign="top">

**`sap.m.DatePicker`, `sap.m.DateTimePicker`, and `sap.m.TimePicker`**

We have aligned the visualization of the full-screen dialog in mobile view for these controls.

<sub>Changed•Control•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MessageView`** 

</td>
<td valign="top">

**`sap.m.MessageView`**

The grouping functionality in the `sap.m.MessageView` shows the messages in the order they were added to the control, or provided in the model. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MessageView).

<sub>Changed•Control•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`** 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`**

-   We have introduced the option to add a third text row and multiple alternatives to display the appointment text. The third text row is available using the new `description` property of the `sap.ui.unified.CalendarAppointment` control. To specify the display of the appointment text, you can use the new `appointmentHeight` property of `sap.m.PlanningCalendar`.
-   The new `appointmentRoundWidth` \(experimental\) property allows developers to avoid cell overlapping by rounding \(up or down\) the width of the appointments by half of a column. The `appointmentRoundWidth` has preset values `HalfColumn` or `None` \(default\) and can only be applied when the calendar interval type is `day` and the view shows more than 20 days.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar%23controlProperties) and the [Sample](https://sdk.openui5.org/entity/sap.m.PlanningCalendar/sample/sap.m.sample.PlanningCalendarAppointmentSizes).

<sub>Changed•Control•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`** 

</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   Developers who are defining data requests in `sap.ui.integration.Extension` \(Experimental\) can now specify the content type of the data in the expected response \(XML along JSON are supported\). You do this by using the `dataType` property of the `request` object. For more information, see the [Card Extension](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/extension) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/gettingData) in the Card Explorer.
-   We have added support for the text badge \(experimental\), which can be used to display concise and important information that attracts the user's attention. Typical usage of the text badge is, for example, to show a new card in the user’s home page. For more information, see the [Text Badge](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/badge) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/badge) in the Card Explorer.
-   We have introduced a new `visible` property in the manifest for the Table Card and the Object Card, to allow the card author to dynamically control the visibility of the columns in the Table Card and visibility of the groups and group items of the Object Card. For more information, see the [Table Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/table) section and the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/object) sections in the Card Explorer.
-   The Adaptive Cards are no longer in experimental state. We have also added an example of how to use the extension mechanism of the Adaptive Cards.For more information, see the [Adaptive Cards](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) section and the [Submit with Extension](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/extension) sample in the Card Explorer.

<sub>Changed•Control•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.unified.Calendar`** 

</td>
<td valign="top">

**`sap.ui.unified.Calendar`**

We have added a new property to the `DateTypeRange` class, called `secondaryType`. It allows developers to set any special day as a non-working day, using a single object. This new property is of type `CalendarDayType` and accepts only `None` and `NonWorkingDay` values, which can be combined with other `CalendarDayType` objects. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.DateTypeRange).

<sub>Changed•Control•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.unified.FileUploader`** 

</td>
<td valign="top">

**`sap.ui.unified.FileUploader`**

We have added a new `httpRequestMethod` \(experimental\) property to enable the file upload with both HTTP POST and HTTP PUT request methods according to the data service requirements. This new property accepts enumeration of type `sap.ui.unified.FileUploaderHttpRequestMethod`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.FileUploader).

<sub>Changed•Control•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
<tr>
<td valign="top">

1.81 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Demo Kit Samples** 

</td>
<td valign="top">

**Demo Kit Samples**

We have added a new *Pattern* category in the *Samples* section of the Demo Kit app. The samples added in this category aim to improve the representation of more complex scenarios, such as layouts and floorplans.

![](images/loio5004e443d73749a48ba7926a0c0d6f69_HiRes.png)

<sub>Changed•Feature•Info Only•1.81</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-08-13

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.122](What_s_New_in_OpenUI5_1_122_5d078da.md "With this release OpenUI5 is upgraded from version 1.121 to 1.122.")

[What's New in OpenUI5 1.121](What_s_New_in_OpenUI5_1_121_91a4a2f.md "With this release OpenUI5 is upgraded from version 1.120 to 1.121.")

[What's New in OpenUI5 1.120](What_s_New_in_OpenUI5_1_120_2359b63.md "With this release OpenUI5 is upgraded from version 1.119 to 1.120.")

[What's New in OpenUI5 1.119](What_s_New_in_OpenUI5_1_119_0b1903a.md "With this release OpenUI5 is upgraded from version 1.118 to 1.119.")

[What's New in OpenUI5 1.118](What_s_New_in_OpenUI5_1_118_3eecbde.md "With this release OpenUI5 is upgraded from version 1.117 to 1.118.")

[What's New in OpenUI5 1.117](What_s_New_in_OpenUI5_1_117_029d3b4.md "With this release OpenUI5 is upgraded from version 1.116 to 1.117.")

[What's New in OpenUI5 1.116](What_s_New_in_OpenUI5_1_116_ebd6f34.md "With this release OpenUI5 is upgraded from version 1.115 to 1.116.")

[What's New in OpenUI5 1.115](What_s_New_in_OpenUI5_1_115_409fde8.md "With this release OpenUI5 is upgraded from version 1.114 to 1.115.")

[What's New in OpenUI5 1.114](What_s_New_in_OpenUI5_1_114_890fce1.md "With this release OpenUI5 is upgraded from version 1.113 to 1.114.")

[What's New in OpenUI5 1.113](What_s_New_in_OpenUI5_1_113_a9553fe.md "With this release OpenUI5 is upgraded from version 1.112 to 1.113.")

[What's New in OpenUI5 1.112](What_s_New_in_OpenUI5_1_112_34afc69.md "With this release OpenUI5 is upgraded from version 1.111 to 1.112.")

[What's New in OpenUI5 1.111](What_s_New_in_OpenUI5_1_111_7a67837.md "With this release OpenUI5 is upgraded from version 1.110 to 1.111.")

[What's New in OpenUI5 1.110](What_s_New_in_OpenUI5_1_110_71a855c.md "With this release OpenUI5 is upgraded from version 1.109 to 1.110.")

[What's New in OpenUI5 1.109](What_s_New_in_OpenUI5_1_109_3264bd2.md "With this release OpenUI5 is upgraded from version 1.108 to 1.109.")

[What's New in OpenUI5 1.108](What_s_New_in_OpenUI5_1_108_66e33f0.md "With this release OpenUI5 is upgraded from version 1.107 to 1.108.")

[What's New in OpenUI5 1.107](What_s_New_in_OpenUI5_1_107_d4ff916.md "With this release OpenUI5 is upgraded from version 1.106 to 1.107.")

[What's New in OpenUI5 1.106](What_s_New_in_OpenUI5_1_106_5b497b0.md "With this release OpenUI5 is upgraded from version 1.105 to 1.106.")

[What's New in OpenUI5 1.105](What_s_New_in_OpenUI5_1_105_4d6c00e.md "With this release OpenUI5 is upgraded from version 1.104 to 1.105.")

[What's New in OpenUI5 1.104](What_s_New_in_OpenUI5_1_104_69e567c.md "With this release OpenUI5 is upgraded from version 1.103 to 1.104.")

[What's New in OpenUI5 1.103](What_s_New_in_OpenUI5_1_103_0e98c76.md "With this release OpenUI5 is upgraded from version 1.102 to 1.103.")

[What's New in OpenUI5 1.102](What_s_New_in_OpenUI5_1_102_f038c99.md "With this release OpenUI5 is upgraded from version 1.101 to 1.102.")

[What's New in OpenUI5 1.101](What_s_New_in_OpenUI5_1_101_7733b00.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](What_s_New_in_OpenUI5_1_100_27dec1d.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](What_s_New_in_OpenUI5_1_99_4f35848.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](What_s_New_in_OpenUI5_1_98_d9f16f2.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](What_s_New_in_OpenUI5_1_97_fa0e282.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](What_s_New_in_OpenUI5_1_96_7a9269f.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](What_s_New_in_OpenUI5_1_95_a1aea67.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What_s_New_in_OpenUI5_1_94_c40f1e6.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What_s_New_in_OpenUI5_1_93_f273340.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What_s_New_in_OpenUI5_1_92_1ef345d.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What_s_New_in_OpenUI5_1_91_0a2bd79.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What_s_New_in_OpenUI5_1_90_91c10c2.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What_s_New_in_OpenUI5_1_89_e56cddc.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What_s_New_in_OpenUI5_1_88_e15a206.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_b506da7.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What_s_New_in_OpenUI5_1_86_4c1c959.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What_s_New_in_OpenUI5_1_85_1d18eb5.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What_s_New_in_OpenUI5_1_84_dc76640.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What_s_New_in_OpenUI5_1_82_3a8dd13.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_8cee506.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_99c4cdc.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_f09b63e.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_c46b439.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_aad03b5.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_5cbb62d.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_c22208a.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_231dd13.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_521cad9.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_a93a6a3.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_f073d69.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_89a18bd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_f94bf93.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_a6b1472.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_c9896e9.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_0f5acfd.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What_s_New_in_OpenUI5_1_64_0e30822.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_e8d9da7.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What_s_New_in_OpenUI5_1_62_771f4d5.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What_s_New_in_OpenUI5_1_61_d991552.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_5a0e1f7.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_7c927aa.md "With this release OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_108b7fd.md "With this release OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_c838330.md "With this release OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_849e1b6.md "With this release OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_759e9f3.md "With this release OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_fa1efac.md "With this release OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_6307539.md "With this release OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

