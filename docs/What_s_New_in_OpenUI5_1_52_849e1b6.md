<!-- loio849e1b678d324d129a84446d9c2841fb -->

| loio |
| -----|
| 849e1b678d324d129a84446d9c2841fb |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/849e1b678d324d129a84446d9c2841fb) | [demo kit latest release](https://sdk.openui5.org/topic/849e1b678d324d129a84446d9c2841fb)</div>

## What's New in OpenUI5 1.52

With this release OpenUI5 is upgraded from version 1.50 to 1.52.

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

1.52 

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

You can now optimize dependent bindings in OData V2 models. The OData V2 model now supports a `preliminaryContext` flag. When set to `true`, the OData model can bundle the OData calls for dependent bindings into fewer `$batch` requests. Two bindings are considered dependent if one cannot be resolved without the other being resolved first. For example, a relative binding cannot be resolved without a resolved absolute binding.

<sub>Changed•Feature•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

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

The new version of the OpenUI5 The OData V4 model has the following features:

-   Handling of `Edm.Stream` in read-only mode

-   Possibility to declare several batch groups as `$auto` or `$direct`

-   Enhancements to the adapter to use the V4 model with an OData V2 service: handling of simple `$filter` expressions


> ### Caution:  
> **Incompatibility Due to a Bug Fix**
> 
> If you call the [sap.ui.model.odata.v4.Context\#getObject\(\)](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/getObject) or the [sap.ui.model.odata.v4.Context\#requestObject\(\)](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/requestObject) methods without a parameter, the expected and documented behavior is that the same result is returned as if the parameter `sPath=""` had been specified. However, due to a bug, the return value wraps the expected output and can only be accessed using `.value[0]`, for example `oContext.getObject().value[0]`.
> 
> **If you have used this workaround, your application will break as of OpenUI5 version 1.44.6.**
> 
> **Solution**: If your application needs to run with both the fixed and unfixed versions of OpenUI5, specify the `sPath=""` parameter, for the `sPath` parameter. In both cases, you **must not** use the `.value[0]`workaround any more.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [sample](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

<sub>Changed•Feature•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Support Assistant** 

</td>
<td valign="top">

**Support Assistant**

Support Assistant has been enhanced with the following features:

![](images/loio43f74fa14f8a4cfc82c0e31998072d6b_LowRes.png)

-   Additional rule property *Async*

    The default value of this property is `false`. If you set it to `true`, a resolve function is passed as a parameter of the check function to allow you to resolve the asynchronous operation. Call `fnResolve` to indicate that the asynchronous check function has finished. The asynchronous function waits 10 seconds before it times out.

-   New options to check the location from which Support Assistant has been loaded:

    -   When you click the *Settings* button in the Support Assistant toolbar, you can see the URL at the bottom of the dialog box. A *Copy* button next to the URL allows you to copy the location to the clipboard.

    -   In the *Technical Information* section of the report.


-   Displaying issues and their severity

    After an analysis run, you can see how many issues of each severity have been reported for each library. This information is also available for the individual rules. In the *Details* section for each rule, you can see a severity icon for each issue generated by that rule.

    ![](images/loioefd9a332c5fe479183f03828938e2cf2_HiRes.png)


<sub>Changed•Feature•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.DynamicPage`** 

</td>
<td valign="top">

**`sap.f.DynamicPage`**

-   Additional visual indicators \(arrow buttons\) are now available. They are positioned either below the header \(when the header is expanded\) or below the title \(when the header is collapsed\). The expanded/collapsed state of the header can be toggled by clicking on the title or the arrow buttons. Both areas get a darker color when hovering over them. For more information, see the [sample](https://sdk.openui5.org/sample/sap.f.sample.DynamicPageFreeStyle/preview).

-   A new area, designated for breadcrumb navigation, has been introduced at the top-left area of the title of the page. It is enabled with the new `breadcrumbs` aggregation \(type `sap.m.IBreadcrumbs`\) that belongs to `sap.f.DynamicPageTitle`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPageTitle) and the [sample](https://sdk.openui5.org/sample/sap.f.sample.DynamicPageFreeStyle/preview).

-   The `sap.f.DynamicPageTitle` has a new `navigationActions` aggregation, which is meant for buttons with navigation semantics, such as *Close*, *Full screen*, and *Exit full screen*. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPageTitle) and the [sample](https://sdk.openui5.org/sample/sap.f.sample.DynamicPageFreeStyle/preview).

-   The `sap.f.DynamicPageTitle` has two new aggregations: `expandedHeading` and `snappedHeading`. They enable the app to display different content in the heading for the expanded and collapsed states of the header. The previous `heading` aggregation is not deprecated and works as a replacement for the new ones. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPageTitle).


<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

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

-   The control has a new `titleContent` aggregation and `titlePrimaryArea` property. The aggregation allows you as an app developer to place content in the middle of the title area, displayed in both expanded and collapsed \(snapped\) states of the header. The property determines which of the title areas \(`Begin`, `Middle`\) is primary \(shrinking at a lower rate, remaining visible as long as it can\). For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.semantic.SemanticPage) and the [sample](https://sdk.openui5.org/sample/sap.f.sample.SemanticPageFreeStyle/preview).

-   The new `navigationActions` aggregation that belongs to the `sap.f.DynamicPageTitle` is now utilized when using the `closeAction`, `fullScreenAction`, and `exitFullScreenAction` aggregations of the `SemanticPage`. The content added in the aggregations is automatically positioned in the title in an ordered way. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPageTitle).


<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.CheckBox`** 

</td>
<td valign="top">

**`sap.m.CheckBox`**

A new `useEntireWidth` Boolean property determines whether the value set for the `width` property applies to the whole control or to the control label only. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.CheckBox).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.DateRangeSelection`** 

</td>
<td valign="top">

**`sap.m.DateRangeSelection`**

The binding is improved and the control now supports date intervals. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DateRangeSelection).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.FeedListItem`** 

</td>
<td valign="top">

**`sap.m.FeedListItem`**

**`sap.m.FeedListItem`** provides new actions for defining additional features. You can find the features in an `sap.m.ActionSheet` when you press the *Action* button. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.FeedListItemAction).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MessagePage`** 

</td>
<td valign="top">

**`sap.m.MessagePage`**

A new `iconAlt` property has been introduced. It enables the setting of an `alt` attribute for the icon displayed on the `sap.m.MessagePage`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MessagePage).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

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

**`sap.m.MessageView`** has new default behavior and a new property. These changes aim to save space on the screen and hide unnecessary controls.

-   If only one item is available, the details page for the first item is used as the initial page after opening a `MessagePopover` or rendering a `MessageView`.

-   If there are messages of only one type, the filtering options in the header will be hidden.

-   A new `showDetailsPageHeader` Boolean property for hiding the details page header has been introduced. When set to `false`, no header will be displayed in the details section of the message.


For more information, see the [Sample](https://sdk.openui5.org/sample/sap.m.sample.MessageViewInsideDialog/preview). 

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.OverflowToolbar`** 

</td>
<td valign="top">

**`sap.m.OverflowToolbar`**

Until now, controls needed to be whitelisted in a central helper class to be allowed to move to the overflow menu. With the addition of the new `sap.m.IOverflowToolbarContent` interface, each control can now provide this data on its own, without needing to be whitelisted. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IOverflowToolbarContent).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

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

There is a new `showWeekNumbers` property that enables the display of the calendar week numbers. They are available for the *Days*, *1 Week*, and *1 Month* views of the `sap.m.PlanningCalendar`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar) and the [sample](https://sdk.openui5.org/sample/sap.m.sample.PlanningCalendar/preview).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.QuickView`** 

</td>
<td valign="top">

**`sap.m.QuickView`**

**`sap.m.QuickView`** has new default behavior. When the *QuickView* is only one page, and when no header is set, the header is no longer rendered. For more information, see the [Sample](https://sdk.openui5.org/sample/sap.m.sample.QuickView/preview).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.RatingIndicator`** 

</td>
<td valign="top">

**`sap.m.RatingIndicator`**

**`sap.m.RatingIndicator`** has a new `editable` property. When set to `true`, the control can be edited and you can rate using the icons. When set to `false`, the rating indicator is presented in a non-interactive mode and can be used, for example, to visualize an aggregated rating score.

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.SegmentedButton`** 

</td>
<td valign="top">

**`sap.m.SegmentedButton`**

After the `buttons` aggregation was deprecated in version 1.28, both the `select` event and `selectedButton` association are no longer useful for the recommended `items` aggregation. For this reason, the `select` event and `selectedButton` association are deprecated as of version 1.52 and are replaced by new ones - the `selectionChange` event and the `selectedItem` association. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SegmentedButton) and the [sample](https://sdk.openui5.org/sample/sap.m.sample.SegmentedButton/preview).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Table` and `sap.ui.table.Table`** 

</td>
<td valign="top">

**`sap.m.Table` and `sap.ui.table.Table`**

Alternate row styling is now supported with the new `alternateRowColors` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Table/overview) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.TableAlternateRowColors/preview) for `sap.m.Table` and the [API Reference](https://sdk.openui5.org/api/sap.ui.table.Table/overview) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.TableAlternateRowColors/preview) for `sap.ui.table.Table`. 

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

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

A new `popinLayout` property has been added that defines the layout for pop-in rows. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Table/controlProperties) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.Table/preview).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Text`** 

</td>
<td valign="top">

**`sap.m.Text`**

**`sap.m.Text`** has a new `renderWhitespace` property. It specifies the rendering of whitespace characters \(`“ “`\) and tabs \(`\t`\) inside the control. The default value is `false`. If set to `true`, the browser preserves whitespace characters and tabs. Line breaks \(`\r\n`, `\n\r`, `\r`, `\n`\) are always visualized unless the `wrapping` property is set to `false`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Text) and the [Samples](https://sdk.openui5.org/sample/sap.m.sample.TextRenderWhitespace/preview).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Title`** 

</td>
<td valign="top">

**`sap.m.Title`**

**`sap.m.Title`** has a new `wrapping` property. It determines if the title will be wrapped. The default value is `false`. If set to `true`, the entire title is wrapped. You should only activate the wrapping if the surrounding container allows flexible heights. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Title/methods/setWrapping) and the [Samples](https://sdk.openui5.org/sample/sap.m.sample.TitleWrapping/preview).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.tnt.NavigationList` and `sap.tnt.SideNavigation`** 

</td>
<td valign="top">

**`sap.tnt.NavigationList` and `sap.tnt.SideNavigation`**

**`sap.tnt.NavigationList`** and **`sap.tnt.SideNavigation`** have a new `selectedItem` association. It allows you to specify which `NavigationListItem` will be selected when you load the page and enables you to change the selected *Menu* item using the code. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.tnt.SideNavigation) and the [Samples](https://sdk.openui5.org/sample/sap.tnt.sample.SideNavigation/preview).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.tnt.NavigationListItem`** 

</td>
<td valign="top">

**`sap.tnt.NavigationListItem`**

`sap.tnt.NavigationListItem` has a new `visible` property. It allows you to choose if a `NavigationListItem` will be rendered in the `NavigationList` or not. By default it is set to `true`.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.tnt.NavigationListItem) and the [Samples](https://sdk.openui5.org/sample/sap.tnt.sample.NavigationList/preview).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.table.Table`** 

</td>
<td valign="top">

**`sap.ui.table.Table`**

You can now use drag and drop for table rows with aggregation `dragDropConfig`. For more information, see the [API Reference for the `dragDropConfig` aggregation](https://sdk.openui5.org/api/sap.ui.table.Table/aggregations), the [API Reference for `sap.ui.core.dnd`](https://sdk.openui5.org/api/sap.ui.core.dnd), the [Sample for `TreeTable`](https://sdk.openui5.org/sample/sap.ui.table.sample.TreeTable.HierarchyMaintenanceJSONTreeBinding/preview) and the [Sample for `Table`](https://sdk.openui5.org/sample/sap.ui.table.sample.DnD/preview).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

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

-   A new `valueStateText` property has been introduced to enable the display of custom messages when a `valueState` is set. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.FileUploader).

-   The new `xhrSettings` aggregation allows app developers to specify settings for the internally used `XMLHttpRequest` object when uploading files with `sendXHR=true`. Currently the only supported setting is `withCredentials`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.FileUploader).

-   A new `sap.ui.unified.IProcessableBlobs` interface has been implemented and `sap.ui.unified.FileUploader` has been updated to use it. It facilitates the implementation of custom controls that extend the `sap.ui.unified.FileUploader`, for example, to modify the files before they get uploaded. To enable the feature, you need to set the `bPreProcessFiles` parameter of the `upload` method to `true`. As a result, the method becomes asynchronous. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.IProcessableBlobs).


<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

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

**`sap.uxap.ObjectPageLayout`** now contains a new type of header. The new header is flexible and dynamic as opposed to the classic header that has a specific and predefined layout. To implement the new dynamic header, the app should provide an instance of the new `sap.uxap.ObjectPageDynamicHeaderTitle` control as the value of the `headerTitle` aggregation.

With the new dynamic header the following features are available:

-   General-purpose aggregations instead of semantic properties that allow you to build a custom header layout

-   An arrow button displayed below the header content and visual indicators when hovering over the title and the arrow button

-   The title and the arrow button can be clicked to expand or collapse the header

-   A pin button allowing the header to remain expanded when scrolling the page or clicking/tapping the title

-   `sap.m.OverflowToolbar` is used internally to implement the `actions` aggregation, enabling its features, such as the priority and grouping of the actions.


For more information, see [Object Page Headers](Object_Page_Headers_d2ef009.md), the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageDynamicHeaderTitle), and the [sample](https://sdk.openui5.org/sample/sap.uxap.sample.ObjectPageWithDynamicHeader/preview).

<sub>Changed•Control•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

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

A big thank you to everyone who sent us valuable feedback from many different channels. We are working hard to implement your suggestions.

With this version, we have improved the performance of the Demo Kit app, enhanced link handling and scrolling, improved quality, solved many issues, and added several new features:

**General**

-   Compact display mode is always used so that white space is utilized better for all devices.

-   Link processing is improved and links can be opened in a new browser tab.

-   Performance is improved for initial loading, deep linking, and the *API Reference*.

-   Busy indicators are added.

-   The error pages are improved and new ones are added.

-   Global search: Clicking the magnifier icon puts the focus on the search field.

-   Visualization of search results on small screens is improved.


**Documentation**

-   The root level node of the documentation tree is removed to improve usability.

-   The documentation can be downloaded in PDF format from the *Download* button on the landing page of the *Documentation* section.


**API Reference**

White spaces are decreased, contrast between the background and the tables is increased, and the structure of the content is improved.

-   The URL hash \(\#\) is updated when selecting sections and subsections and while scrolling through the page sections.

-   Thrown exceptions are displayed.

-   The following information is displayed in the header:

    -   Cross links to *Documentation* are added.

    -   Abstract classes are displayed in front of the class name.

    -   Known direct subclasses and known direct implementations are displayed. If there is more than one instance, they are visualized in a popover.

    -   Class visibility information is added.

    -   Library information for a certain namespace is added.



**Samples**

-   The cross-links between *Samples* and *API Reference* are more prominent.
-   *About* sections with descriptions are added for the tutorial samples.

**Tools**

We added a new *Tools* section in the main navigation after the *Demo Apps* section. It contains documentation and quick navigation to different OpenUI5 tools, such as SAP Web IDE, UI5 Inspector, the icon explorer, the theme parameter toolbox, UI theme designer, and Build.

> ### Note:  
> The icon explorer and the theme parameter toolbox were moved from *Demo Apps* to the *Tools* section.

<sub>Changed•Feature•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
<tr>
<td valign="top">

1.52 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

User Documentation 

</td>
<td valign="top">

**Documentation and Templates** 

</td>
<td valign="top">

**Documentation and Templates**

Check out the following new and updated documentation topics:

-   [Test Automation](Test_Automation_ae44824.md#loioae448243822448d8ba04b4784f4b09a0) that describes the setup for automated testing with *Karma*

-   [Continuous Integration: Ensure Code Quality](Continuous_Integration_Ensure_Code_Quality_fe7a158.md)

-   [Performance: Speed Up Your App](Performance_Speed_Up_Your_App_408b40e.md)


Our tutorials and templates have been updated according to the latest practices:


<table>
<tr>
<th valign="top">

Change

</th>
<th valign="top">

Why?

</th>
</tr>
<tr>
<td valign="top">

IDs added:

-   Component ID in all HTML pages that instantiate a UI component manually

    ```
    new ComponentContainer({
       height : "100%",
       name : "sap.ui.demo.worklist",
       settings : {
          id : "worklist"
       }
    })
    
    ```

-   IDs for targets in the routing configuration in the `manifest.json` descriptor file




</td>
<td valign="top">

Unique IDs are necessary for many tools and testing scenarios. If there is no ID specified for an object, it gets a generated ID.

For components, this can be confusing in scenarios in which more than one component is being used.

For target IDs, this leads to unpredictable view IDs as the views are generated by the router in the sequence in which they are called.

</td>
</tr>
<tr>
<td valign="top">

Asynchronous processing added:

-   In the routing configuration in the `manifest.json` descriptor files

-   Loading of the `rootView` in the `manifest.json` descriptor files

-   Loading of the `rootView` in the `Component.js` files

    ```
    rootView : {
                    viewName: "sap.m.sample.ActionListItem.List",
                    type: "XML",
                    async: true,
                    id: "app"
    }
    
    ```




</td>
<td valign="top">

Asynchronous loading of views \(or any resources\) can be faster in modern browsers. The browser can load resources in parallel without freezing the UI. So this may improve the performance and user experience.

> ### Note:  
> There are rules in the support assistant that check for asynchronous loading.



</td>
</tr>
<tr>
<td valign="top">

`getView().byId` replaced by `byId` on all controller files

</td>
<td valign="top">

It is shorter, hence easier to read and type. It even makes writing some unit tests easier because developers do not need to “stub” the `getView()` method.

</td>
</tr>
<tr>
<td valign="top">

Namespace of the Walkthrough tutorial renamed from `wt` to `walkthrough` 

</td>
<td valign="top">

Long namespaces can make resource paths pretty long, so this is easier to understand.

</td>
</tr>
</table>

<sub>Changed•User Documentation•Info Only•1.52</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-01-18

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_759e9f3.md "With this release OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_fa1efac.md "With this release OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_6307539.md "With this release OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

