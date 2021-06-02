<!-- loio0968958c4143469d941dbe3b59e06142 -->

| loio |
| -----|
| 0968958c4143469d941dbe3b59e06142 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/0968958c4143469d941dbe3b59e06142) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/0968958c4143469d941dbe3b59e06142)</div>

## What's New in OpenUI5 1.67

With this release OpenUI5 is upgraded from version 1.66 to 1.67.

***

<a name="loio0968958c4143469d941dbe3b59e06142__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   You can now call `v4.ODataModel.submitBatch` also for groups with submit mode `Auto`, for example, `$auto`.

-   The automatic refresh of the created entity is now also executed when `v4.ODataListBinding.create` was called on a relative list binding unless the `bSkipRefresh` parameter of `v4.ODataListBinding.create` is set.

-   Contexts of relative list bindings can now be refreshed with `v4.Context.refresh`.

-   The method `v4.Context.setProperty` is introduced.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).



</td>
</tr>
</table>

***

<a name="loio0968958c4143469d941dbe3b59e06142__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td>

**`sap.f.ShellBar`**

-   You can now define a custom tooltip for the home icon of the control using the new `homeIconTooltip` property.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.ShellBar).

-   A new search functionality is now available for the control. You can enable it by using the new `searchManager` aggregation which accepts controls of type `sap.f.SearchManager`.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.ShellBar) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.ShellBar/sample/sap.f.sample.ShellBarWithSearch).

-   Two different types of menu and title are now enabled for the control:

    -   If you need a separate menu button and a plain title, set the `showMenuButton` property to `true`.

    -   To display the title as part of a configurable mega menu, set the `showMenuButton` property to `false` and use the `menu` aggregation.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.ShellBar) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.f.ShellBar).




</td>
</tr>
<tr>
<td>

**`sap.m.OverflowToolbar`**

To improve the control's performance, we have introduced a new `asyncMode` property. When enabled, the thread is not blocked immediately after the `onAfterRendering` and `handleResize` functions, leading to fewer frame drops and a smoother experience upon resizing.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.OverflowToolbar).



</td>
</tr>
<tr>
<td>

**`sap.m.SinglePlanningCalendar`**

We have created new examples of the different use cases for `sap.m.SinglePlanningCalendar`. The first example represents a fully featured control to help you get familiar with all functionalities. The rest of the examples focus on one feature each so that it's convenient to copy source code from them.For more information, see the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar).



</td>
</tr>
<tr>
<td>

`**sap.m.StandardListItem**`

You can now use the `wrapping` property to enable the wrapping of titles and descriptions. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.StandardListItem) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.StandardListItem/sample/sap.m.sample.StandardListItemWrapping).



</td>
</tr>
<tr>
<td>

**`sap.ui.integration.widgets.Card`**

-   The status text attribute, part of the card header, is now also available in the numeric header. In addition to already supported string formats, you can now also configure bindable and dynamic formats and values, for example “X of Y” dynamic counter.

-   The content area of the Object and Analytical cards is now actionable. Card developers can now configure the content area to navigate to the corresponding app when clicked.


 For more information, see [Cards](Cards_5b46b03.md), the [API Reference](https://openui5.hana.ondemand.com//#/api/sap.ui.integration.widgets.Card), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.integration.widgets.Card). 



</td>
</tr>
<tr>
<td>

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table`, `sap.ui.table.TreeTable`**

The `MultiSelectionPlugin` class is now available: It provides a plugin to support multiple selections in a table. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.table.plugins.MultiSelectionPlugin) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.table.Table/sample/sap.ui.table.sample.MultiSelectionPlugin).



</td>
</tr>
<tr>
<td>

**`sap.uxap.ObjectPageLayout`**

The control header can now be snapped \(collapsed\) and no scroll bar is displayed. This behavior happens when there is only one section with only one subsection and the subsection is marked with the `sapUxAPObjectPageSubSectionFitContainer` CSS class to expand to the full height of the sections container.



</td>
</tr>
</table>

