<!-- loioccf76b76327c421e9d87ff7fc3d7ba41 -->

| loio |
| -----|
| ccf76b76327c421e9d87ff7fc3d7ba41 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ccf76b76327c421e9d87ff7fc3d7ba41) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ccf76b76327c421e9d87ff7fc3d7ba41)</div>

## What's New in OpenUI5 1.84

With this release OpenUI5 is upgraded from version 1.82 to 1.84.

***

<a name="loioccf76b76327c421e9d87ff7fc3d7ba41__section_qwl_pb5_zcb"/>

### Improved Features

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th> **Asynchronous Loading of XML Content in Fragments** The `sap.ui.core.Fragment.load()` generic function to instantiate fragments is now fully asynchronic. Many scenarios, such as the declarative use of fragments in XML views, automatically benefit from the new asynchronous behavior. If your own code [instantiates fragments programmatically](Programmatically_Instantiating_XML_Fragments_d6af195.md) and accesses dependent entities such as controls by ID, make sure you're correctly chaining to the Promise returned by `Fragment.load()`. We have adjusted samples, tutorials, and documentation to reflect the typical asynchronous usage of fragments. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Fragment/methods/sap.ui.core.Fragment.load) in the Demo Kit.</th>

 -   We have added detailed documentation about sizing and layouts in Integration cards. For more information, see the [Sizing](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/sizing) and the  [Layouts](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/layouts) pages in the Card Explorer.
			</td>
		</tr>
		<tr>
			<td> **Navigation with Dynamic Targets** In addition to the usual static definition of navigation targets in the [Routing Configuration](Routing_Configuration_9023130.md) of the manifest, we also provide APIs to allow the declaration and display of targets at runtime. This accounts for scenarios in which the necessary information is only available at runtime, for example depending on the specific user configuration. Note that the static definition remains the preferred solution as it allows for performance optimization. Only use dynamic targets when a static declaration is not possible. For more information, see [Navigate with Dynamic Targets](Navigate_with_Dynamic_Targets_856d6c6.md).</td>
			<td> **OpenUI5 OData V2 Model** The new version of the OpenUI5 OData V2 model introduces the following features:

 -   We have introduced a `persistTechnicalMessages` model parameter. If set to `true`, messages returned with failed requests are treated as persistent and aren't removed by the OData model. -   An `expand` parameter can be provided to the `sap.ui.model.odata.v2.ODataModel#callFunction` method in `mParameters`. The expand is performed in a separate GET request within the same batch request as the POST request of the function import. The GET request references the result of the function import.
			</td>
		</tr>
		<tr>
			<td> **OpenUI5 OData V4 Model** The new version of the OpenUI5 OData V4 model introduces the following features:

 -   We now recommend using the [Manifest Model Preload](Manifest_Model_Preload_26ba6a5.md). For an earlier request of the root `$metadata` and the security token you need to also set the `earlyRequests` model parameter. -   The `sap.ui.model.odata.v4.Context#refresh` method is now supported for kept-alive contexts. A list binding context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.
 -   The `com.sap.vocabularies.Common.v1.ValueListRelevantQualifiers` annotation is now automatically taken into account by `sap.ui.model.odata.v4.ODataPropertyBinding#requestValueListInfo`.
 -   When using `groupLevels` with the `$$aggregation` list binding parameter, we now support the collapsing and re-expanding of previously expanded nodes.
 -   The `DataStateIndicator` table plugin now also works with the OData V4 model.
 -   Messages resulting from failed requests contain the HTTP status code in `technicalDetails.httpStatus`.
 -   Query options starting with `sap-valid-` are allowed.
 -   Dynamic "[14.5.5 Expression `edm:Collection`](http://docs.oasis-open.org/odata/odata/v4.0/csprd02/part3-csdl/odata-v4.0-csprd02-part3-csdl.html#_Toc360208903)" is supported by `sap.ui.model.odata.v4.AnnotationHelper#format` and `sap.ui.model.odata.v4.AnnotationHelper#value`.

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.</td>
		</tr>

***

<a name="loioccf76b76327c421e9d87ff7fc3d7ba41__section_rqn_wd5_zcb"/>

### Improved Controls

		<tr>
			<td>**`sap.f.GridContainer`**You can now drag and drop items using the keyboard into an empty container. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer). </td>
			<td>**`sap.m.Button`**The new `ariaHasPopup` property allows the `aria-haspopup` attribute to be set from another control that uses `sap.m.Button`. It indicates the availability and type of an interactive popup element that can be triggered by another control. This property is of type `sap.ui.core.aria.HasPopup`, which can have the following values: `None`\(default\), `Menu, ListBox, Tree, Grid`, and `Dialog`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Button).</td>
			<td>**`sap.m.ComboBox`**We have updated the behavior of the control regarding the `selectedKey` and `value` properties, to be aligned with `sap.m.Input`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ComboBox).</td>
			<td>**`sap.m.IconTabBar`**The control now supports the badge feature. You can use it to indicate that something new has been added in a tab. This visual eye catcher, in the shape of a circle inherits the semantic colors of the tab filters. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.BadgeCustomData) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarBadges).</td>
			<td>`**sap.m.Input**`We have introduced a new `valueHelpIconSrc` property. It allows you to set a custom value help icon, instead of the default one, by setting `sap.ui.core.URI` as value of the `valueHelpIconSrc` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Input) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Input/sample/sap.m.sample.InputCustomValueHelpIcon).</td>
			<td>**`sap.m.List`**The new `accDescription` property allows applications to define their own application-specific text for screen readers to replace the default text of `CustomListItem`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.CustomListItem%23methods/getAccDescription).</td>
			<td>**`sap.m.ObjectStatus`**We have made several visual improvements:
 -   Samples have been updated to use the latest message and status icons.
 -   Icons now have same width, which allows the text to be aligned when there are more than one items one below the other.
 -   The control now supports light font in large state.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ObjectStatus) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ObjectStatus/sample/sap.m.sample.ObjectStatus).
			</td>
		</tr>
		<tr>
			<td> **`sap.m.ProgressIndicator`** We have improved the control behavior when the available width is not enough and the text displayed inside `sap.m.ProgressIndicator` is truncated. Now, if the text value set in the `displayValue` property is truncated, the cursor becomes a pointer \(hand\). In such a scenario, the `ProgressIndicator` can be clicked/tapped to open an information popover that displays the full text value.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ProgressIndicator) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ProgressIndicator/sample/sap.m.sample.ProgressIndicator). </td>
			<td>**`sap.m.SearchField`**The icon of the Refresh button in the `sap.m.SearchField` is now changed from sap-icon://synchronize to sap-icon://refresh.</td>
			<td>**`sap.m.Wizard` \(Experimental\)**We have enhanced the `sap.m.Wizard` to support rendering of the steps as separate pages, instead of being appended to the previous one. Enable this by setting the new `renderMode` property to `sap.m.WizardRenderMode.Page`. The default behavior is not changed. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Wizard) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Wizard/sample/sap.m.sample.WizardSingleStep) .</td>
			<td>**`sap.ui.integration.widgets.Card`**-   The Calendar card is no longer in experimental state. This card shows an overview of tasks for a single entity \(such as a person or resource\). It consists of an interactive calendar and a chronological list of appointments for a single date. For more information, see [Calendar Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar) in the Card Explorer. -   You can now dynamically fetch data to populate filters \(experimental\). For more information, see the `data` property in the [Filters](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/filters) section and the  [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/filters) in the Card Explorer.
 -   We have introduced `size` and `backgroundColor` icon properties \(experimental\). They are both available for the List, Object, and Table cards, while the default card header has only the `backgroundColor` \(experimental\) property. For more information, see the [List Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/list), [Object Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/object) and [Table Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/table) sections in the Card Explorer.
 -   You can now use the `oCard.triggerAction` \(experimental\) method to programmatically trigger an action from a Component card or from an extension. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.integration.widgets.CardFacade%23methods/sap.ui.integration.widgets.CardFacade.triggerAction), [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/component/triggerAction) and the [Card Actions](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/cardActions) section in the Card Explorer. 
 -   You can now make HTTP POST requests with body encoding of type JSON. For more information, see the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/data/graphql) and the [Data](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/data) section in the Card Explorer.
			</td>
		</tr>
	</tbody>
</table>

