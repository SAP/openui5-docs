<!-- loiod176be37229a45dbb1d6d0a1ae2f3167 -->

| loio |
| -----|
| d176be37229a45dbb1d6d0a1ae2f3167 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d176be37229a45dbb1d6d0a1ae2f3167) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d176be37229a45dbb1d6d0a1ae2f3167)</div>

## What's New in OpenUI5 1.78

With this release OpenUI5 is upgraded from version 1.77 to 1.78.

***

<a name="loiod176be37229a45dbb1d6d0a1ae2f3167__section_yxw_pxt_zcb"/>

### New Features

| **Special Messaging Support for Visually Impaired Users \(Experimental\)** We have introduced a way to programmatically expose dynamic content changes, that can be announced by the screen reader via the newly added `sap.ui.core.InvisibleMessage` \(experimental\) class. The class is designed to be used both internally in the controls logic and from the applications. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.InvisibleMessage) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.core.InvisibleMessage). |

***

<a name="loiod176be37229a45dbb1d6d0a1ae2f3167__section_qwl_pb5_zcb"/>

### Improved Features

| **OpenUI5 OData V2 Model** The new version of the OpenUI5 OData V2 model introduces the following features: -   A new `expand` parameter has been added to `sap.ui.model.odata.v2.ODataModel#createEntry`. The listed navigation properties are requested with an additional GET request in the same `$batch` request as the POST request for the entity creation. Note the prerequisites listed in the API documentation.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v2.ODataModel%23methods/createEntry).

-   Server messages without the `target` property, that is with `target=undefined`, are interpreted as unbound messages if the `BusinessObject` message scope is used.

 |
| **OpenUI5 OData V4 Model** The new version of the OpenUI5 OData V4 model introduces the following features: -   The `sap.ui.model.odata.v4.AnnotationHelper#format` and `#value` methods can be used on properties.
-   `sap.ui.model.odata.v4.Context#requestSideEffects` now supports updating data by specifying navigation properties to the parent entities followed by collection-valued structural or navigation properties in the path expressions. This extends the feature delivered with OpenUI5 1.75.
-   The auto-`$expand/$select` mechanism has been improved, so that the first data requests are sent out earlier.

 > Note:
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).
> 
> 

 For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.|
| **Screen Reader Support Enhancement** We have removed the `application` role from the body of OpenUI5 apps. Following the Aria 1.1 recommendations, the `application` role is not recommended on a body level, as the screen reader interprets the whole application as one big custom control. Now, the screen reader will no longer be forced into operating mode and will be started in its regular reading mode.|

***

<a name="loiod176be37229a45dbb1d6d0a1ae2f3167__section_rqn_wd5_zcb"/>

### Improved Controls

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>**`sap.m.ColorPalette`**We have added a new `setColorPickerSelectedColor` setter, which enables developers to dynamically set the selected color, prior to opening the color picker. This is useful when the user wants to select a variation of this color. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ColorPalette) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.ColorPalette).</th>

 -   If the `IconTabBar` is used inside a shell, it inherits the styling of the shell.

 -   A new `ariaTexts` property is now available. You can use it to set specific texts to be announced by a screen reader. It is of type `object` and can have two properties: `headerLabel` and `headerDescription`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.IconTabBar%23methods/setAriaTexts).
			</td>
		</tr>
		<tr>
			<td> **`sap.m.InputBase` \(Experimental\)** The class now supports the possibility to add links as part of the `ValueStateText` in the `InputBase`. Using the `formattedValueStateText` aggregation, you can now define the formatted text that appears in the value state message pop-up. The support is fully implemented in the `sap.m.Input`, `sap.m.MultiInput`, and `sap.m.ComboBox` controls. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.InputBase). </td>
			<td> **`sap.m.List, sap.m.Table`** The `List` and `Table` controls now provide a method to scroll the list of items so that the item with the given index is in the viewport. The scrolling is done based on the provided item index. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase%23methods/scrollToIndex) for the related method and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Table/sample/sap.m.sample.TableScrollToIndex). </td>
			<td> **`sap.m.MultiComboBox`, `sap.m.MultiInput`** When the `sap.m.MultiComboBox` and `sap.m.MultiInput` controls contain only one token with long text, the token is always displayed and the text is truncated depending on the screen width. Previously, the token was removed and in its place a text saying “1 item” was displayed, which was not very informative. For more information, see the [`sap.m.MultiComboBox`](https://openui5.hana.ondemand.com/#/entity/sap.m.MultiComboBox/sample/sap.m.sample.MultiComboBox) and the [`sap.m.MultiInput`](https://openui5.hana.ondemand.com/#/entity/sap.m.MultiInput/sample/sap.m.sample.MultiInput) samples. </td>
			<td>**`sap.ui.layout.Splitter`**-   A new `resetContentAreasSizes` method is now available that allows developers to programmatically reset the size of the content areas. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.Splitter%23methods/resetContentAreasSizes).
 -   The bars used in the `sap.ui.layout.Splitter` and `sap.ui.layout.ResponsiveSplitter` controls are now larger. This makes the bars easily draggable on touch devices. For more information, see the sample pages of [sap.ui.layout.Splitter](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.Splitter) and [sap.ui.layout.ResponsiveSplitter](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.ResponsiveSplitter).
			</td>
		</tr>
	</tbody>
</table>

