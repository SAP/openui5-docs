<!-- loio4c1c95953602429798faec98065f2096 -->

# What's New in OpenUI5 1.86

With this release OpenUI5 is upgraded from version 1.85 to 1.86.



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

1.86 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Announcement 

</td>
<td valign="top">

**Preannouncement: End of Support for Microsoft Internet Explorer 11 after OpenUI5 1.87** 

</td>
<td valign="top">

**Preannouncement: End of Support for Microsoft Internet Explorer 11 after OpenUI5 1.87**

OpenUI5 1.87 will be the last version to support Microsoft Internet Explorer 11. For more information, see [OpenUI5 Support Status for Microsoft Internet Explorer 11](../02_Read-Me-First/browser-and-platform-support-74b59ef.md#loio74b59efa0eef48988d3b716bd0ecc933__MS_IE).

<sub>Deprecated•Announcement•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

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

-   A new `unit` property within the `aggregate` map of the `$$aggregation` list binding parameter.

    You can use it to determine the correct currency or unit value for the grand total, as well as subtotals. Note that the name provided for `unit` has to refer to a structural property as well as to a custom aggregate. The custom aggregate has to provide the single value of that unit if there is only one, or `null` if there is more than one distinct value.

-   New `grandTotalAtBottomOnly` and `subtotalsAtBottomOnly` properties in the `$$aggregation` list binding parameter. For more information, see [`sap.ui.model.odata.v4.ODataListBinding#setAggregation`](https://ui5.sap.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/setAggregation).
-   You can now filter by properties that are not aggregated when using visual grouping, that is when having `groupLevels` defined in the `$$aggregation` list binding parameter.
-   If the `$$patchWithoutSideEffects` binding parameter is set, `PATCH` requests are now sent out with the `return=minimal` preference in the [`Prefer` header](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part1-protocol/odata-v4.0-errata03-os-part1-protocol-complete.html#_Toc453752234). This allows the server to skip the determination of the response.
-   The `sap.ui.model.odata.v4.ODataListBinding#refresh` method can now handle several kept-alive contexts, and also a kept-alive context that has been deleted in the back end, for example due to a side effect. Note that refreshing dependent bindings relative to the context of a deleted entity will fail as that entity no longer exists.

    A list binding context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.


For more information, see [OData V4 Model](../04_Essentials/odata-v4-model-5de13cf.md), the [API Reference](https://ui5.sap.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://ui5.sap.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

<sub>Changed•Feature•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.FormattedText`** 

</td>
<td valign="top">

**`sap.m.FormattedText`**

We have introduced two ways to set the text direction in the control:

-   The HTML `bdi` tag and the HTML `dir` attribute can now be used in the control.
-   The new `textDirection` property sets the text direction for the root DOM element.

To set the text alignment for the DOM element of the control, you can now use the `textAlign` property.

For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.FormattedText) and the [Samples](https://ui5.sap.com/#/entity/sap.m.FormattedText).

<sub>Changed•Control•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.IconTabBar`, `sap.m.RadioButton`** 

</td>
<td valign="top">

**`sap.m.IconTabBar`, `sap.m.RadioButton`**

Value states are not shown when the controls are in read-only or disabled mode. If the controls are set as enabled and editable later, then value states are shown.

<sub>Changed•Control•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

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

The colon symbol \(:\) is represented differently in different languages. In German the colon is followed by a space, in French the colon is preceded by a `U+202F: NARROW NO-BREAK SPACE` character and followed by a space, and in Chinese the character itself is different. The colon symbol used in the control is now dynamically determined, according to which of these languages is used.

<sub>Changed•Control•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Select`** 

</td>
<td valign="top">

**`sap.m.Select`**

With the new experimental `columnRatio` property, you can now set a custom ratio of the columns when you're using a two-column layout for `sap.m.Select`.For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.Select) and the [Sample](https://ui5.sap.com/#/entity/sap.m.Select/sample/sap.m.sample.Select2Columns).

<sub>Changed•Control•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

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

In version 1.85.1 we have added the `Strict` value to the `fixedLayout` property. If this value is set, and the `width` property of `sap.m.Column` is not set to `auto` for any of the columns, the table renders a placeholder column that occupies the remaining width of the control to ensure the column width is strictly applied.

For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.Table/methods/getFixedLayout) and the [Sample](https://ui5.sap.com/#/entity/sap.m.Table/sample/sap.m.sample.TableColumnWidth).

<sub>Changed•Control•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

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

We have introduced the `textDirection` property, which is also available in the `sap.m.FormattedText`, `sap.m.Label`, and `sap.m.Text` controls. It allows you to set the text direction to right-to-left \(RTL\) or left-to-right \(LTR\) on a page with mixed-language content. This is important in cases where content from different-direction languages must be shown on the same page. Do not use the `textDirection` property on single-language pages where the direction is centrally determined depending on the language. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.m.Title) and the [Samples](https://ui5.sap.com/#/entity/sap.m.Title).

<sub>Changed•Control•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

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

-   We have introduced a text formatter for texts with placeholders. The text formatter takes a string that contains placeholders and puts values inside these placeholders. Typically the values are translation texts coming from an `i18n` resource bundle. The text formatter allows this replacement to be performed properly for different languages \(each with its own word order\). For more information, see the [Text Formatter](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/formatters/text) section in the Card Explorer.
-   Using the new `showLoadingPlaceholders` and `hideLoadingPlaceholders` methods you can now precisely control the loading-animation placeholders when using Component card or Extension. For example, as a card developer, you can show the loading-animation placeholder when requesting data and hide it when the data is available. These placeholders can be loaded on a section \(for example, `Header`, `Content`, or `Filters`\) or on the whole card. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.ui.integration.widgets.Card) and the [Explore Extension](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension/namedDataSection) section in the Card Explorer.

<sub>Changed•Control•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.layout.form.SemanticFormElement`** 

</td>
<td valign="top">

**`sap.ui.layout.form.SemanticFormElement`**

The `SemanticFormElement` element \(experimental\) now allows you to render semantically connected fields separately in edit mode. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.ui.layout.form.SemanticFormElement).

<sub>Changed•Control•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

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

The `rowsUpdated` event is now available so applications can find out about any updates in the tables they are using, for example, if there has been a model update or a user interaction that modified the rows. For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.ui.table.Table/events/rowsUpdated).

<sub>Changed•Control•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
<tr>
<td valign="top">

1.86 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Demo Kit Search Suggestions in Global Search** 

</td>
<td valign="top">

**Demo Kit Search Suggestions in Global Search**

We’ve improved the global search functionality in the Demo Kit. Now, when you start typing in the search field, you immediately get a popover with the top ten suggestions that match your keyword. From there, you can pick one suggestion and proceed to the specific page.

If you’re typing in the search field while the page you're currently on is in one of the main categories \(*API Reference*, *Documentation*, or *Samples*\), the top ten search results only display matches that belong to the same category.

To proceed to the page that lists all search results, you can either finish your search by pressing [Enter\], or you can select the *All* button below the top ten search results.

At the bottom of the popover, you have the *Results by Category* section from where you can proceed directly to the chosen search results page \(*API Reference*, *Documentation*, or *Samples*\).

![](images/WN1_86_Demo_Kit_Search_Suggestions_b35225c.gif)

<sub>Changed•Feature•Info Only•1.86</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2021-01-28

</td>
</tr>
</table>

**Related Information**  


[What's New in OpenUI5 1.133](what-s-new-in-openui5-1-133-86d7605.md "With this release OpenUI5 is upgraded from version 1.132 to 1.133.")

[What's New in OpenUI5 1.132](what-s-new-in-openui5-1-132-bd2e61f.md "With this release OpenUI5 is upgraded from version 1.131 to 1.132.")

[What's New in OpenUI5 1.131](what-s-new-in-openui5-1-131-7d24d94.md "With this release OpenUI5 is upgraded from version 1.130 to 1.131.")

[What's New in OpenUI5 1.130](what-s-new-in-openui5-1-130-85609d4.md "With this release OpenUI5 is upgraded from version 1.129 to 1.130.")

[What's New in OpenUI5 1.129](what-s-new-in-openui5-1-129-d22b8af.md "With this release OpenUI5 is upgraded from version 1.128 to 1.129.")

[What's New in OpenUI5 1.128](what-s-new-in-openui5-1-128-1f76220.md "With this release OpenUI5 is upgraded from version 1.127 to 1.128.")

[What's New in OpenUI5 1.127](what-s-new-in-openui5-1-127-e5e1317.md "With this release OpenUI5 is upgraded from version 1.126 to 1.127.")

[What's New in OpenUI5 1.126](what-s-new-in-openui5-1-126-1d98116.md "With this release OpenUI5 is upgraded from version 1.125 to 1.126.")

[What's New in OpenUI5 1.125](what-s-new-in-openui5-1-125-9d87044.md "With this release OpenUI5 is upgraded from version 1.124 to 1.125.")

[What's New in OpenUI5 1.124](what-s-new-in-openui5-1-124-7f77c3f.md "With this release OpenUI5 is upgraded from version 1.123 to 1.124.")

[What's New in OpenUI5 1.123](what-s-new-in-openui5-1-123-9d00ac7.md "With this release OpenUI5 is upgraded from version 1.122 to 1.123.")

[What's New in OpenUI5 1.122](what-s-new-in-openui5-1-122-5d078da.md "With this release OpenUI5 is upgraded from version 1.121 to 1.122.")

[What's New in OpenUI5 1.121](what-s-new-in-openui5-1-121-91a4a2f.md "With this release OpenUI5 is upgraded from version 1.120 to 1.121.")

[What's New in OpenUI5 1.120](what-s-new-in-openui5-1-120-2359b63.md "With this release OpenUI5 is upgraded from version 1.119 to 1.120.")

[What's New in OpenUI5 1.119](what-s-new-in-openui5-1-119-0b1903a.md "With this release OpenUI5 is upgraded from version 1.118 to 1.119.")

[What's New in OpenUI5 1.118](what-s-new-in-openui5-1-118-3eecbde.md "With this release OpenUI5 is upgraded from version 1.117 to 1.118.")

[What's New in OpenUI5 1.117](what-s-new-in-openui5-1-117-029d3b4.md "With this release OpenUI5 is upgraded from version 1.116 to 1.117.")

[What's New in OpenUI5 1.116](what-s-new-in-openui5-1-116-ebd6f34.md "With this release OpenUI5 is upgraded from version 1.115 to 1.116.")

[What's New in OpenUI5 1.115](what-s-new-in-openui5-1-115-409fde8.md "With this release OpenUI5 is upgraded from version 1.114 to 1.115.")

[What's New in OpenUI5 1.114](what-s-new-in-openui5-1-114-890fce1.md "With this release OpenUI5 is upgraded from version 1.113 to 1.114.")

[What's New in OpenUI5 1.113](what-s-new-in-openui5-1-113-a9553fe.md "With this release OpenUI5 is upgraded from version 1.112 to 1.113.")

[What's New in OpenUI5 1.112](what-s-new-in-openui5-1-112-34afc69.md "With this release OpenUI5 is upgraded from version 1.111 to 1.112.")

[What's New in OpenUI5 1.111](what-s-new-in-openui5-1-111-7a67837.md "With this release OpenUI5 is upgraded from version 1.110 to 1.111.")

[What's New in OpenUI5 1.110](what-s-new-in-openui5-1-110-71a855c.md "With this release OpenUI5 is upgraded from version 1.109 to 1.110.")

[What's New in OpenUI5 1.109](what-s-new-in-openui5-1-109-3264bd2.md "With this release OpenUI5 is upgraded from version 1.108 to 1.109.")

[What's New in OpenUI5 1.108](what-s-new-in-openui5-1-108-66e33f0.md "With this release OpenUI5 is upgraded from version 1.107 to 1.108.")

[What's New in OpenUI5 1.107](what-s-new-in-openui5-1-107-d4ff916.md "With this release OpenUI5 is upgraded from version 1.106 to 1.107.")

[What's New in OpenUI5 1.106](what-s-new-in-openui5-1-106-5b497b0.md "With this release OpenUI5 is upgraded from version 1.105 to 1.106.")

[What's New in OpenUI5 1.105](what-s-new-in-openui5-1-105-4d6c00e.md "With this release OpenUI5 is upgraded from version 1.104 to 1.105.")

[What's New in OpenUI5 1.104](what-s-new-in-openui5-1-104-69e567c.md "With this release OpenUI5 is upgraded from version 1.103 to 1.104.")

[What's New in OpenUI5 1.103](what-s-new-in-openui5-1-103-0e98c76.md "With this release OpenUI5 is upgraded from version 1.102 to 1.103.")

[What's New in OpenUI5 1.102](what-s-new-in-openui5-1-102-f038c99.md "With this release OpenUI5 is upgraded from version 1.101 to 1.102.")

[What's New in OpenUI5 1.101](what-s-new-in-openui5-1-101-7733b00.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](what-s-new-in-openui5-1-100-27dec1d.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](what-s-new-in-openui5-1-99-4f35848.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](what-s-new-in-openui5-1-98-d9f16f2.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](what-s-new-in-openui5-1-97-fa0e282.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](what-s-new-in-openui5-1-96-7a9269f.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](what-s-new-in-openui5-1-95-a1aea67.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](what-s-new-in-openui5-1-94-c40f1e6.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](what-s-new-in-openui5-1-93-f273340.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](what-s-new-in-openui5-1-92-1ef345d.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](what-s-new-in-openui5-1-91-0a2bd79.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](what-s-new-in-openui5-1-90-91c10c2.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](what-s-new-in-openui5-1-89-e56cddc.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](what-s-new-in-openui5-1-88-e15a206.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](what-s-new-in-openui5-1-87-b506da7.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.85](what-s-new-in-openui5-1-85-1d18eb5.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](what-s-new-in-openui5-1-84-dc76640.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](what-s-new-in-openui5-1-82-3a8dd13.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](what-s-new-in-openui5-1-81-f5e2a21.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](what-s-new-in-openui5-1-80-8cee506.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](what-s-new-in-openui5-1-79-99c4cdc.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](what-s-new-in-openui5-1-78-f09b63e.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](what-s-new-in-openui5-1-77-c46b439.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](what-s-new-in-openui5-1-76-aad03b5.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](what-s-new-in-openui5-1-75-5cbb62d.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](what-s-new-in-openui5-1-74-c22208a.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](what-s-new-in-openui5-1-73-231dd13.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](what-s-new-in-openui5-1-72-521cad9.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](what-s-new-in-openui5-1-71-a93a6a3.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](what-s-new-in-openui5-1-70-f073d69.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](what-s-new-in-openui5-1-69-89a18bd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](what-s-new-in-openui5-1-68-f94bf93.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](what-s-new-in-openui5-1-67-a6b1472.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](what-s-new-in-openui5-1-66-c9896e9.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](what-s-new-in-openui5-1-65-0f5acfd.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](what-s-new-in-openui5-1-64-0e30822.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](what-s-new-in-openui5-1-63-e8d9da7.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](what-s-new-in-openui5-1-62-771f4d5.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](what-s-new-in-openui5-1-61-d991552.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](what-s-new-in-openui5-1-60-5a0e1f7.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](what-s-new-in-openui5-1-58-7c927aa.md "With this release OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](what-s-new-in-openui5-1-56-108b7fd.md "With this release OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](what-s-new-in-openui5-1-54-c838330.md "With this release OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](what-s-new-in-openui5-1-52-849e1b6.md "With this release OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](what-s-new-in-openui5-1-50-759e9f3.md "With this release OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](what-s-new-in-openui5-1-48-fa1efac.md "With this release OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](what-s-new-in-openui5-1-46-6307539.md "With this release OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](what-s-new-in-openui5-1-44-a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](what-s-new-in-openui5-1-42-468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](what-s-new-in-openui5-1-40-fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](what-s-new-in-openui5-1-38-f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

