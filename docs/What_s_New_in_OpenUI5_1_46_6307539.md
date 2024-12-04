<!-- loio6307539826e946eda7b619f2e679569a -->

| loio |
| -----|
| 6307539826e946eda7b619f2e679569a |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/6307539826e946eda7b619f2e679569a) | [demo kit latest release](https://sdk.openui5.org/topic/6307539826e946eda7b619f2e679569a)</div>

## What's New in OpenUI5 1.46

With this release OpenUI5 is upgraded from version 1.44 to 1.46.

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

1.46 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**New Themes** 

</td>
<td valign="top">

**New Themes**

The High Contrast White \(HCW\) and High Contrast Black \(HCB\) themes \(`sap_belize_hcw` / `sap_belize_hcb`\) are now delivered with all SAP Fiori-related libraries. They offer a better visual experience for people with visual impairments. For more information, see [Accessibility](Accessibility_322f55d.md).

<sub>New•Feature•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Support for Persian Calendar** 

</td>
<td valign="top">

**Support for Persian Calendar**

All our controls now support the Persian calendar. The Persian calendar is also sometimes referred to as "Solar Hijri", "Iranian" or "Farsi" calendar.

The Persian calendar year begins around March 21st of each Gregorian year and ends at around March 20th of the following year. To convert the Persian calendar years into the equivalent Gregorian year, add 621 or 622 years to the Persian calendar year depending on whether the Persian calendar year has begun or not.

![](images/loiobbe5a6aa64b74db6bcf6f0bc510f0d34_LowRes.png)

<sub>New•Feature•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.Avatar`** 

</td>
<td valign="top">

**`sap.f.Avatar`**

**`sap.f.Avatar`** is an SAP Fiori 2.0 image-like control that has different display options for representing images, initials, and icons. It allows the usage of different content, shapes, and sizes depending on the use case.

![](images/loiob6de75d7ec6745ef9bd006c430325948_LowRes.png)

There are several predefined sizes, as well as an option to set a custom size.

![](images/loio9127c435630540d890ff85b14cbed308_LowRes.png)

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.Avatar) and the [Sample](https://sdk.openui5.org/entity/sap.m.Avatar/sample/sap.m.sample.Avatar).

<sub>New•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayout`** 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayout`**

This control represents the new SAP Fiori 2.0 base layout for an app. It implements the master-detail-detail paradigm by displaying up to three pages in separate columns. The columns are referred to as `Begin`, `Mid`, and `End`, and their width is variable depending on the current layout.

There are several possible layouts that can be changed with the control's API, and also by the user with navigation arrows.

![](images/loio2d2dc782d40843f391a6da7b3c056acb_LowRes.png)

For more information, see [Building an App with the Flexible Column Layout and Related Classes](Building_an_App_with_the_Flexible_Column_Layout_and_Related_Classes_59a0e11.md), the [API Reference](https://sdk.openui5.org/api/sap.f.FlexibleColumnLayout), and the [Sample](https://sdk.openui5.org/entity/sap.f.FlexibleColumnLayout/sample/sap.f.sample.FlexibleColumnLayoutSimple).

<sub>New•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.semantic.SemanticPage`** 

</td>
<td valign="top">

**`sap.f.semantic.SemanticPage`**

This new SAP Fiori 2.0 control represents an enhanced `sap.f.DynamicPage` that contains controls with semantic-specific meaning. You can set different actions using the available aggregations, and the `sap.f.semantic.SemanticPage` will automatically position them in dedicated sections of the title or the footer of the page, facilitating the implementation of the SAP Fiori 2.0 design guidelines.

  
  
**Different types of actions in the title positioned in a predefined order**

![](images/loio12fc65627dd9416e98d8a25fc31d2410_LowRes.png "Different types of actions in the title positioned in a
									predefined order")

  
  
**Different types of actions in the footer’s right and left areas, positioned in a predefined order**

![](images/loio57b825fe5df7414e89013e92e0ee30e8_LowRes.png "Different types of actions in the footer’s right and left
									areas, positioned in a predefined order")

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.semantic.SemanticPage) and the [Sample](https://sdk.openui5.org/entity/sap.f.semantic.SemanticPage/sample/sap.f.sample.SemanticPageFreeStyle).

<sub>New•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.codeeditor.CodeEditor`** 

</td>
<td valign="top">

**`sap.ui.codeeditor.CodeEditor`**

You can use this control to visualize source code of various types, with syntax highlighting and line numbers, in edit and read-only mode, for example, in scenarios where you want the user to inspect and edit source code. The `CodeEditor` is a wrapper control for the open-source *Ace* code editor \(see [https://ace.c9.io](https://ace.c9.io)\). For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.codeeditor.CodeEditor) and the [Sample](https://sdk.openui5.org/entity/sap.ui.codeeditor.CodeEditor/sample/sap.ui.codeeditor.sample.CodeEditor).

<sub>New•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

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

The new version of the OpenUI5 OData V4 model now supports the following features:

-   Changing query options on `sap.ui.model.odata.v4.ODataListBinding` and `sap.ui.model.odata.v4.ODataContextBinding`

-   Requesting `$count` system query option on `sap.ui.model.odata.v4.ODataListBinding`

-   Accessing value lists

-   Forwarding the `$search` system query option

-   Branching from OData V4 model into metadata using the hash \(`#`\) character \(see [sap.ui.model.odata.v4.Context\#getObject\(\)](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/methods/createBindingContext)\) in `template:with`


> ### Caution:  
> **Incompatibility Due to Bug Fix**
> 
> The following bug has been reported: If you call the [sap.ui.model.odata.v4.Context\#getObject\(\)](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/getObject) or the [sap.ui.model.odata.v4.Context\#requestObject\(\)](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/requestObject) methods without a parameter, the expected and documented behavior is that the same result is returned as if the parameter `sPath=""` had been specified. Due to the bug, however, the return value wraps the expected output that can then only be accessed via `.value[0]`, for example `oContext.getObject().value[0]`.
> 
> **If you have used this workaround, your application will break starting with OpenUI5 version 1.44.6.**
> 
> **Solution**: If your application needs to run with both the fixed and unfixed versions of OpenUI5, specify the `sPath=""` parameter, for `sPath` parameter. In both cases, you **must not** use the workaround with `.value[0]` any longer.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [sample](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

<sub>Changed•Feature•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OData V2 Model** 

</td>
<td valign="top">

**OData V2 Model**

For OData V2 models, the V2 annotation `sap:aggregation-role=”dimension”` is now converted into V4 annotation `"com.sap.vocabularies.Analytics.v1.Dimension" : { "Bool" : "true" }`.

V2 annotation `sap:aggregation-role="measure"` is now converted into V4 annotation `"com.sap.vocabularies.Analytics.v1.Measure" : { "Bool" : "true" }`.

For more information, see [Meta Model for OData V2](OData_V2_Model_6c47b2b.md#loio341823349ed04df1813197f2a0d71db2) and the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.ODataMetaModel).

<sub>Changed•Feature•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**One Page Acceptance Tests \(OPA5\)** 

</td>
<td valign="top">

**One Page Acceptance Tests \(OPA5\)**

The new `LabelFor` matcher checks if a given control is associated with the `sap.m.Label` control by their `labelFor` property. You can use it when searching by the text property or by the `i18n` key of the `sap.m.Label` control. For more information, see [Cookbook for OPA5](Cookbook_for_OPA5_ce4b180.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.test.matchers.LabelFor), and the [Sample](https://sdk.openui5.org/entity/sap.ui.test.matchers/sample/sap.ui.core.sample.matcher.LabelFor).

<sub>Changed•Feature•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ComboBox`** 

</td>
<td valign="top">

**`sap.m.ComboBox`**

-   The value state error message is now visible above all list items in the dropdown list of the `sap.m.ComboBox`. This improves the usability on mobile devices \(tablets and phones\).

-   When the `ComboBox` displays two columns \(for example, key and value\), you can search and filter for matching strings in both columns. This is enabled with the `filterSecondaryValues` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ComboBox/methods/getFilterSecondaryValues) and the [Sample](https://sdk.openui5.org/entity/sap.m.ComboBox/sample/sap.m.sample.ComboBoxSearchBoth).


<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.DatePicker`** 

</td>
<td valign="top">

**`sap.m.DatePicker`**

We have introduced a new `navigate` event. While navigating in the calendar popup of the `sap.m.DatePicker`, you can now receive an event containing the first and the last dates that are currently visible. You can use this information for lazy loading of special dates. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DatePicker/events/navigate).

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.GenericTile`** 

</td>
<td valign="top">

**`sap.m.GenericTile`**

The new `Actions` `scope` property was added to provide an editing option for the `GenericTile` control when included on a Web page, for example, on the SAP Fiori launchpad. It is aligned explicitly with the interaction design of the SAP Fiori launchpad’s *Edit* mode. Both the `sap.m.GenericTile` and `sap.m.SlideTile` controls have been extended with this feature. You use the new `scope` property to switch the visual representation of the `GenericTile` or `SlideTile` on a Web page from the `Display` scope to the `Actions` scope. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.GenericTile) and the [Sample](https://sdk.openui5.org/entity/sap.m.GenericTile/sample/sap.m.sample.GenericTileLineMode).

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

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

**`sap.m.Input`** and all inheriting controls now allow filtering and searching in two or more columns. Matching is done only on the initial character and the matching sequence is displayed in bold in the suggestion list.

![](images/loiof31e644295ca4df1a16300064c886e28_LowRes.png)

For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Input/sample/sap.m.sample.InputAssistedTwoValues).

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MessageBox`** 

</td>
<td valign="top">

**`sap.m.MessageBox`**

**`sap.m.MessageBox`** can now hold and display formatted text \(`sap.m.FormattedText`\) and JSON content. This allows you to display message boxes with complex content. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.MessageBox/sample/sap.m.sample.MessageBoxInfo).

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MultiComboBox`** 

</td>
<td valign="top">

**`sap.m.MultiComboBox`**

The delay for text validation in the `sap.m.MultiComboBox` has been changed in order to react correctly to special inputs in non-Latin languages \(for example, Chinese\).

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MultiInput`** 

</td>
<td valign="top">

**`sap.m.MultiInput`**

**`sap.m.MultiInput`** has been refactored to improve performance and accessibility. The `tokenChange()` event is deprecated and replaced with the new `tokenUpdate()`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MultiInput/events/tokenUpdate).

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.NotificationListItem / sap.m.NotificationListGroup`** 

</td>
<td valign="top">

**`sap.m.NotificationListItem / sap.m.NotificationListGroup`**

We have implemented several new features:

-   When the maximum number of notifications is reached, a message is shown on the bottom of the `NotificationListGroup` notifying the user about additional notifications that are hidden.

    ![](images/loio4387085657e0455786240dbffb89fe5b_LowRes.png)

-   Action buttons have been moved from the footer of the `NotificationListItem` to the header to improve usability.

    ![](images/loio2b1c9e05fad34795bb189c9c28975b1d_LowRes.png)


For more information, see the samples [Notification List Item](https://sdk.openui5.org/entity/sap.m.NotificationListItem/sample/sap.m.sample.NotificationListItem) and [Notification List Group with Max Number of Notifications Reached](https://sdk.openui5.org/entity/sap.m.NotificationListGroup/sample/sap.m.sample.MaxNumberOfNotificationsReached). 

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

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

We have introduced a new `rowHeaderClick` event. You can now receive an event when a row header of the `sap.m.PlanningCalendar` is clicked. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar/events/rowHeaderClick).

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.QuickView / sap.m.QuickViewCard`** 

</td>
<td valign="top">

**`sap.m.QuickView / sap.m.QuickViewCard`**

**`sap.m.QuickView`** and **`sap.m.QuickViewCard`** have a new parameter called `navOrigin` that improves the navigation when you use data binding. The new parameter is set in the `navigate` and `afterNavigate` events and holds a link to the originating card. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.QuickViewBase/events/afterNavigate).

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Slider / sap.m.RangeSlider`** 

</td>
<td valign="top">

**`sap.m.Slider / sap.m.RangeSlider`**

**`sap.m.Slider`** and **`sap.m.RangeSlider`** can display labels for tick marks. The labels are defined and represented as a `sap.m.ResponsiveScale`, which is logically decoupled from the slider. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ResponsiveScale) and the [Sample](https://sdk.openui5.org/entity/sap.m.Slider/sample/sap.m.sample.Slider).

![](images/loiob11c763f854c4b069eb89f58423bb993_LowRes.png)

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Table`** 

</td>
<td valign="top">

**`sap.m.Table`**

Screen reader support for `sap.m.Table` has been improved. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Table).

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.UploadCollection`** 

</td>
<td valign="top">

**`sap.m.UploadCollection`**

To add an item to the upload list, you can also use drag & drop on your desktop or tablet. This feature is available in both the *Instant Upload* and *Upload Pending* scenarios. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.UploadCollection) and the [Samples](https://sdk.openui5.org/entity/sap.m.UploadCollection).

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.layout.form.Form`** 

</td>
<td valign="top">

**`sap.ui.layout.form.Form`**

The samples in the Demo Kit have been improved.

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.table.*`** 

</td>
<td valign="top">

**`sap.ui.table.*`**

-   Keyboard navigation has been enhanced for *Edit* mode.

-   You can now define row-specific actions, such as navigation. The actions remain available on the right even when you scroll horizontally.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.Table) and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.ui.table.sample.RowAction). 

<sub>Changed•Control•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
<tr>
<td valign="top">

1.46 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Demo Kit Improvements** 

</td>
<td valign="top">

**Demo Kit Improvements**

-   You can now switch the *Samples* to the new *High Contrast White* theme from the *Settings* menu.

-   We reworked the landing page for the *Demo Apps* in the Demo Kit. It now features and highlights demo apps in multiple categories, and tests and related documentation chapters are now linked. Check it out at [Demo Apps](https://sdk.openui5.orgdemoapps).

-   New and reworked demo apps:

    -   *Browse Orders*: A new master-detail app with features for browsing orders

        ![](images/loio67c304672d8241b4a6496b969c01d972_LowRes.png)

    -   *Shop Administrator*: The tool page demo app has been completely renovated and now showcases a shop administration scenario with controls from the `sap.tnt`, `sap.ui.layout`, and `sap.suite.ui` library.

        ![](images/loioa053afde39624bf29121f26802d1d168_LowRes.png)



<sub>Changed•Feature•Info Only•1.46</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2017-05-04

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.130](What_s_New_in_OpenUI5_1_130_85609d4.md "With this release OpenUI5 is upgraded from version 1.129 to 1.130.")

[What's New in OpenUI5 1.129](What_s_New_in_OpenUI5_1_129_d22b8af.md "With this release OpenUI5 is upgraded from version 1.128 to 1.129.")

[What's New in OpenUI5 1.128](What_s_New_in_OpenUI5_1_128_1f76220.md "With this release OpenUI5 is upgraded from version 1.127 to 1.128.")

[What's New in OpenUI5 1.127](What_s_New_in_OpenUI5_1_127_e5e1317.md "With this release OpenUI5 is upgraded from version 1.126 to 1.127.")

[What's New in OpenUI5 1.126](What_s_New_in_OpenUI5_1_126_1d98116.md "With this release OpenUI5 is upgraded from version 1.125 to 1.126.")

[What's New in OpenUI5 1.125](What_s_New_in_OpenUI5_1_125_9d87044.md "With this release OpenUI5 is upgraded from version 1.124 to 1.125.")

[What's New in OpenUI5 1.124](What_s_New_in_OpenUI5_1_124_7f77c3f.md "With this release OpenUI5 is upgraded from version 1.123 to 1.124.")

[What's New in OpenUI5 1.123](What_s_New_in_OpenUI5_1_123_9d00ac7.md "With this release OpenUI5 is upgraded from version 1.122 to 1.123.")

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

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f5e2a21.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

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

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

