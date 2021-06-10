<!-- loio75777daa78734f2db4e4c8a8124c0644 -->

| loio |
| -----|
| 75777daa78734f2db4e4c8a8124c0644 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/75777daa78734f2db4e4c8a8124c0644) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/75777daa78734f2db4e4c8a8124c0644)</div>

## What's New in OpenUI5 1.91

With this release OpenUI5 is upgraded from version 1.90 to 1.91.

***

<a name="loio75777daa78734f2db4e4c8a8124c0644__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

**OpenUI5 OData V2 Model**

A `Content-ID` header has been added to all non-read requests in a batch request. For failing change sets, the `Content-ID` of individual messages in the error response is used to map the message to the correct request. This allows you to calculate the correct target.



</td>
</tr>
<tr>
<td>

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   For a list binding with visual grouping, that is with a `groupLevels` list provided in the `$$aggregation` binding parameter, you can now request the `$count` parameter. The resulting count represents the number of records at the leaf level. The `$count` parameter can be accessed through the header context as described in [Binding Collection Inline Count](Binding_Collection_Inline_Count_77d2310.md).

-   We now provide a new [`sap.ui.model.odata.v4.ODataListBinding#getCount`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/getCount) method that allows you to get the count of elements or leaves in your collection.




</td>
</tr>
</table>

***

<a name="loio75777daa78734f2db4e4c8a8124c0644__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td>

**`sap.m.App`**

Until now, `sap.m.App` assumed that it wasn't nested and always appeared as the top-level root DOM element for apps. With the new `isTopLevel` property, you can now disable this behavior for different use cases, such as, nested components and standalone usage.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.App).



</td>
</tr>
<tr>
<td>

**`sap.m.ExpandableText`**

Тhe control now also implements the new `emptyIndicatorMode` property. It allows developers to display an empty text as a language dependent “-” symbol. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ExpandableText).



</td>
</tr>
<tr>
<td>

**`sap.m.Table`**

We introduced the `ColumnResizer` plugin that handles column resizing for a responsive table.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.plugins.ColumnResizer%23methods/Summary).



</td>
</tr>
</table>

***

<a name="loio75777daa78734f2db4e4c8a8124c0644__section_z2h_fh5_zcb"/>

### Documentation


<table>
<tr>
<td>

We have enhanced the existing documentation for the `sap.m.Table` control and related entities with details about column width handling, such as the strict layout and the pop-in feature.

For more information, see [Configuring Responsive Behavior of a Table](Configuring_Responsive_Behavior_of_a_Table_38855e0.md), [Defining Column Width](Defining_Column_Width_6f778a8.md), and [Table Design](Table_Design_d3234bc.md).



</td>
</tr>
</table>

