<!-- loio21fc6cb77b0c44aab55f045812e69c98 -->

| loio |
| -----|
| 21fc6cb77b0c44aab55f045812e69c98 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/21fc6cb77b0c44aab55f045812e69c98) | [demo kit latest release](https://sdk.openui5.org/topic/21fc6cb77b0c44aab55f045812e69c98)</div>

## What's New in OpenUI5 1.74

With this release OpenUI5 is upgraded from version 1.73 to 1.74.

***

<a name="loio21fc6cb77b0c44aab55f045812e69c98__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td valign="top">

**Test Recorder**

The Test Recorder tool is now part of the OpenUI5 framework and is available in all browsers. Use it in any OpenUI5 app to inspect the rendered user interface, view the control properties, and get hints about writing tests. The tool is aligned with the two official OpenUI5 testing tools – OPA5 and UIVeri5.

 ![](images/loio639a7041dc2740c2b9f0183a7aee41bb_HiRes.png) 

For more information, see [Test Recorder](Test_Recorder_2535ef9.md).



</td>
</tr>
</table>

***

<a name="loio21fc6cb77b0c44aab55f045812e69c98__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**`Card Explorer`**

We have enhanced the functionality to download samples from the Card Explorer, and now there are 3 optional file formats available: JSON, ZIP, and CARD.For more information, see [Card Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/index.html).



</td>
</tr>
<tr>
<td valign="top">

**Navigation in Nested Components**

In recent releases, the capabilities to [Navigate with Nested Components](Navigate_with_Nested_Components_8e9d6e4.md) were enhanced significantly. In addition to the available documentation, a [Sample](https://sdk.openui5.org/entity/sap.ui.core.routing.Router/sample/sap.ui.core.sample.RoutingNestedComponent) has been added to showcase some fundamental possibilities of using components to structure applications and how to interconnect them via routing. 



</td>
</tr>
<tr>
<td valign="top">

**Negative Predefined CSS Margin Classes**

We’ve introduced the following negative CSS margin classes to help you align controls that have their own default margins:

-   `sapUiTinyNegativeMarginBeginEnd`

-   `sapUiSmallNegativeMarginBeginEnd`

-   `sapUiMediumNegativeMarginBeginEnd`

-   `sapUiLargeNegativeMarginBeginEnd`


For more information, see [Using Predefined CSS Margin Classes](Using_Predefined_CSS_Margin_Classes_777168f.md)and the [Sample](https://sdk.openui5.org/entity/sap.ui.core.StandardMargins/sample/sap.m.sample.StandardNegativeMarginsTwoSided).



</td>
</tr>
<tr>
<td valign="top">

**Responsive Padding Enablement**

We've introduced responsive paddings to the `sap.m.IconTabBar`, `sap.m.ObjectHeader`, and `sap.m.TabContainer` controls. For more information, see [Enabling Responsive Paddings According to the Control Width](Enabling_Responsive_Paddings_According_to_the_Control_Width_3b718b5.md).



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The `autoExpandSelect:true` model setting has been enhanced for property bindings that are added later.

-   We have added the `sap.ui.model.v4.ODataListBinding.getDownloadUrl` method.
-   `sap.ui.model.v4.AnnotationHelper.format` can now be used for operation parameters.
-   For messages returned in error responses of operation calls, targets pointing to operation parameters are now parsed correctly.
-   The `sap.ui.model.v4.Context.setProperty` method can be used to set properties locally on the client by specifying `null` as the `groupId`. The set value is then not included in PATCH and POST requests to create the new entity.
-   Annotation targets for \(overloaded\) bound operations in 4.01 Format are also supported in value list metadata.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.



</td>
</tr>
</table>

***

<a name="loio21fc6cb77b0c44aab55f045812e69c98__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.Avatar`**

We've added *remove* and *reveal* actions in the `Avatar` design-time metadata. Now, the control can be removed and revealed when using UI adaptation at runtime.For more information, see the [Samples](https://sdk.openui5.org/entity/sap.m.Avatar/sample/sap.m.sample.Avatar).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.ColorPalette`**

We have introducted a *Recent Colors* section, showing the last 5 recently used colors. This feature is enabled by default, making it is easier to find and select the exact colors. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ColorPalette) and the [Sample](https://sdk.openui5.org/entity/sap.m.ColorPalette/sample/sap.m.sample.ColorPalettePopover).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.DateRangeSelection`**

We have introduced the ability to select month and year ranges. This improves the user experience when only a month or a year range has to be selected, and is defined by the `displayFormat` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DateRangeSelection) and the [Sample](https://sdk.openui5.org/entity/sap.m.DateRangeSelection/sample/sap.m.sample.DateRangeSelection).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.List, sap.m.Table, sap.m.Tree`**

The busy indicator is now displayed in the center of the visible area of the UIs of these controls and is no longer vertically centered and therefore not always visible. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.List/sample/sap.m.sample.ListDeletion).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.NavContainer`**

In version 1.69, the default value for the `defaultTransitionName` property was visually updated to behave as a slide & fade animation and the classic slide animation was no longer an option. Now, we've added the previous slide behavior as a new type of transition. To use it, set the `defaultTransitionName` property to `baseSlide`.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.NavContainer) and the [Sample](https://sdk.openui5.org/entity/sap.m.NavContainer/sample/sap.m.sample.NavContainer).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.NotificationListItem`**

The avatar background color can now be managed by the application developer using the new `authorAvatarColor` property. Now, if any of the `authorPicture` or `authorInitials` properties are not set, the default icon will not be displayed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.NotificationListItem) and the [Sample](https://sdk.openui5.org/entity/sap.m.NotificationListItem/sample/sap.m.sample.NotificationListItem).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.plugins.DataStateIndicator`**

This plugin for the table controls \(`sap.m.List, sap.m.Table, sap.ui.table.Table`\) allows you to implement binding-related messages and show them on the UI using a message strip. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.plugins.DataStateIndicator) 



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Select`**

With the new `required` property, you can now indicate whether user input is required. This property is helpful for accessibility purposes when a single relationship between the field and a label can't be established, for example, when one label exists for multiple fields.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Select).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.StandardListItem`**

The new `infoStateInverted` property changes the rendering behavior of the information state and information text. If it is set to `true`, the color defined by the `infoState` property is then shown as the background color of the information text. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.StandardListItem) and the [Sample](https://sdk.openui5.org/entity/sap.m.StandardListItem/sample/sap.m.sample.StandardListItemInfoStateInverted).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Table`**

A more comprehensive message text is now shown if no data is available because all table columns are hidden. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Table/sample/sap.m.sample.TablePerso).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.ViewSettingsDialog`**

We have introduced a new button to display only the selected items in the filter tab, and to hide items that are not selected. This button works in combination with the Search field, so the displayed items are both filtered by title and selection. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ViewSettingsDialog) and the [Sample](https://sdk.openui5.org/entity/sap.m.ViewSettingsDialog/sample/sap.m.sample.ViewSettingsDialog).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Wizard`**

We have enhanced the `sap.m.Wizard` control for better integration in the `sap.f.DynamicPage`. In order to make use of it, you need to make certain configurations. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Wizard). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.tnt.InfoLabel`**

We have introduced the option to add an icon to the `sap.tnt.InfoLabel` content. It is defined by the new `icon` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.tnt.InfoLabel) and the [Sample](https://sdk.openui5.org/entity/sap.tnt.InfoLabel/sample/sap.tnt.sample.InfoLabel).

 ![](images/loiocadac6c2a6e74ac18c574ee7f3b4b0df_LowRes.png) 



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   A new experimental Calendar Card type is now available . Its purpose is to give an overview of a single entity \(a person, for example\). It consists of an interactive calendar, legend, and a schedule. For more information, see [Calendar Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar) in the Card Explorer.
-   We have enabled Data Sources to be used in the descriptor for `sap.ui.integration.widgets.Card`. Data Sources are named and reusable manifest entities that hold configuration settings for services. Referenced using special double-bracketed syntax, they are used to construct data request URLs. Data Sources are defined in the `sap.app` part of the manifest. For more information, see [Data Sources](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/dataSources) in the Card Explorer.
-   We have introduced new number formatters to represent the data on the UI in human-readable format. Now we have predefined number formatters for:

    -   Currency
    -   Date and Time
    -   Floating-point numbers
    -   Integers
    -   Percent
    -   Units of measurement

    For more information, see [Card Formatters](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/formatters) in the Card Explorer.

-   We now also support objects as values for manifest parameters. Until now only string values were supported. For more information, see [Manifest Parameters](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/manifestParameters) section in the Card Explorer.
-   We have introduced a new experimental type of card - Adaptive Card. With this type of card, you can visualize and reuse cards created using the Microsoft Adaptive Cards specification and manifest, while achieving fully adapted SAP Fiori 3 user experience, out of the box. For more information, see [Adaptive Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) in the Card Explorer.



</td>
</tr>
<tr>
<td valign="top">

**`sap.uxap.ObjectPageLayout`**

You can now move the corresponding section numbers that are displayed in the `AnchorBar` when using UI adaptation at runtime.For more information, see the [Samples](https://sdk.openui5.org/entity/sap.uxap.ObjectPageLayout).



</td>
</tr>
</table>

***

<a name="loio21fc6cb77b0c44aab55f045812e69c98__section_z2h_fh5_zcb"/>

### Documentation


<table>
<tr>
<td valign="top">

**Performance Checklist**

Ensuring that your OpenUI5 apps run fast is an important topic in application development. To support you in this task, we have improved the existing performance-related documentation as well as added some new information. Please use the comprehensive [Performance Checklist](Performance_Checklist_9c6400e.md) as a starting point for best practices to help you to review and speed up your OpenUI5 apps.



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

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f71563c.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_3294c68.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_edf8e35.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_d176be3.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_2ec6b6b.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_b9b0a3f.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_dc3d3ce.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

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

