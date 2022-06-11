<!-- loio77e1dcc27c494d60ba0a03759b706e89 -->

| loio |
| -----|
| 77e1dcc27c494d60ba0a03759b706e89 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/77e1dcc27c494d60ba0a03759b706e89) | [demo kit latest release](https://sdk.openui5.org/topic/77e1dcc27c494d60ba0a03759b706e89)</div>

## What's New in OpenUI5 1.63

With this release OpenUI5 is upgraded from version 1.62 to 1.63.

***

<a name="loio77e1dcc27c494d60ba0a03759b706e89__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td valign="top">

**Custom Currencies**

Comprehensive support for formatting and parsing currencies has been part of OpenUI5 for a long time. We now extended the handling of custom currencies, so that you can also specify custom currencies per currency `NumberFormat` instance.

For more information, see [Currency Formatting](Currency_Formatting_e978728.md).



</td>
</tr>
<tr>
<td valign="top">

**UI5 Web Components**

UI5 Web Components are a set of reusable UI elements, which can be used for your static websites or web apps with a minimal footprint. They bring the relevant OpenUI5 qualities and latest SAP Fiori user experience to the HTML level and enable you to build a complete, enterprise-ready, and responsive web app, even if you're already using a different web framework.

UI5 Web Components are not built on top of OpenUI5 and are not its successor. They are lightweight and independent UI elements, offered complementary to the framework.



For more information, see the [UI5 Web Components](https://sap.github.io/ui5-webcomponents/) home page, the [GitHub Project](https://github.com/SAP/ui5-webcomponents), and the [blog post](https://blogs.sap.com/2019/02/11/ui5-web-components-the-beta-is-there/).



</td>
</tr>
</table>

***

<a name="loio77e1dcc27c494d60ba0a03759b706e89__section_bkm_s15_zcb"/>

### New Controls


<table>
<tr>
<td valign="top">

**`sap.f.ShellBar` \(Experimental\)**

We have implemented a new `sap.f.ShellBar` control, which is used as the uppermost section \(shell\) of the app. The control is fully responsive and adaptive, and corresponds to the latest SAP Fiori Design Guidelines.

 ![](images/loio421fe34907584da9a4415f4f5bdbd890_HiRes.gif) 

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.ShellBar) and the [Samples](https://sdk.openui5.org/entity/sap.f.ShellBar).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.upload.UploadSet`**

`UploadSet` is a new control that enables users to upload one or multiple files from their computer, tablet, or phone and to attach them to your application. This control builds on the `sap.m.UploadCollection` control, providing better handling of headers and requests, unified behavior of instant and deferred uploads, as well as improved progress indication.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.upload.UploadSet) and the [Samples](https://sdk.openui5.org/entity/sap.m.upload.UploadSet).



</td>
</tr>
</table>

***

<a name="loio77e1dcc27c494d60ba0a03759b706e89__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The new types `sap.ui.model.odata.type.Unit` and `sap.ui.model.odata.type.Currency`: The new types use the unit or currency customizing as provided by the back end in a special code list. For more information, see [Currency and Unit Customizing in OData V4](Currency_and_Unit_Customizing_in_OData_V4_4d1b9d4.md).

-   The method `sap.ui.model.odata.v4.AnnotationHelper.format`: This method can be used instead of `v4.AnnotationHelper.value` to generate bindings with type information and constraints. It also includes `$Path` in the result. To avoid the inclusion of `$Path`, resolve `$path` with the `sap.ui.mode.odata.v4.AnnotationHelper.resolve$Path` method. To create composite bindings with the new `sap.ui.model.odata.type.Unit` and `sap.ui.model.odata.type.Currency` types, use `sap.ui.model.odata.v4.AnnotationHelper.format`. For more information, see [Meta Model for OData V4](Meta_Model_for_OData_V4_7f29fb3.md).

-   The binding parameter `$$patchWithoutSideEffects`: The parameter was introduced with SAPUI5 1.60 and can now be used for `sap.ui.model.odata.v4.ODataListBindings`. The parameter is now also inherited to dependent bindings to avoid inconsistent behavior that was caused by the missing inheritance.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).



</td>
</tr>
</table>

***

<a name="loio77e1dcc27c494d60ba0a03759b706e89__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.f.Avatar`**

We have introduced a fallback image behavior that handles situations when the provided image source path leads to a non-existing image. If the `initials` property is set, `Avatar` displays the set value, otherwise a default icon markup is displayed.For more information, see the [Sample](https://sdk.openui5.org/sample/sap.f.sample.Avatar/preview).



</td>
</tr>
<tr>
<td valign="top">

**`sap.f.DynamicPage`**

We have implemented the option to provide a simple, single-line title that takes less space on smaller phone screens when the `DynamicPageHeader` is collapsed \(snapped\). You can enable it with the use of the new `snappedTitleOnMobile` aggregation.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPageTitle) and the [Sample](https://sdk.openui5.org/sample/sap.f.sample.DynamicPageFreeStyle/preview).



</td>
</tr>
<tr>
<td valign="top">

**`sap.f.semantic.SemanticPage`**

We have implemented the option to provide a simple, single-line title that takes less space on smaller phone screens when the `SemanticPage` header is collapsed \(snapped\). You can enable it with the use of the new `titleSnappedOnMobile` aggregation.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.semantic.SemanticPage) and the [Sample](https://sdk.openui5.org/sample/sap.f.sample.SemanticPageFreeStyle/preview).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.ObjectNumber`**, **`sap.m.ObjectStatus`**

You can now display both controls with a large font size, thus meeting the SAP Fiori Design Guidelines for displaying facets in the `ObjectPageHeader`. To use the larger font size, add the newly introduced CSS classes to the controls. For more information, see the *API Reference* \([`sap.m.ObjectNumber`](https://sdk.openui5.org/api/sap.m.ObjectNumber), [`sap.m.ObjectStatus`](https://sdk.openui5.org/api/sap.m.ObjectStatus)\), and the *Samples* \([`sap.m.ObjectNumber`](https://sdk.openui5.org/entity/sap.m.ObjectNumber), [`sap.m.ObjectStatus`](https://sdk.openui5.org/entity/sap.m.ObjectStatus)\).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Select`**

To ensure that the value states are displayed in all situations and devices, the control is now enabled to display the text set in the `valueStateText` property when the dropdown is opened.For more information, see the [Sample](https://sdk.openui5.org/sample/sap.m.sample.SelectValueState/preview).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.layout.cssgrid.CSSGrid`**

You can now set the `CSSGrid` breakpoints \(large, medium, or small\) to depend on the size of the parent container rather than the device screen size \(media query\). To enable the feature, use the new `containerQuery` property in the `GridResponsiveLayout` class. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.cssgrid.GridResponsiveLayout) and the [Sample](https://sdk.openui5.org/sample/sap.ui.layout.sample.GridResponsiveness/preview).



</td>
</tr>
</table>

***

<a name="loio77e1dcc27c494d60ba0a03759b706e89__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td valign="top">

**API Reference Tree**

We have improved the *API Reference* tree to use proper nesting of the OpenUI5 symbols based on a strict hierarchical structure. Fewer elements are now displayed on the root level, thus improving the user experience and shortening the time the user spends trying to find a specific symbol in the tree structure.

 ![](images/loio1e5ae735b1004f4eb807106d68ad71e2_HiRes.png) 



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

[What's New in OpenUI5 1.92](What_s_New_in_OpenUI5_1_92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

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

