<!-- loio1492551a0b8d4f58adc46eefcf58a2fa -->

| loio |
| -----|
| 1492551a0b8d4f58adc46eefcf58a2fa |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/1492551a0b8d4f58adc46eefcf58a2fa) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/1492551a0b8d4f58adc46eefcf58a2fa)</div>

## What's New in OpenUI5 1.92

With this release OpenUI5 is upgraded from version 1.91 to 1.92.

***

<a name="loio1492551a0b8d4f58adc46eefcf58a2fa__section_bkm_s15_zcb"/>

### New Controls


<table>
<tr>
<td>

**`sap.m.DynamicDateRange` \(Experimental\)**

The new \(experimental\) `DynamicDateRange` control enables users to select absolute and relative dates and date ranges using a different offset from the current date. Application developers can configure the list of values offered. The `DynamicDateRange` control supports several standard options, but as a developer, you can also define a custom option that fits your specific use case. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.DynamicDateRange) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.DynamicDateRange).



</td>
</tr>
</table>

***

<a name="loio1492551a0b8d4f58adc46eefcf58a2fa__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

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
<td>

**`sap.m.Dialog`**

We have updated the colors of value-state status icons. Now, they have better color-contrast ratios for improved accessibility. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Dialog/sample/sap.m.sample.DialogMessage).



</td>
</tr>
<tr>
<td>

**`sap.m.List, sap.m.Table, sap.m.Tree`**

We have provided the new `requestItems` method that lets you load more data in a control. You can now trigger the growing feature manually, if the `growing` property is set to `true`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase%23methods/requestItems).



</td>
</tr>
<tr>
<td>

**`sap.m.QuickViewPage`**

The control now supports avatars, which display business objects, images, initials, and more. To enable this functionality, the `QuickViewPage` control uses `sap.m.Avatar` as an aggregation. The `icon` and `fallbackIcon` properties of the `QuickViewPage` are now deprecated. Instead, developers should use the functionality of the new `avatar` aggregation. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.QuickViewPage) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.QuickView/sample/sap.m.sample.QuickViewAvatarConfiguration).



</td>
</tr>
<tr>
<td>

**`sap.ui.integration.widgets.Card`**

The charts in the Analytical card now support \(in experimental state\) interactions on the detail level. Until now, users could only interact with the whole content area. Now, the user can click on separate points of the charts. As an application developer you can configure two optional scenarios upon click:

-   Trigger navigation actions defined by the `actionableArea` \(experimental\) property.

-   Open a popover with more details about the selected point defined by the `popover` \(experimental\) property.


For more information, see the [Analytical Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/analytical) section and the [Chart Actions](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/analytical/chartActions) and [Details Popover](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/analytical/detailsPopover) samples in the Card Explorer.



</td>
</tr>
<tr>
<td>

**`sap.ui.layout.ResponsiveSplitter`**

We have added a new `resize` event, fired when the contents of the `sap.ui.layout.PaneContainer` are resized. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.PaneContainer) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.ResponsiveSplitter/sample/sap.ui.layout.sample.ResponsiveSplitter).



</td>
</tr>
</table>

***

<a name="loio1492551a0b8d4f58adc46eefcf58a2fa__section_yxw_pxt_zcb"/>

### Deprecations


<table>
<tr>
<td>

**Deprecation of String-Based Rendering**

String-based rendering \(also known as "apiVersion 1" of a renderer\) has been deprecated. Please use the [Semantic Rendering API \("apiVersion 2"\)](https://openui5.hana.ondemand.com/#/api/sap.ui.core.RenderManager) instead.For a complete list of all deprecations, see [Deprecated APIs](https://openui5.hana.ondemand.com/#/api/deprecated).



</td>
</tr>
</table>

**Parent topicColonSymbol** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.94](What's_New_in_OpenUI5_1.94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What's_New_in_OpenUI5_1.93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

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

