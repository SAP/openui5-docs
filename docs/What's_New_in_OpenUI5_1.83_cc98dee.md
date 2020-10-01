<!-- loiocc98dee51f9542c9977395440a0ac487 -->

| loio |
| -----|
| cc98dee51f9542c9977395440a0ac487 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/cc98dee51f9542c9977395440a0ac487) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/cc98dee51f9542c9977395440a0ac487)</div>

## What's New in OpenUI5 1.83

With this release OpenUI5 is upgraded from version 1.82 to 1.83.

***

<a name="loiocc98dee51f9542c9977395440a0ac487__section_qwl_pb5_zcb"/>

### Improved Features

| **OpenUI5 OData V2 Model** The new version of the OpenUI5 OData V2 model introduces the following features: -   We have introduced a `persistTechnicalMessages` model parameter. If set to `true`, messages returned with failed requests are treated as persistent and aren't removed by the OData model.
-   An `expand` parameter can be provided to the `sap.ui.model.odata.v2.ODataModel#callFunction` method in `mParameters`. The expand will be performed in a separate GET request within the same batch request as the POST request of the function import. The GET request references the result of the function import.

 |
| **OpenUI5 OData V4 Model** The new version of the OpenUI5 OData V4 model introduces the following features: -   Messages resulting from failed requests contain the HTTP status code in `technicalDetails.httpStatus`.
-   Query options starting with `sap-valid-` are allowed.
-   Dynamic "14.5.5 Expression edm:Collection" is supported by `sap.ui.model.odata.v4.AnnotationHelper#format` and `sap.ui.model.odata.v4.AnnotationHelper#value`.

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.|

***

<a name="loiocc98dee51f9542c9977395440a0ac487__section_rqn_wd5_zcb"/>

### Improved Controls

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>**`sap.f.GridContainer`**You can now drag and drop items using the keyboard into an empty container. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer). </th>
		<tr>
			<td>**`sap.m.IconTabBar`**The control now supports the badge feature. You can use it to indicate that something new has been added in a tab. This visual eye catcher, in the shape of a circle inherits the semantic colors of the tab filters. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.BadgeCustomData) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarBadges).</td>
			<td>**`sap.ui.integration.widgets.Card`**-   The Calendar card is no longer in experimental state. This card shows an overview of tasks for a single entity \(such as a person or resource\). It consists of an interactive calendar and a chronological list of appointments for a single date. For more information, see [Calendar Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar) in the Card Explorer. -   You can now dynamically fetch data to populate filters \(experimental\). For more information, see the `data` property in the [Filters](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/filters) section in the Card Explorer.
 -   We have introduced `size` and `backgroundColor` icon properties \(experimental\). They are both available for the List, Object, and Table cards, while the default card header has only the `backgroundColor` \(experimental\) property. For more information, see the [List Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/list), [Object Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/object) and [Table Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/table) sections in the Card Explorer.
			</td>
		</tr>
	</tbody>
</table>

