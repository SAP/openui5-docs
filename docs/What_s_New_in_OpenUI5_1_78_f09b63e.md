<!-- loiof09b63e46de44642ba2bf4bd3bf848a0 -->

| loio |
| -----|
| f09b63e46de44642ba2bf4bd3bf848a0 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/f09b63e46de44642ba2bf4bd3bf848a0) | [demo kit latest release](https://sdk.openui5.org/topic/f09b63e46de44642ba2bf4bd3bf848a0)</div>

## What's New in OpenUI5 1.78

With this release OpenUI5 is upgraded from version 1.77 to 1.78.

***

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

1.78 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Special Messaging Support for Visually Impaired Users \(Experimental\)** 

</td>
<td valign="top">

**Special Messaging Support for Visually Impaired Users \(Experimental\)**

We have introduced a way to programmatically expose dynamic content changes, that can be announced by the screen reader via the newly added `sap.ui.core.InvisibleMessage` \(experimental\) class. The class is designed to be used both internally in the controls logic and from the applications. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.InvisibleMessage) and the [Sample](https://sdk.openui5.org/entity/sap.ui.core.InvisibleMessage).

<sub>New•Feature•Info Only•1.78</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2020-05-21

</td>
</tr>
<tr>
<td valign="top">

1.78 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V2 Model** 

</td>
<td valign="top">

**OpenUI5 OData V2 Model**

The new version of the OpenUI5 OData V2 model introduces the following features:

-   A new `expand` parameter has been added to `sap.ui.model.odata.v2.ODataModel#createEntry`. The listed navigation properties are requested with an additional GET request in the same `$batch` request as the POST request for the entity creation. Note the prerequisites listed in the API documentation.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v2.ODataModel%23methods/createEntry).

-   Server messages without the `target` property, that is with `target=undefined`, are interpreted as unbound messages if the `BusinessObject` message scope is used.

<sub>Changed•Feature•Info Only•1.78</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-05-21

</td>
</tr>
<tr>
<td valign="top">

1.78 

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

-   The `sap.ui.model.odata.v4.AnnotationHelper#format` and `#value` methods can be used on properties.
-   `sap.ui.model.odata.v4.Context#requestSideEffects` now supports updating data by specifying navigation properties to the parent entities followed by collection-valued structural or navigation properties in the path expressions. This extends the feature delivered with OpenUI5 1.75.
-   The auto-`$expand/$select` mechanism has been improved, so that the first data requests are sent out earlier.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

<sub>Changed•Feature•Info Only•1.78</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-05-21

</td>
</tr>
<tr>
<td valign="top">

1.78 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Screen Reader Support Enhancement** 

</td>
<td valign="top">

**Screen Reader Support Enhancement**

We have removed the `application` role from the body of OpenUI5 apps. Following the Aria 1.1 recommendations, the `application` role is not recommended on a body level, as the screen reader interprets the whole application as one big custom control. Now, the screen reader will no longer be forced into operating mode and will be started in its regular reading mode.

<sub>Changed•Feature•Info Only•1.78</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-05-21

</td>
</tr>
<tr>
<td valign="top">

1.78 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ColorPalette`** 

</td>
<td valign="top">

**`sap.m.ColorPalette`**

We have added a new `setColorPickerSelectedColor` setter, which enables developers to dynamically set the selected color, prior to opening the color picker. This is useful when the user wants to select a variation of this color. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ColorPalette) and the [Samples](https://sdk.openui5.org/entity/sap.m.ColorPalette).

<sub>Changed•Control•Info Only•1.78</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-05-21

</td>
</tr>
<tr>
<td valign="top">

1.78 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.IconTabBar`** 

</td>
<td valign="top">

**`sap.m.IconTabBar`**

-   We have introduced a new behavior of the `IconTabBar` filters with sub tabs. If the filter has its own text content, you can select the filter to display the content. Clicking on the second area \(chevron button\) expands the list of sub tabs. If the filter doesn’t have its own text content, then we have one single area and clicking on it expands the list of sub tabs. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarSubTabs).

-   If the `IconTabBar` is used inside a shell, it inherits the styling of the shell.

-   A new `ariaTexts` property is now available. You can use it to set specific texts to be announced by a screen reader. It is of type `object` and can have two properties: `headerLabel` and `headerDescription`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IconTabBar%23methods/setAriaTexts).


<sub>Changed•Control•Info Only•1.78</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-05-21

</td>
</tr>
<tr>
<td valign="top">

1.78 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.InputBase` \(Experimental\)** 

</td>
<td valign="top">

**`sap.m.InputBase` \(Experimental\)**

The class now supports the possibility to add links as part of the `ValueStateText` in the `InputBase`. Using the `formattedValueStateText` aggregation, you can now define the formatted text that appears in the value state message pop-up. The support is fully implemented in the `sap.m.Input`, `sap.m.MultiInput`, and `sap.m.ComboBox` controls. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.InputBase).

<sub>Changed•Control•Info Only•1.78</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-05-21

</td>
</tr>
<tr>
<td valign="top">

1.78 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.List`, `sap.m.Table`** 

</td>
<td valign="top">

**`sap.m.List`, `sap.m.Table`**

The `List` and `Table` controls now provide a method to scroll the list of items so that the item with the given index is in the viewport. The scrolling is done based on the provided item index. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ListBase%23methods/scrollToIndex) for the related method and the [Sample](https://sdk.openui5.org/entity/sap.m.Table/sample/sap.m.sample.TableScrollToIndex).

<sub>Changed•Control•Info Only•1.78</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-05-21

</td>
</tr>
<tr>
<td valign="top">

1.78 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MultiComboBox`, `sap.m.MultiInput`** 

</td>
<td valign="top">

**`sap.m.MultiComboBox`, `sap.m.MultiInput`**

When the `sap.m.MultiComboBox` and `sap.m.MultiInput` controls contain only one token with long text, the token is always displayed and the text is truncated depending on the screen width. Previously, the token was removed and in its place a text saying “1 item” was displayed, which was not very informative. For more information, see the [`sap.m.MultiComboBox`](https://sdk.openui5.org/entity/sap.m.MultiComboBox/sample/sap.m.sample.MultiComboBox) and the [`sap.m.MultiInput`](https://sdk.openui5.org/entity/sap.m.MultiInput/sample/sap.m.sample.MultiInput) samples.

<sub>Changed•Control•Info Only•1.78</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-05-21

</td>
</tr>
<tr>
<td valign="top">

1.78 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.layout.Splitter`** 

</td>
<td valign="top">

**`sap.ui.layout.Splitter`**

-   A new `resetContentAreasSizes` method is now available that allows developers to programmatically reset the size of the content areas. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.Splitter%23methods/resetContentAreasSizes).

-   The bars used in the `sap.ui.layout.Splitter` and `sap.ui.layout.ResponsiveSplitter` controls are now larger. This makes the bars easily draggable on touch devices. For more information, see the sample pages of [sap.ui.layout.Splitter](https://sdk.openui5.org/entity/sap.ui.layout.Splitter) and [sap.ui.layout.ResponsiveSplitter](https://sdk.openui5.org/entity/sap.ui.layout.ResponsiveSplitter).


<sub>Changed•Control•Info Only•1.78</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-05-21

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.133](What_s_New_in_OpenUI5_1_133_86d7605.md "With this release OpenUI5 is upgraded from version 1.132 to 1.133.")

[What's New in OpenUI5 1.132](What_s_New_in_OpenUI5_1_132_bd2e61f.md "With this release OpenUI5 is upgraded from version 1.131 to 1.132.")

[What's New in OpenUI5 1.131](What_s_New_in_OpenUI5_1_131_7d24d94.md "With this release OpenUI5 is upgraded from version 1.130 to 1.131.")

[What's New in OpenUI5 1.130](What_s_New_in_OpenUI5_1_130_85609d4.md "With this release OpenUI5 is upgraded from version 1.129 to 1.130.")

[What's New in OpenUI5 1.129](What_s_New_in_OpenUI5_1_129_d22b8af.md "With this release OpenUI5 is upgraded from version 1.128 to 1.129.")

[What's New in OpenUI5 1.128](What_s_New_in_OpenUI5_1_128_1f76220.md "With this release OpenUI5 is upgraded from version 1.127 to 1.128.")

[What's New in OpenUI5 1.127](What_s_New_in_OpenUI5_1_127_e5e1317.md "With this release OpenUI5 is upgraded from version 1.126 to 1.127.")

[What's New in OpenUI5 1.126](What_s_New_in_OpenUI5_1_126_1d98116.md "With this release OpenUI5 is upgraded from version 1.125 to 1.126.")

[What's New in OpenUI5 1.125](What_s_New_in_OpenUI5_1_125_9d87044.md "With this release OpenUI5 is upgraded from version 1.124 to 1.125.")

[What's New in OpenUI5 1.124](What_s_New_in_OpenUI5_1_124_7f77c3f.md "With this release OpenUI5 is upgraded from version 1.123 to 1.124.")

[What's New in OpenUI5 1.123](What_s_New_in_OpenUI5_1_123_9d00ac7.md "With this release OpenUI5 is upgraded from version 1.122 to 1.123.")

[What's New in OpenUI5 1.122](What_s_New_in_OpenUI5_1_122_5d078da.md "With this release OpenUI5 is upgraded from version 1.121 to 1.122.")

[What's New in OpenUI5 1.121](What_s_New_in_OpenUI5_1_121_91a4a2f.md "With this release OpenUI5 is upgraded from version 1.120 to 1.121.")

[What's New in OpenUI5 1.120](What_s_New_in_OpenUI5_1_120_2359b63.md "With this release OpenUI5 is upgraded from version 1.119 to 1.120.")

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

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_849e1b6.md "With this release OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_759e9f3.md "With this release OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_fa1efac.md "With this release OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_6307539.md "With this release OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

