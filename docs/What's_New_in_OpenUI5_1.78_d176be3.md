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


<table>
<tr>
<td>

**Special Messaging Support for Visually Impaired Users \(Experimental\)**

We have introduced a way to programmatically expose dynamic content changes, that can be announced by the screen reader via the newly added `sap.ui.core.InvisibleMessage` \(experimental\) class. The class is designed to be used both internally in the controls logic and from the applications. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.InvisibleMessage) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.core.InvisibleMessage).



</td>
</tr>
</table>

***

<a name="loiod176be37229a45dbb1d6d0a1ae2f3167__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

**OpenUI5 OData V2 Model**

The new version of the OpenUI5 OData V2 model introduces the following features:

-   A new `expand` parameter has been added to `sap.ui.model.odata.v2.ODataModel#createEntry`. The listed navigation properties are requested with an additional GET request in the same `$batch` request as the POST request for the entity creation. Note the prerequisites listed in the API documentation.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v2.ODataModel%23methods/createEntry).

-   Server messages without the `target` property, that is with `target=undefined`, are interpreted as unbound messages if the `BusinessObject` message scope is used.



</td>
</tr>
<tr>
<td>

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The `sap.ui.model.odata.v4.AnnotationHelper#format` and `#value` methods can be used on properties.
-   `sap.ui.model.odata.v4.Context#requestSideEffects` now supports updating data by specifying navigation properties to the parent entities followed by collection-valued structural or navigation properties in the path expressions. This extends the feature delivered with OpenUI5 1.75.
-   The auto-`$expand/$select` mechanism has been improved, so that the first data requests are sent out earlier.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.



</td>
</tr>
<tr>
<td>

**Screen Reader Support Enhancement**

We have removed the `application` role from the body of OpenUI5 apps. Following the Aria 1.1 recommendations, the `application` role is not recommended on a body level, as the screen reader interprets the whole application as one big custom control. Now, the screen reader will no longer be forced into operating mode and will be started in its regular reading mode.



</td>
</tr>
</table>

***

<a name="loiod176be37229a45dbb1d6d0a1ae2f3167__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td>

**`sap.m.ColorPalette`**

We have added a new `setColorPickerSelectedColor` setter, which enables developers to dynamically set the selected color, prior to opening the color picker. This is useful when the user wants to select a variation of this color. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ColorPalette) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.ColorPalette).



</td>
</tr>
<tr>
<td>

**`sap.m.IconTabBar`**

-   We have introduced a new behavior of the `IconTabBar` filters with sub tabs. If the filter has its own text content, you can select the filter to display the content. Clicking on the second area \(chevron button\) expands the list of sub tabs. If the filter doesn’t have its own text content, then we have one single area and clicking on it expands the list of sub tabs. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarSubTabs).

-   If the `IconTabBar` is used inside a shell, it inherits the styling of the shell.

-   A new `ariaTexts` property is now available. You can use it to set specific texts to be announced by a screen reader. It is of type `object` and can have two properties: `headerLabel` and `headerDescription`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.IconTabBar%23methods/setAriaTexts).




</td>
</tr>
<tr>
<td>

**`sap.m.InputBase` \(Experimental\)**

The class now supports the possibility to add links as part of the `ValueStateText` in the `InputBase`. Using the `formattedValueStateText` aggregation, you can now define the formatted text that appears in the value state message pop-up. The support is fully implemented in the `sap.m.Input`, `sap.m.MultiInput`, and `sap.m.ComboBox` controls. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.InputBase). 



</td>
</tr>
<tr>
<td>

**`sap.m.List, sap.m.Table`**

The `List` and `Table` controls now provide a method to scroll the list of items so that the item with the given index is in the viewport. The scrolling is done based on the provided item index. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase%23methods/scrollToIndex) for the related method and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Table/sample/sap.m.sample.TableScrollToIndex).



</td>
</tr>
<tr>
<td>

**`sap.m.MultiComboBox`, `sap.m.MultiInput`**

When the `sap.m.MultiComboBox` and `sap.m.MultiInput` controls contain only one token with long text, the token is always displayed and the text is truncated depending on the screen width. Previously, the token was removed and in its place a text saying “1 item” was displayed, which was not very informative. For more information, see the [`sap.m.MultiComboBox`](https://openui5.hana.ondemand.com/#/entity/sap.m.MultiComboBox/sample/sap.m.sample.MultiComboBox) and the [`sap.m.MultiInput`](https://openui5.hana.ondemand.com/#/entity/sap.m.MultiInput/sample/sap.m.sample.MultiInput) samples.



</td>
</tr>
<tr>
<td>

**`sap.ui.layout.Splitter`**

-   A new `resetContentAreasSizes` method is now available that allows developers to programmatically reset the size of the content areas. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.Splitter%23methods/resetContentAreasSizes).

-   The bars used in the `sap.ui.layout.Splitter` and `sap.ui.layout.ResponsiveSplitter` controls are now larger. This makes the bars easily draggable on touch devices. For more information, see the sample pages of [sap.ui.layout.Splitter](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.Splitter) and [sap.ui.layout.ResponsiveSplitter](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.ResponsiveSplitter).




</td>
</tr>
</table>

**Parent topicColonSymbol** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.94](What's_New_in_OpenUI5_1.94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What's_New_in_OpenUI5_1.93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What's_New_in_OpenUI5_1.92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What's_New_in_OpenUI5_1.91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What's_New_in_OpenUI5_1.90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What's_New_in_OpenUI5_1.89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What's_New_in_OpenUI5_1.88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What's_New_in_OpenUI5_1.87_e315108.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What's_New_in_OpenUI5_1.86_067e2fb.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What's_New_in_OpenUI5_1.85_eeb5bd9.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What's_New_in_OpenUI5_1.84_ccf76b7.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What's_New_in_OpenUI5_1.82_f081cf0.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What's_New_in_OpenUI5_1.81_f71563c.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What's_New_in_OpenUI5_1.80_3294c68.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What's_New_in_OpenUI5_1.79_edf8e35.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

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

