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

