<!-- loio1492551a0b8d4f58adc46eefcf58a2fa -->

| loio |
| -----|
| 1492551a0b8d4f58adc46eefcf58a2fa |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/1492551a0b8d4f58adc46eefcf58a2fa) | [demo kit latest release](https://sdk.openui5.org/topic/1492551a0b8d4f58adc46eefcf58a2fa)</div>

## What's New in OpenUI5 1.92

With this release OpenUI5 is upgraded from version 1.91 to 1.92.

***

<a name="loio1492551a0b8d4f58adc46eefcf58a2fa__section_bkm_s15_zcb"/>

### New Controls


<table>
<tr>
<td valign="top">

**`sap.m.DynamicDateRange` \(Experimental\)**

The new \(experimental\) `DynamicDateRange` control enables users to select absolute and relative dates and date ranges using a different offset from the current date. Application developers can configure the list of values offered. The `DynamicDateRange` control supports several standard options, but as a developer, you can also define a custom option that fits your specific use case. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DynamicDateRange) and the [Sample](https://sdk.openui5.org/entity/sap.m.DynamicDateRange).



</td>
</tr>
</table>

***

<a name="loio1492551a0b8d4f58adc46eefcf58a2fa__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The `sap.ui.model.odata.v4.Context#setKeepAlive` method now provides an additional `bRequestMessages` parameter that allows you to request bound messages for the kept-alive context. The message property is identified through the `com.sap.vocabularies.Common.v1.Messages` annotation. For more information, see [Server Messages in the OData V4 Model](Server_Messages_in_the_OData_V4_Model_fbe1cb5.md).

-   You can now execute actions with the `Prefer` header `handling=strict`. For more information, see [Strict Handling](OData_Operations_b54f789.md#loiob54f7895b7594c61a83fa7257fa9d13f__section_SH).

-   We now support absolute property bindings of `$count`. Note that this will display the count as it is provided by the server. If a count that includes transient entries is required, the header context has to be used. For more information, see [Binding Collection Inline Count](Binding_Collection_Inline_Count_77d2310.md).




</td>
</tr>
</table>

***

<a name="loio1492551a0b8d4f58adc46eefcf58a2fa__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.Dialog`**

We have updated the colors of value-state status icons. Now, they have better color-contrast ratios for improved accessibility. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.Dialog/sample/sap.m.sample.DialogMessage).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.List, sap.m.Table, sap.m.Tree`**

We have provided the new `requestItems` method that lets you load more data in a control. You can now trigger the growing feature manually, if the `growing` property is set to `true`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ListBase%23methods/requestItems).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.QuickViewPage`**

The control now supports avatars, which display business objects, images, initials, and more. To enable this functionality, the `QuickViewPage` control uses `sap.m.Avatar` as an aggregation. The `icon` and `fallbackIcon` properties of the `QuickViewPage` are now deprecated. Instead, developers should use the functionality of the new `avatar` aggregation. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.QuickViewPage) and the [Sample](https://sdk.openui5.org/entity/sap.m.QuickView/sample/sap.m.sample.QuickViewAvatarConfiguration).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

The charts in the Analytical card now support \(in experimental state\) interactions on the detail level. Until now, users could only interact with the whole content area. Now, the user can click on separate points of the charts. As an application developer you can configure two optional scenarios upon click:

-   Trigger navigation actions defined by the `actionableArea` \(experimental\) property.

-   Open a popover with more details about the selected point defined by the `popover` \(experimental\) property.


For more information, see the [Analytical Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/analytical) section and the [Chart Actions](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/analytical/chartActions) and [Details Popover](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/analytical/detailsPopover) samples in the Card Explorer.



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.layout.ResponsiveSplitter`**

We have added a new `resize` event, fired when the contents of the `sap.ui.layout.PaneContainer` are resized. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.PaneContainer) and the [Sample](https://sdk.openui5.org/entity/sap.ui.layout.ResponsiveSplitter/sample/sap.ui.layout.sample.ResponsiveSplitter).



</td>
</tr>
</table>

***

<a name="loio1492551a0b8d4f58adc46eefcf58a2fa__section_yxw_pxt_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

**Deprecation of String-Based Rendering**

String-based rendering \(also known as "apiVersion 1" of a renderer\) has been deprecated. Please use the [Semantic Rendering API \("apiVersion 2"\)](https://sdk.openui5.org/api/sap.ui.core.RenderManager) instead.For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated).



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.101](What_s_New_in_OpenUI5_1_101_5a18410.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](What_s_New_in_OpenUI5_1_100_5deb78f.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](What_s_New_in_OpenUI5_1_99_5e35c25.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](What_s_New_in_OpenUI5_1_98_7aacb4e.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](What_s_New_in_OpenUI5_1_97_f21858f.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](What_s_New_in_OpenUI5_1_96_b39a11b.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](What_s_New_in_OpenUI5_1_95_1b09465.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What_s_New_in_OpenUI5_1_94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What_s_New_in_OpenUI5_1_93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.91](What_s_New_in_OpenUI5_1_91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What_s_New_in_OpenUI5_1_90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What_s_New_in_OpenUI5_1_89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What_s_New_in_OpenUI5_1_88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_e315108.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What_s_New_in_OpenUI5_1_86_067e2fb.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What_s_New_in_OpenUI5_1_85_eeb5bd9.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What_s_New_in_OpenUI5_1_84_ccf76b7.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What_s_New_in_OpenUI5_1_82_f081cf0.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f71563c.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_3294c68.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_edf8e35.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_d176be3.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_2ec6b6b.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_b9b0a3f.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_dc3d3ce.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_21fc6cb.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_7b82664.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_25e5326.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_609fd01.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_4e89fee.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_41203fd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_5531aef.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_0968958.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_ebe7fda.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_9d2b189.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What_s_New_in_OpenUI5_1_64_1975e30.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_77e1dcc.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What_s_New_in_OpenUI5_1_62_27eea38.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What_s_New_in_OpenUI5_1_61_de4d50b.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_2a70354.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_b28edde.md "With this release, OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_53b4b5e.md "With this release, OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_f29023e.md "With this release, OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_a09dd79.md "With this release, OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_a844984.md "With this release, OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_2818f80.md "With this release, OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_4cf0986.md "With this release, OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_4768f1a.md "With this release, OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

