<!-- loio5cbb62df99cd4fe9ae4548a757ae9ad7 -->

| loio |
| -----|
| 5cbb62df99cd4fe9ae4548a757ae9ad7 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/5cbb62df99cd4fe9ae4548a757ae9ad7) | [demo kit latest release](https://sdk.openui5.org/topic/5cbb62df99cd4fe9ae4548a757ae9ad7)</div>

## What's New in OpenUI5 1.75

With this release OpenUI5 is upgraded from version 1.74 to 1.75.

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

1.75 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Accessibility Enhancement** 



</td>
<td valign="top">

**Accessibility Enhancement**

OpenUI5 is following the SAP ‘s updated design and development guidelines, as well as the testing procedures and accessibility reporting, that are based on WCAG 2.1 level A and AA.

<sub>New•Feature•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Browser and Platform Support** 



</td>
<td valign="top">

**Browser and Platform Support**

OpenUI5 now supports the latest Chromium-based version of Microsoft Edge. The next long-term maintenance OpenUI5 release that comes after 1.71 will be the last release to support the legacy EdgeHTML-based version of Microsoft Edge. For more information, see [Browser and Platform Support](Browser_and_Platform_Support_74b59ef.md).

<sub>New•Feature•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Card Explorer** 



</td>
<td valign="top">

**Card Explorer**

We have introduced a schema validation feature in our samples in the Card Explorer. With this option, developers can see a more detailed report for mistakes inside the card manifest. Things like wrong names of properties, bad property types or bad structures are easily spotted.For more information, explore the samples in the [Card Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/exploreOverview/types).

<sub>Changed•Feature•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Currency Codes** 



</td>
<td valign="top">

**Currency Codes**

When displaying ISO currency codes using `sap.ui.core.format.NumberFormat`, `sap.ui.model.type.Currency` or `sap.ui.model.odata.type.Currency`, the currency code is now displayed by default after the amount, ignoring locale, in order to be consistent with SAP design guidelines. The core configuration parameter `trailingCurrencyCode` can be used to switch the behavior globally.

If currency symbols are enabled \(formatting option `currencyCode: false`\), they continue to follow locale-specific placement.

<sub>Changed•Feature•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**OpenUI5 OData V2 Messages** 



</td>
<td valign="top">

**OpenUI5 OData V2 Messages**

With the new version of the OpenUI5 OData V2 model, the target of server messages is shortened by removing associated pairs of navigation properties. For example, a `/SalesOrderSet('1')/ToLineItems(SalesOrderID='1',ItemPosition='10')/ToHeader/GrossAmount` message target gets reduced to `/SalesOrderSet('1')/GrossAmount` if the `ToLineItems` and `ToHeader` navigation properties have the same relationship in the service metadata. If the second navigation property references a collection, the message target path is reduced only if the referenced entity is the same as without the navigation.

<sub>Changed•Feature•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



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

-   When displaying aggregated data with a list binding using either the `$$aggregation` binding parameter or `sap.ui.model.odata.v4.ODataListBinding#setAggregation`, you can filter by properties that are part of the original entity set but not of the result set. Note that these filters need to be provided as `sap.ui.model.Filter` objects.
-   `sap.ui.model.odata.v4.Context#requestSideEffects` now supports updating in parent bindings by specifying navigation properties to the parent entities in the path expressions. The respective navigation properties from the parent binding to the binding of the context and back to the parent need to be marked as partners in the metadata.
-   When using `autoExpandSelect`, paths with navigation properties can now be added to `$select`. The binding will evaluate this and automatically derive `$select` and `$expand`.
-   For `sap.ui.model.odata.v4.ODataPropertyBinding`, a `$$noPatch` binding parameter is provided, so that values can be changed in the model without updating them in the back end.
-   The `resume` method of the `v4.ODataContextBinding` and `v4.ODataListBinding` classes now works synchronously.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

<sub>Changed•Feature•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Title Support in Nested Components** 



</td>
<td valign="top">

**Title Support in Nested Components**

The `title` property can now also be defined on routing targets of type `Component`. When set with a binding syntax, it is resolved in the context of the root view of the component loaded by this target.

The router of a nested component may also have a `title` property defined on its own target\(s\) and eventually fire its own `titleChanged` event once such a target is displayed. A new configuration `propagateTitle` allows the `titleChanged` event to propagate from an individual `Component` target to the router of its parent component. In the routing configuration, this can also be enabled for all `Component` targets, so that it is not necessary to define the `propagateTitle` property on each `Component` target.

For more information, see [Using the title Property in Targets](Using_the_title_Property_in_Targets_1238d70.md) and [Enabling Routing in Nested Components](Enabling_Routing_in_Nested_Components_fb19f50.md). In addition, the [Sample](https://sdk.openui5.org/entity/sap.ui.core.routing.Router/sample/sap.ui.core.sample.RoutingNestedComponent) application introduced in the previous release to feature routing of nested components has been enhanced. It now shows how the new title definition and title propagation could be used in an application built with nested \(or reuse\) components. 

<sub>Changed•Feature•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.InitialPagePattern`** 



</td>
<td valign="top">

**`sap.m.InitialPagePattern`**

We have introduced the initial page floorplan as a Demo Kit sample. The floorplan allows users to navigate to a single object to view or edit it. The interaction point on the screen is a single input field and it relies on assisted input to direct the user to the object in as few steps as possible \(using features such as value help and live search\). For more information, see the [CardSAP Fiori Design Guidelines](https://experience.sap.com/fiori-design-web/initial-page-floorplan/)and the [Sample](https://sdk.openui5.org/entity/sap.m.InitialPagePattern/sample/sap.m.sample.InitialPagePattern).

<sub>Changed•Control•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Link`** 



</td>
<td valign="top">

**`sap.m.Link`**

The `text` property can now be changed using UI adaptation at runtime. This enables key users to provide meaningful link text according to the application context.For more information, see the [Samples](https://sdk.openui5.org/entity/sap.m.Link).

<sub>Changed•Control•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.MessageBox`** 



</td>
<td valign="top">

**`sap.m.MessageBox`**

We have introduced a new `emphasizedAction` property. This allows developers to specify which button in the dialog will receive the type `Emphasized`. If `emphasizedAction` is empty with no actions provided, the default value applies. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MessageBox) and the [Samples](https://sdk.openui5.org/entity/sap.m.MessageBox).

<sub>Changed•Control•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.ObjectStatus`** 



</td>
<td valign="top">

**`sap.m.ObjectStatus`**

We have enhanced the `sap.ui.core.IndicationColor` palette. Three new colors were added to the palette as numbers 6, 7, and 8. These colors enable developers to represent statuses that don't require a meaning in the sense of good-bad, but should be visually distinguishable. For example, statuses such as Updated, New, or Active. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ObjectStatus) and the [Sample](https://sdk.openui5.org/entity/sap.m.ObjectStatus/sample/sap.m.sample.ObjectStatus).

<sub>Changed•Control•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`** 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

We have enhanced the capabilities of the Adaptive Card \(Experimental\).

-   You can now load the Adaptive Card manifest/descriptor from а URL.

-   The Adaptive Card supports templating, which enables the separation of data from the layout.


For more information, see the [Adaptive Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) in the Card Explorer.

<sub>Changed•Control•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table, sap.ui.table.TreeTable`** 



</td>
<td valign="top">

**`sap.ui.table.AnalyticalTable`, `sap.ui.table.Table, sap.ui.table.TreeTable`**

A more comprehensive message text is now shown if no data is available because all table columns are hidden.

<sub>Changed•Control•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
<tr>
<td valign="top">

1.75 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Demo Kit Improvements** 



</td>
<td valign="top">

**Demo Kit Improvements**

***Edit on GitHub* link from each OpenUI5 *Documentation* page**

We have added a direct link from each OpenUI5 documentation page to its markdown version in the *openui5-docs* GitHub repo. Now, when you want to send us feedback on a specific topic or even suggest a change with a pull request, we hope to save you time and efforts in finding the respective file.

![](images/loio8a5845e5be56483da308611359ba45ea_HiRes.gif)

**Search Highlighting in the *Documentation* and *Samples* sections**

The search highlighting functionality is now also available in the *Documentation* tree filter and the *Samples* list.

![](images/loioe79499d4357e4a7eb7de9c5e1a835d55_HiRes.png)

![](images/loio308ff81070684b318c4da4d1290a7e95_HiRes.png)

<sub>New•Feature•Info Only•1.75</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-02-27



</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_f09b63e.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_c46b439.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_aad03b5.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

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

