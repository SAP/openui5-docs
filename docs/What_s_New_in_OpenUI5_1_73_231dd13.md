<!-- loio231dd13787ca4d5c8fd976b0f2fbe82b -->

| loio |
| -----|
| 231dd13787ca4d5c8fd976b0f2fbe82b |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/231dd13787ca4d5c8fd976b0f2fbe82b) | [demo kit latest release](https://sdk.openui5.org/topic/231dd13787ca4d5c8fd976b0f2fbe82b)</div>

## What's New in OpenUI5 1.73

With this release OpenUI5 is upgraded from version 1.72 to 1.73.

***

** **


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

 1.73 



</td>
<td valign="top">

 New 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.f.AvatarGroup` \(Experimental\)** 



</td>
<td valign="top">

**`sap.f.AvatarGroup` \(Experimental\)**

`AvatarGroup` is used to display a group of related avatars, arranged horizontally. The control allows you to display the avatars in different sizes, depending on your use case. Two group types are available: `Group` and `Individual`.

 ![](images/loiod2ac28d2859f484fb9228049eefe0372_HiRes.gif) 

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.AvatarGroup) and the [Samples](https://sdk.openui5.org/entity/sap.f.AvatarGroup).

<sub>New•Control•Info Only•1.73</sub>



</td>
<td valign="top">

Info Only



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Export Functions** 



</td>
<td valign="top">

**Export Functions**

The `sap.ui.core.util.Export` class has been deprecated.

<sub>Changed•Feature•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



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

-   Binding of operation parameters as described in [OData Operations](OData_Operations_b54f789.md) in the OpenUI5 documentation.

-   Methods for finding bindings that have become public:

    -   `sap.ui.model.odata.v4.ODataModel#getAllBindings`
    -   `sap.ui.model.Binding#getPath` 
    -   `sap.ui.model.Binding#getContext`
    -   `sap.ui.model.Binding#getModel`


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

<sub>Changed•Feature•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.f.semantic.SemanticPage`** 



</td>
<td valign="top">

**`sap.f.semantic.SemanticPage`**

The `fitContent` property of the `sap.f.DynamicPage` control is now also exposed in `sap.f.semantic.SemanticPage`. It's used to optimize the responsiveness and behavior of the control and we recommend using this property when displaying content of adaptive controls that stretch to fill the available space.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.semantic.SemanticPage).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



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

Four new button types were introduced in the `sap.m.ButtonType` enum. Designed as message triggering buttons, use them to open `sap.m.MessagePopover`. Each button type has a dedicated meaning.

-   Critical
-   Negative
-   Success
-   Neutral

 ![](images/loiodbf0df86dd374616b631e278ab40f5de_LowRes.png) 

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ButtonType).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.ComboBox`, `sap.m.MultiComboBox`** 



</td>
<td valign="top">

**`sap.m.ComboBox`, `sap.m.MultiComboBox`**

We have updated the behavior of the `showItems` method. When the control's picker is opened, the dropdown arrow is not in pressed state, as it was previously. Now, pressing the dropdown arrow for the first time opens the control's picker with all items, and with the second press the picker is closed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ComboBoxBase).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.Dialog`** 



</td>
<td valign="top">

**`sap.m.Dialog`**

We have enabled responsive padding support. Application developers can now configure `sap.m.Dialog` and enable its responsive padding in the SAP Fiori 3 themes.

For more information, see [Enabling Responsive Paddings According to the Control Width](Enabling_Responsive_Paddings_According_to_the_Control_Width_3b718b5.md).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.Input`** 



</td>
<td valign="top">

**`sap.m.Input`**

A `change` event is now fired when the browser autofill fills an input.

> ### Note:  
> If `showValueHelp` or `showSuggestion` are set to `true`, the native browser autofill will not fire a `change` event.

 For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Input). 

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.Label`** 



</td>
<td valign="top">

**`sap.m.Label`**

A visual change was introduced for the `sap.m.Label` control to align it with SAP Fiori Design Guidelines. The asterisk is now positioned on the right side of the text. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Label) and the [Sample](https://sdk.openui5.org/entity/sap.m.Label/sample/sap.m.sample.Label).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.list`, `sap.m.StandardListItem`** 



</td>
<td valign="top">

**`sap.m.list`, `sap.m.StandardListItem`**

The usability of the additional information text and its combination with title and description has been improved for these controls. The information text is no longer truncated if it is shorter than or equal to the character limit predefined by the control. For more information, see the [Card Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/numeric).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.MessagePopover`** 



</td>
<td valign="top">

**`sap.m.MessagePopover`**

We have exposed the `groupItems` property and `navigateBack` function as APIs in the control. Using the `navigateBack` function you can navigate back to the list page, and with the `groupItems` property you can configure whether or not items should be grouped. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MessagePopover). 

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.NotificationListItem`, `sap.m.NotificationListGroup`** 



</td>
<td valign="top">

**`sap.m.NotificationListItem`, `sap.m.NotificationListGroup`**

We have redesigned the notifications, and now they are lighter, easy to use, and aligned with the SAP Fiori 3 user experience. The changes include:

-   The priority of the notifications is now visualized with a status icon.
-   Action buttons in the `sap.m.OverflowToolbar` could now be hidden.
-   Collapse/expand functionality of the `sap.m.NotificationListGroup` is implemented with an arrow button instead of text.
-   For the `sap.m.NotificationListGroup`, we have enabled an item counter, which represents the count of currently loaded items inside this group. It can be visible or hidden using the new `showItemsCounter` property.
-   The new `authorInitials` property is now introduced for `sap.m.NotificationListItem`. It is visualized as an avatar, and used as a fallback when the `authorPicture` is not provided. The background color of the avatar is chosen randomly.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.NotificationListGroup) and the [Samples](https://sdk.openui5.org/entity/sap.m.NotificationListGroup). 

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.NumericContent`** 



</td>
<td valign="top">

**`sap.m.NumericContent`**

A new `adaptiveFontSize` property is now introduced to meet different country/locale requirements according to the Unicode Common Locale Data Repository \(CLDR\). For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.NumericContent) and [CLDR](http://cldr.unicode.org/).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



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

We have added a new `headerId` parameter to the `rowHeaderClick` event, which enables developers to directly access row header by ID.

> ### Note:  
> Do not use this feature for `PlanningCalendar`’s `rowHeader` modification.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.ProgressIndicator`** 



</td>
<td valign="top">

**`sap.m.ProgressIndicator`**

With the new `displayAnimation` property, you can now determine whether a percentage change is displayed with or without animation.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ProgressIndicator) and the [Sample](https://sdk.openui5.org/entity/sap.m.ProgressIndicator/sample/sap.m.sample.ProgressIndicator).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



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

-   We have improved the support for the relative date ranges. This allows the card developers to use date ranges, such as `lastYear` or `nextQuarter` inside the card's manifest. Such automatically calculated date ranges can be used in data requests or other card attributes. For more information, see [Integration Card Date Range Handling](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/featureDateRangeHandling) in the Card Explorer.
-   We have added a new `format` namespace to hold formatters used in expression bindings, and added a predefined `date` formatter method to it. For more information, see the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/dateAndTime) in the Card Explorer.
-   The custom HTML element to consume cards on any web page is refactored. Now, height and width are specified in the standard CSS syntax and no longer as separate tag attributes. For more information, see the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/htmlConsumption) in the Card Explorer.

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.ui.layout.cssgrid.ResponsiveColumnLayout`** 



</td>
<td valign="top">

**`sap.ui.layout.cssgrid.ResponsiveColumnLayout`**

This control now also supports Microsoft Internet Explorer 11, due to the implemented polyfill. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.cssgrid.CSSGrid) and the [Sample](https://sdk.openui5.org/entity/sap.ui.layout.cssgrid.CSSGrid/sample/sap.ui.layout.sample.GridResponsiveColumnLayout).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`** 



</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`**

The `navigated` property that was introduced in version 1.72 is now also available for these controls \(if no row actions are available\). The property shows a navigation indicator at the end of a row to indicate that the user has either already navigated to further details or can navigate to further details from the item, depending on the application use case. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.table.RowSettings) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.RowAction).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.uxap.ObjectPageHeader`** 



</td>
<td valign="top">

**`sap.uxap.ObjectPageHeader`**

With the new `objectImageBackgroundColor` property, you can now determine the background color of the icon or the image placeholder used in the `sap.uxap.ObjectPageHeader`.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageHeader) and the [Sample](https://sdk.openui5.org/entity/sap.uxap.ObjectPageLayout/sample/sap.uxap.sample.ObjectPageHeaderContentPriorities).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.uxap.ObjectPageLayout`** 



</td>
<td valign="top">

**`sap.uxap.ObjectPageLayout`**

With the new `sectionChange` event, you can identify when the page is scrolled to a specific section. The `section` and `subSection` event parameters are provided when the event is fired.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageLayout).

<sub>Changed•Control•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
<tr>
<td valign="top">

 1.73 



</td>
<td valign="top">

 New 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Demo Kit Search Highlighting** 



</td>
<td valign="top">

**Demo Kit Search Highlighting**

You can now easily find the results you're interested in with the new search highlighting functionality that we implemented for the *Search Results* page and the *API Reference* tree filter.

 ![](images/loio040558940043445a9299e24b37aef5c5_HiRes.gif) 

<sub>New•Feature•Info Only•1.73</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2019-12-05



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f5e2a21.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_8cee506.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_99c4cdc.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_f09b63e.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_c46b439.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_aad03b5.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_5cbb62d.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_c22208a.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

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

