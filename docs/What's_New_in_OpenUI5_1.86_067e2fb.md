<!-- loio067e2fb0165145a5ac9b128b5853f7c9 -->

| loio |
| -----|
| 067e2fb0165145a5ac9b128b5853f7c9 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/067e2fb0165145a5ac9b128b5853f7c9) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/067e2fb0165145a5ac9b128b5853f7c9)</div>

## What's New in OpenUI5 1.86

With this release OpenUI5 is upgraded from version 1.85 to 1.86.

***

<a name="loio067e2fb0165145a5ac9b128b5853f7c9__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td valign="top">

**Preannouncement: End of Support for Microsoft Internet Explorer 11 after OpenUI5 1.87**

OpenUI5 1.87 will be the last version to support Microsoft Internet Explorer 11. For more information, see [OpenUI5 Support Status for Microsoft Internet Explorer 11](Browser_and_Platform_Support_74b59ef.md#loio74b59efa0eef48988d3b716bd0ecc933__MS_IE).



</td>
</tr>
</table>

***

<a name="loio067e2fb0165145a5ac9b128b5853f7c9__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   A new `unit` property within the `aggregate` map of the `$$aggregation` list binding parameter.

    You can use it to determine the correct currency or unit value for the grand total, as well as subtotals. Note that the name provided for `unit` has to refer to a structural property as well as to a custom aggregate. The custom aggregate has to provide the single value of that unit if there is only one, or `null` if there is more than one distinct value.

-   New `grandTotalAtBottomOnly` and `subtotalsAtBottomOnly` properties in the `$$aggregation` list binding parameter. For more information, see [`sap.ui.model.odata.v4.ODataListBinding#setAggregation`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/setAggregation).
-   You can now filter by properties that are not aggregated when using visual grouping, that is when having `groupLevels` defined in the `$$aggregation` list binding parameter.
-   If the `$$patchWithoutSideEffects` binding parameter is set, `PATCH` requests are now sent out with the `return=minimal` preference in the [`Prefer` header](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part1-protocol/odata-v4.0-errata03-os-part1-protocol-complete.html#_Toc453752234). This allows the server to skip the determination of the response.
-   The `sap.ui.model.odata.v4.ODataListBinding#refresh` method can now handle several kept-alive contexts, and also a kept-alive context that has been deleted in the back end, for example due to a side effect. Note that refreshing dependent bindings relative to the context of a deleted entity will fail as that entity no longer exists.

    A list binding context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.


For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.



</td>
</tr>
</table>

***

<a name="loio067e2fb0165145a5ac9b128b5853f7c9__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.FormattedText`**

We have introduced two ways to set the text direction in the control:

-   The HTML `bdi` tag and the HTML `dir` attribute can now be used in the control.
-   The new `textDirection` property sets the text direction for the root DOM element.

To set the text alignment for the DOM element of the control, you can now use the `textAlign` property.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.FormattedText) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.FormattedText).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.IconTabBar`, `sap.m.RadioButton`**

Value states are not shown when the controls are in read-only or disabled mode. If the controls are set as enabled and editable later, then value states are shown.



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Label`**

The colon symbol \(:\) is represented differently in different languages. In German the colon is followed by a space, in French the colon is preceded by a `U+202F: NARROW NO-BREAK SPACE` character and followed by a space, and in Chinese the character itself is different. The colon symbol used in the control is now dynamically determined, according to which of these languages is used.



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Select`**

With the new experimental `columnRatio` property, you can now set a custom ratio of the columns when you're using a two-column layout for `sap.m.Select`.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Select) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Select/sample/sap.m.sample.Select2Columns).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Table`**

In version 1.85.1 we have added the `Strict` value to the `fixedLayout` property. If this value is set, and the `width` property of `sap.m.Column` is not set to `auto` for any of the columns, the table renders a placeholder column that occupies the remaining width of the control to ensure the column width is strictly applied.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Table/methods/getFixedLayout) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Table/sample/sap.m.sample.TableColumnWidth).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Title`**

We have introduced the `textDirection` property, which is also available in the `sap.m.FormattedText`, `sap.m.Label`, and `sap.m.Text` controls. It allows you to set the text direction to right-to-left \(RTL\) or left-to-right \(LTR\) on a page with mixed-language content. This is important in cases where content from different-direction languages must be shown on the same page. Do not use the `textDirection` property on single-language pages where the direction is centrally determined depending on the language. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Title) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.Title).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   We have introduced a text formatter for texts with placeholders. The text formatter takes a string that contains placeholders and puts values inside these placeholders. Typically the values are translation texts coming from an `i18n` resource bundle. The text formatter allows this replacement to be performed properly for different languages \(each with its own word order\). For more information, see the [Text Formatter](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/formatters/text) section in the Card Explorer.
-   Using the new `showLoadingPlaceholders` and `hideLoadingPlaceholders` methods you can now precisely control the loading-animation placeholders when using Component card or Extension. For example, as a card developer, you can show the loading-animation placeholder when requesting data and hide it when the data is available. These placeholders can be loaded on a section \(for example, `Header`, `Content`, or `Filters`\) or on the whole card. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.integration.widgets.Card) and the [Explore Extension](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/namedDataSection) section in the Card Explorer.



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.layout.form.SemanticFormElement`**

The `SemanticFormElement` element \(experimental\) now allows you to render semantically connected fields separately in edit mode. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.form.SemanticFormElement).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.table.AnalyticalTable, sap.ui.table.Table, sap.ui.table.TreeTable`**

The `rowsUpdated` event is now available so applications can find out about any updates in the tables they are using, for example, if there has been a model update or a user interaction that modified the rows. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.table.Table/events/rowsUpdated).



</td>
</tr>
</table>

***

<a name="loio067e2fb0165145a5ac9b128b5853f7c9__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td valign="top">

**Search Suggestions in Global Search**

We’ve improved the global search functionality in the Demo Kit. Now, when you start typing in the search field, you immediately get a popover with the top ten suggestions that match your keyword. From there, you can pick one suggestion and proceed to the specific page.

If you’re typing in the search field while the page you're currently on is in one of the main categories \(*API Reference*, *Documentation*, or *Samples*\), the top ten search results only display matches that belong to the same category.

To proceed to the page that lists all search results, you can either finish your search by pressing [Enter\], or you can select the *All* button below the top ten search results.

At the bottom of the popover, you have the *Results by Category* section from where you can proceed directly to the chosen search results page \(*API Reference*, *Documentation*, or *Samples*\).

![](loiob35225c0a6b54b4e98852363ed08a0e8_HiRes.gif)



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.95](What's_New_in_OpenUI5_1.95_1b09465.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What's_New_in_OpenUI5_1.94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What's_New_in_OpenUI5_1.93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What's_New_in_OpenUI5_1.92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What's_New_in_OpenUI5_1.91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What's_New_in_OpenUI5_1.90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What's_New_in_OpenUI5_1.89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What's_New_in_OpenUI5_1.88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What's_New_in_OpenUI5_1.87_e315108.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.85](What's_New_in_OpenUI5_1.85_eeb5bd9.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What's_New_in_OpenUI5_1.84_ccf76b7.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What's_New_in_OpenUI5_1.82_f081cf0.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What's_New_in_OpenUI5_1.81_f71563c.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What's_New_in_OpenUI5_1.80_3294c68.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What's_New_in_OpenUI5_1.79_edf8e35.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What's_New_in_OpenUI5_1.78_d176be3.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What's_New_in_OpenUI5_1.77_2ec6b6b.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What's_New_in_OpenUI5_1.76_b9b0a3f.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What's_New_in_OpenUI5_1.75_dc3d3ce.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What's_New_in_OpenUI5_1.74_21fc6cb.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What's_New_in_OpenUI5_1.73_7b82664.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What's_New_in_OpenUI5_1.72_25e5326.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What's_New_in_OpenUI5_1.71_609fd01.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What's_New_in_OpenUI5_1.70_4e89fee.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What's_New_in_OpenUI5_1.69_41203fd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What's_New_in_OpenUI5_1.68_5531aef.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What's_New_in_OpenUI5_1.67_0968958.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What's_New_in_OpenUI5_1.66_ebe7fda.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What's_New_in_OpenUI5_1.65_9d2b189.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What's_New_in_OpenUI5_1.64_1975e30.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What's_New_in_OpenUI5_1.63_77e1dcc.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What's_New_in_OpenUI5_1.62_27eea38.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What's_New_in_OpenUI5_1.61_de4d50b.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What's_New_in_OpenUI5_1.60_2a70354.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What's_New_in_OpenUI5_1.58_b28edde.md "With this release, OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What's_New_in_OpenUI5_1.56_53b4b5e.md "With this release, OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What's_New_in_OpenUI5_1.54_f29023e.md "With this release, OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What's_New_in_OpenUI5_1.52_a09dd79.md "With this release, OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What's_New_in_OpenUI5_1.50_a844984.md "With this release, OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What's_New_in_OpenUI5_1.48_2818f80.md "With this release, OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What's_New_in_OpenUI5_1.46_4cf0986.md "With this release, OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What's_New_in_OpenUI5_1.44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What's_New_in_OpenUI5_1.42_4768f1a.md "With this release, OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What's_New_in_OpenUI5_1.40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What's_New_in_OpenUI5_1.38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

