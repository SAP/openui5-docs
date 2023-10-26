<!-- loioe8d9da76dcba4068aea81902bf631861 -->

| loio |
| -----|
| e8d9da76dcba4068aea81902bf631861 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/e8d9da76dcba4068aea81902bf631861) | [demo kit latest release](https://sdk.openui5.org/topic/e8d9da76dcba4068aea81902bf631861)</div>

## What's New in OpenUI5 1.63

With this release OpenUI5 is upgraded from version 1.62 to 1.63.

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

1.63 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Custom Currencies** 

</td>
<td valign="top">

**Custom Currencies**

Comprehensive support for formatting and parsing currencies has been part of OpenUI5 for a long time. We now extended the handling of custom currencies, so that you can also specify custom currencies per currency `NumberFormat` instance.

For more information, see [Currency Formatting](Currency_Formatting_e978728.md).

<sub>New•Feature•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**UI5 Web Components** 

</td>
<td valign="top">

**UI5 Web Components**

UI5 Web Components are a set of reusable UI elements, which can be used for your static websites or web apps with a minimal footprint. They bring the relevant OpenUI5 qualities and latest SAP Fiori user experience to the HTML level and enable you to build a complete, enterprise-ready, and responsive web app, even if you're already using a different web framework.

UI5 Web Components are not built on top of OpenUI5 and are not its successor. They are lightweight and independent UI elements, offered complementary to the framework.



For more information, see the [UI5 Web Components](https://sap.github.io/ui5-webcomponents/) home page, the [GitHub Project](https://github.com/SAP/ui5-webcomponents), and the [blog post](https://blogs.sap.com/2019/02/11/ui5-web-components-the-beta-is-there/).

<sub>New•Feature•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.ShellBar` \(Experimental\)** 

</td>
<td valign="top">

**`sap.f.ShellBar` \(Experimental\)**

We have implemented a new `sap.f.ShellBar` control, which is used as the uppermost section \(shell\) of the app. The control is fully responsive and adaptive, and corresponds to the latest SAP Fiori Design Guidelines.

![](images/loio421fe34907584da9a4415f4f5bdbd890_HiRes.gif)

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.ShellBar) and the [Samples](https://sdk.openui5.org/entity/sap.f.ShellBar).

<sub>New•Control•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.upload.UploadSet`** 

</td>
<td valign="top">

**`sap.m.upload.UploadSet`**

`UploadSet` is a new control that enables users to upload one or multiple files from their computer, tablet, or phone and to attach them to your application. This control builds on the `sap.m.UploadCollection` control, providing better handling of headers and requests, unified behavior of instant and deferred uploads, as well as improved progress indication.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.upload.UploadSet) and the [Samples](https://sdk.openui5.org/entity/sap.m.upload.UploadSet).

<sub>New•Control•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

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

-   The new types `sap.ui.model.odata.type.Unit` and `sap.ui.model.odata.type.Currency`: The new types use the unit or currency customizing as provided by the back end in a special code list. For more information, see [Currency and Unit Customizing in OData V4](Currency_and_Unit_Customizing_in_OData_V4_4d1b9d4.md).

-   The method `sap.ui.model.odata.v4.AnnotationHelper.format`: This method can be used instead of `v4.AnnotationHelper.value` to generate bindings with type information and constraints. It also includes `$Path` in the result. To avoid the inclusion of `$Path`, resolve `$path` with the `sap.ui.mode.odata.v4.AnnotationHelper.resolve$Path` method. To create composite bindings with the new `sap.ui.model.odata.type.Unit` and `sap.ui.model.odata.type.Currency` types, use `sap.ui.model.odata.v4.AnnotationHelper.format`. For more information, see [Meta Model for OData V4](Meta_Model_for_OData_V4_7f29fb3.md).

-   The binding parameter `$$patchWithoutSideEffects`: The parameter was introduced with SAPUI5 1.60 and can now be used for `sap.ui.model.odata.v4.ODataListBindings`. The parameter is now also inherited to dependent bindings to avoid inconsistent behavior that was caused by the missing inheritance.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

<sub>Changed•Feature•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.Avatar`** 

</td>
<td valign="top">

**`sap.f.Avatar`**

We have introduced a fallback image behavior that handles situations when the provided image source path leads to a non-existing image. If the `initials` property is set, `Avatar` displays the set value, otherwise a default icon markup is displayed.For more information, see the [Sample](https://sdk.openui5.org/sample/sap.f.sample.Avatar/preview).

<sub>Changed•Control•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.DynamicPage`** 

</td>
<td valign="top">

**`sap.f.DynamicPage`**

We have implemented the option to provide a simple, single-line title that takes less space on smaller phone screens when the `DynamicPageHeader` is collapsed \(snapped\). You can enable it with the use of the new `snappedTitleOnMobile` aggregation.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPageTitle) and the [Sample](https://sdk.openui5.org/sample/sap.f.sample.DynamicPageFreeStyle/preview).

<sub>Changed•Control•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.semantic.SemanticPage`** 

</td>
<td valign="top">

**`sap.f.semantic.SemanticPage`**

We have implemented the option to provide a simple, single-line title that takes less space on smaller phone screens when the `SemanticPage` header is collapsed \(snapped\). You can enable it with the use of the new `titleSnappedOnMobile` aggregation.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.semantic.SemanticPage) and the [Sample](https://sdk.openui5.org/sample/sap.f.sample.SemanticPageFreeStyle/preview).

<sub>Changed•Control•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ObjectNumber / sap.m.ObjectStatus`** 

</td>
<td valign="top">

**`sap.m.ObjectNumber / sap.m.ObjectStatus`**

You can now display both controls with a large font size, thus meeting the SAP Fiori Design Guidelines for displaying facets in the `ObjectPageHeader`. To use the larger font size, add the newly introduced CSS classes to the controls. For more information, see the *API Reference* \([`sap.m.ObjectNumber`](https://sdk.openui5.org/api/sap.m.ObjectNumber), [`sap.m.ObjectStatus`](https://sdk.openui5.org/api/sap.m.ObjectStatus)\), and the *Samples* \([`sap.m.ObjectNumber`](https://sdk.openui5.org/entity/sap.m.ObjectNumber), [`sap.m.ObjectStatus`](https://sdk.openui5.org/entity/sap.m.ObjectStatus)\).

<sub>Changed•Control•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Select`** 

</td>
<td valign="top">

**`sap.m.Select`**

To ensure that the value states are displayed in all situations and devices, the control is now enabled to display the text set in the `valueStateText` property when the dropdown is opened.For more information, see the [Sample](https://sdk.openui5.org/sample/sap.m.sample.SelectValueState/preview).

<sub>Changed•Control•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.layout.cssgrid.CSSGrid`** 

</td>
<td valign="top">

**`sap.ui.layout.cssgrid.CSSGrid`**

You can now set the `CSSGrid` breakpoints \(large, medium, or small\) to depend on the size of the parent container rather than the device screen size \(media query\). To enable the feature, use the new `containerQuery` property in the `GridResponsiveLayout` class. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.cssgrid.GridResponsiveLayout) and the [Sample](https://sdk.openui5.org/sample/sap.ui.layout.sample.GridResponsiveness/preview).

<sub>Changed•Control•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
<tr>
<td valign="top">

1.63 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Demo Kit API Reference Tree** 

</td>
<td valign="top">

**Demo Kit API Reference Tree**

We have improved the *API Reference* tree to use proper nesting of the OpenUI5 symbols based on a strict hierarchical structure. Fewer elements are now displayed on the root level, thus improving the user experience and shortening the time the user spends trying to find a specific symbol in the tree structure.

![](images/loio1e5ae735b1004f4eb807106d68ad71e2_HiRes.png)

<sub>Changed•Feature•Info Only•1.63</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2019-02-27

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_f09b63e.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

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

