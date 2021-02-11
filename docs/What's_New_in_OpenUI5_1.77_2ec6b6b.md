<!-- loio2ec6b6b03ee249928bba929eec3d2d74 -->

| loio |
| -----|
| 2ec6b6b03ee249928bba929eec3d2d74 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/2ec6b6b03ee249928bba929eec3d2d74) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/2ec6b6b03ee249928bba929eec3d2d74)</div>

## What's New in OpenUI5 1.77

With this release OpenUI5 is upgraded from version 1.76 to 1.77.

***

<a name="loio2ec6b6b03ee249928bba929eec3d2d74__section_yxw_pxt_zcb"/>

### New Features

| **Supported Locales and Fallback** A list of [supported locales](Supported_Locales_and_Fallback_ec753bc.md) can now be configured in the `manifest.json` file. This enables an application to only request particular resource bundles with language-specific texts. As requests, that were previously needed to check for the availability of language files, can now be avoided, this helps to improve the runtime performance of applications. In addition, a new configuration allows you to explicitly set the fallback locale. English used to be the default locale, but now any fallback locale can be specified.|
| **Terminologies** By defining terminologies together with additional resource bundles, you can adapt an application for different scenarios or industries. [Terminologies](Terminologies_eba8d25.md) can be configured in the `manifest.json` file and can be activated in several ways, such as via API, URL parameter, or the bootstrap configuration.|

***

<a name="loio2ec6b6b03ee249928bba929eec3d2d74__section_qwl_pb5_zcb"/>

### Improved Features

| **OpenUI5 OData V4 Model** The new version of the OpenUI5 OData V4 model introduces the following features: -   You can now expand the first node of visually grouped aggregated data using `sap.ui.model.odata.v4.Context#expand`, as described in [Extension for Data Aggregation](Extension_for_Data_Aggregation_7d91431.md).

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding%23methods/setAggregation).

-   Binding parameters and format options can now be passed to `sap.ui.model.odata.v4.AnnotationHelper#format`, and binding parameters can be passed to `sap.ui.model.odata.v4.AnnotationHelper#value`.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.AnnotationHelper%23methods/).


 > Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.|
|**`Team Calendar`**This demo app is now enhanced with improvements in the navigation and available resolutions to provide better user experience. Switching between the different calendars now happens without loading the pages. Find the updated Team Calendar under [Demo Apps](https://openui5.hana.ondemand.com/#demoapps).|

***

<a name="loio2ec6b6b03ee249928bba929eec3d2d74__section_rqn_wd5_zcb"/>

### Improved Controls

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th> **`sap.f.FlexibleColumnLayout`** We’ve introduced the `restoreFocusOnBackNavigation` property. If the property is set to `true`, the focus is restored to the last known when navigating back to a previously opened column, for example, upon closing of the end column and being transferred back to the mid column.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.FlexibleColumnLayout) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.FlexibleColumnLayout/sample/sap.f.sample.FlexibleColumnLayoutWithOneColumnStart). </th>
		<tr>
			<td>**`sap.m.Button`**We have added a new `Attention` button type to the `sap.m.ButtonType` enum. This button type indicates a critical situation. For more information about the `sap.m.Button`, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Button). </td>
			<td>**`sap.m.IconTabBar`**This control is now updated according to the latest SAP Fiori design guidelines. The horizontal scrolling behavior of the tab filters has been removed. Now, all tabs that can't fit on the tab strip, are moved over to an overflow tab. An `items` aggregation has been added to the `sap.m.IconTabFilter` control, which allows the nesting of tab filters in a hierarchical order. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.IconTabBar) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar). </td>
			<td>**`sap.m.SearchField`**We have introduced a new `change` event, fired when the user changes the value of the search field. Unlike the `liveChange` event, the `change` event is not fired for each key press. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SearchField).</td>
			<td> **`sap.m.Table`** The automatic pop-in mode for the responsive table has been expanded: The new `hiddenInPopin` property now allows you to hide columns instead of moving them into the pop-in area based on the importance defined for each column \(`getImportance` in `sap.m.Column`\). For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Table%23methods/getHiddenInPopin) for the related method and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Table/sample/sap.m.sample.TableAutoPopin). </td>
			<td>**`sap.tnt.SideNavigation`**We have added a UI adaptation at runtime \(RTA\) `rename` action for the `sap.tnt.SideNavigation` items. Now it is possible to rename the text properties of the control at runtime directly in the SAP Fiori launchpad, without having to write new code. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.tnt.SideNavigation) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.tnt.SideNavigation).</td>
			<td>**`sap.ui.integration.widgets.Card`**-   We have introduced loading animation for UI Integration Cards. It displays a preview with an animated placeholder, which indicates the type and the attributes of the card while loading. For more information, see the loading of card samples in the [Card Explorer](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/index.html#/exploreOverview/types)..
 -   We have introduced `label` and `description` properties in the Parameters and Destinations sections of the manifest. This is useful for user-friendly visualization when working with design-time configuration tools.
 -   The markdown feature of Microsoft Adaptive Cards in `sap.ui.integration.widgets.Card` of type Adaptive is now enabled. The `TextBlock` element of the card supports a subset of Markdown syntax, that is defined in Microsoft's Adaptive Card. For more information, see the [Markdown Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/markdown) in the Card Explorer. 

 -   We have enhanced the capabilities of the Adaptive Card by supporting the `data` property, provided on the `sap.card` level in the card's manifest. For more information, see the [Data and Templating Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/data) in the Card Explorer.

 -   We have enabled manifest authors to define a destination with a basic configuration for the `Submit` action of the Adaptive Card type. Now you can control and define how the `Submit` action would be handled via the manifest. For more information, see the [Adaptive Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) section and the [Submit Action Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/adaptive-action-submit) in the Card Explorer.
			</td>
		</tr>
		<tr>
			<td> **`sap.uxap.ObjectPageLayout`**

 -   We’ve introduced the `showTitle` property for `sap.uxap.ObjectPageSubSection` to enable you to determine whether the subsection title is displayed. If a subsection is the only one \(or the only one visible\) within a section, its title is displayed instead of the section title, even if this property is set to `false`. To hide the title of a subsection that is the only one \(or the only one visible\), you need to set the `showTitle` properties to `false` for both `ObjectPageSection` and its `ObjectPageSubSection`.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.uxap.ObjectPageSubSection).
 -   We’ve introduced the `subSectionVisibilityChange` event. The event is fired when there’s a change in the visibility of the subsections of the page or the current tab \(when `ObjectPageLayout` is used in tabs-based mode\).For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.uxap.ObjectPageLayout) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.uxap.ObjectPageLayout/sample/sap.uxap.sample.ObjectPageState).
			</td>
		</tr>
	</tbody>
</table>

