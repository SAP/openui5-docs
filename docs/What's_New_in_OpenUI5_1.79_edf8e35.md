<!-- loioedf8e35377d4452491cdc488030feb13 -->

| loio |
| -----|
| edf8e35377d4452491cdc488030feb13 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/edf8e35377d4452491cdc488030feb13) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/edf8e35377d4452491cdc488030feb13)</div>

## What's New in OpenUI5 1.79

With this release OpenUI5 is upgraded from version 1.78 to 1.79.

***

<a name="loioedf8e35377d4452491cdc488030feb13__section_qwl_pb5_zcb"/>

### Improved Features

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th> **Browser and Platform Support** OpenUI5 used PhantomJS in the past to test the framework, even though PhantomJS was never officially supported. We have now removed all PhantomJS-specific code from the OpenUI5 code base. For more information, see [Browser and Platform Support](Browser_and_Platform_Support_74b59ef.md).</th>
 -   Server messages may target more than one property of the same entity. The additional targets are provided in the `additionalTargets` property in the `SAP-Message` header and the error response.
 -   If the new `bRejectOnFailure` parameter is set to true, `sap.ui.model.odata.v2.ODataModel#metadataLoaded` returns a promise that is rejected when the initial loading of metadata fails.
			</td>
		</tr>
		<tr>
			<td> **OpenUI5 OData V4 Model** The new version of the OpenUI5 OData V4 model introduces the following features:

 -   The `sap.ui.model.odata.v4.ODataListBinding#resume` and `sap.ui.model.odata.v4.ODataContextBinding#resume` methods only refresh the bindings that were changed while being suspended. -   The `autoExpandSelect` model setting and the `$$aggregation` list binding parameter can now be used together.

 > Restriction:  
 > Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.</td>
		</tr>

***

<a name="loioedf8e35377d4452491cdc488030feb13__section_rqn_wd5_zcb"/>

### Improved Controls

		<tr>
			<td>**`sap.f.GridContainer`, `sap.f.GridList`**We have improved the accessibility of these controls by providing better navigation and keyboard handling. For more information, see the [sap.f.GridContainer](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer) and [sap.f.GridList](https://openui5.hana.ondemand.com/#/entity/sap.f.GridList) samples.</td>
			<td>**`sap.m.IconTabBar`**-   We have introduced the `maxNestingLevel` property, which specifies the allowed levels of tabs nested within one another using drag and drop. The default value is 0, which means that nesting via user interaction is not allowed. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarDragDrop). -   Tab-filter label texts in horizontal layout are no longer truncated. For more information, see the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar).
			</td>
		</tr>
		<tr>
			<td>**`sap.m.Input`, `sap.m.MultiInput`**When the controls are used with tabular suggestions, the column headers are now sticky. In this way, when the list is scrolled, the headers do not scroll away, helping users to easily understand the relation between the header and the cell below. For more information, see the [sap.m.Input](https://openui5.hana.ondemand.com/#/entity/sap.m.Input/sample/sap.m.sample.InputKeyValueTabularSuggestions) and [sap.m.MultiInput](https://openui5.hana.ondemand.com/#/entity/sap.m.MultiInput/sample/sap.m.sample.MultiInputGrouping) samples. </td>
			<td> **`sap.m.InputBase` \(Experimental\)** We are extending the set of controls that support the possibility to add links as part of the `ValueStateText` in the `InputBase` with the `sap.m.MultiComboBox`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.InputBase). </td>
			<td>**`sap.m.Panel`**We have enhanced the control by making the whole header clickable to allow users to collapse/expand the `sap.m.Panel` easier and faster. In addition, when the focus is on the active area, the *Spacebar* and *Enter*/*Return* keys also trigger expand/collapse of the control. This scenario works if the title is provided via the API. If the `headerToolbar` aggregation is used, app developers have to handle it on their own. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Panel). </td>
			<td>**`sap.ui.integration.widgets.Card`**-   We have introduced the Extension JavaScript module \(experimental\), which enables developers to extend the built-in capabilities of the card. You can use it to specify custom logic for fetching data, define custom data formatters, or add custom actions to the card. For more information, see the [Card Extension](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/extension) section and the [Card Extension Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/extension) in the Card Explorer. -   The dynamic filtering feature \(experimental\) is now available, which allows developers to define custom filters in the manifest of the card. For more information, see the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/filtering) in the Card Explorer.
			</td>
		</tr>
	</tbody>
</table>

