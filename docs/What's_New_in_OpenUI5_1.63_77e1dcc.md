<!-- loio77e1dcc27c494d60ba0a03759b706e89 -->

| loio |
| -----|
| 77e1dcc27c494d60ba0a03759b706e89 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/77e1dcc27c494d60ba0a03759b706e89) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/77e1dcc27c494d60ba0a03759b706e89)</div>

## What's New in OpenUI5 1.63

With this release OpenUI5 is upgraded from version 1.62 to 1.63.

***

<a name="loio77e1dcc27c494d60ba0a03759b706e89__section_yxw_pxt_zcb"/>

### New Features

|**Custom Currencies**

Comprehensive support for formatting and parsing currencies has been part of OpenUI5 for a long time. We now extended the handling of custom currencies, so that you can also specify custom currencies per currency `NumberFormat` instance.

For more information, see [Currency Formatting](Currency_Formatting_e978728.md).

|
|**UI5 Web Components**

UI5 Web Components are a set of reusable UI elements, which can be used for your static websites or web apps with a minimal footprint. They bring the relevant OpenUI5 qualities and latest SAP Fiori user experience to the HTML level and enable you to build a complete, enterprise-ready, and responsive web app, even if you're already using a different web framework.

UI5 Web Components are not built on top of OpenUI5 and are not its successor. They are lightweight and independent UI elements, offered complementary to the framework.

   

For more information, see the [UI5 Web Components](https://sap.github.io/ui5-webcomponents/) home page, the [GitHub Project](https://github.com/SAP/ui5-webcomponents), and the [blog post](https://blogs.sap.com/2019/02/11/ui5-web-components-the-beta-is-there/).

|

***

<a name="loio77e1dcc27c494d60ba0a03759b706e89__section_bkm_s15_zcb"/>

### New Controls

|**`sap.f.ShellBar` \(Experimental\)**

We have implemented a new `sap.f.ShellBar` control, which is used as the uppermost section \(shell\) of the app. The control is fully responsive and adaptive, and corresponds to the latest SAP Fiori Design Guidelines.

 ![](loio421fe34907584da9a4415f4f5bdbd890_HiRes.gif) 

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.ShellBar) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.f.ShellBar).

|
|**`sap.m.upload.UploadSet`**

`UploadSet` is a new control that enables users to upload one or multiple files from their computer, tablet, or phone and to attach them to your application. This control builds on the `sap.m.UploadCollection` control, providing better handling of headers and requests, unified behavior of instant and deferred uploads, as well as improved progress indication.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.upload.UploadSet) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.upload.UploadSet).

|

***

<a name="loio77e1dcc27c494d60ba0a03759b706e89__section_qwl_pb5_zcb"/>

### Improved Features

|**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The new types `sap.ui.model.odata.type.Unit` and `sap.ui.model.odata.type.Currency`: The new types use the unit or currency customizing as provided by the back end in a special code list. For more information, see [Currencies and Units \(OData V4 Model\)](Currencies_and_Units_(OData_V4_Model)_4d1b9d4.md).

-   The method `sap.ui.model.odata.v4.AnnotationHelper.format`: This method can be used instead of `v4.AnnotationHelper.value` to generate bindings with type information and constraints. It also includes `$Path` in the result. To avoid the inclusion of `$Path`, resolve `$path` with the `sap.ui.mode.odata.v4.AnnotationHelper.resolve$Path` method. To create composite bindings with the new `sap.ui.model.odata.type.Unit` and `sap.ui.model.odata.type.Currency` types, use `sap.ui.model.odata.v4.AnnotationHelper.format`. For more information, see [Meta Model for OData V4](Meta_Model_for_OData_V4_7f29fb3.md).

-   The binding parameter `$$patchWithoutSideEffects`: The parameter was introduced with SAPUI5 1.60 and can now be used for `sap.ui.model.odata.v4.ODataListBindings`. The parameter is now also inherited to dependent bindings to avoid inconsistent behavior that was caused by the missing inheritance.


> Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).

|

***

<a name="loio77e1dcc27c494d60ba0a03759b706e89__section_rqn_wd5_zcb"/>

### Improved Controls

|**`sap.f.Avatar`**

We have introduced a fallback image behavior that handles situations when the provided image source path leads to a non-existing image. If the `initials` property is set, `Avatar` displays the set value, otherwise a default icon markup is displayed.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.f.sample.Avatar/preview).

|
|**`sap.f.DynamicPage`**

We have implemented the option to provide a simple, single-line title that takes less space on smaller phone screens when the `DynamicPageHeader` is collapsed \(snapped\). You can enable it with the use of the new `snappedTitleOnMobile` aggregation.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPageTitle) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.f.sample.DynamicPageFreeStyle/preview).

|
|**`sap.f.semantic.SemanticPage`**

We have implemented the option to provide a simple, single-line title that takes less space on smaller phone screens when the `SemanticPage` header is collapsed \(snapped\). You can enable it with the use of the new `titleSnappedOnMobile` aggregation.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.semantic.SemanticPage) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.f.sample.SemanticPageFreeStyle/preview).

|
|**`sap.m.ObjectNumber`**, **`sap.m.ObjectStatus`**

You can now display both controls with a large font size, thus meeting the SAP Fiori Design Guidelines for displaying facets in the `ObjectPageHeader`. To use the larger font size, add the newly introduced CSS classes to the controls. For more information, see the *API Reference* \([`sap.m.ObjectNumber`](https://openui5.hana.ondemand.com/#/api/sap.m.ObjectNumber), [`sap.m.ObjectStatus`](https://openui5.hana.ondemand.com/#/api/sap.m.ObjectStatus)\), and the *Samples* \([`sap.m.ObjectNumber`](https://openui5.hana.ondemand.com/#/entity/sap.m.ObjectNumber), [`sap.m.ObjectStatus`](https://openui5.hana.ondemand.com/#/entity/sap.m.ObjectStatus)\).

|
|**`sap.m.Select`**

To ensure that the value states are displayed in all situations and devices, the control is now enabled to display the text set in the `valueStateText` property when the dropdown is opened.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.SelectValueState/preview).

|
|**`sap.ui.layout.cssgrid.CSSGrid`**

You can now set the `CSSGrid` breakpoints \(large, medium, or small\) to depend on the size of the parent container rather than the device screen size \(media query\). To enable the feature, use the new `containerQuery` property in the `GridResponsiveLayout` class. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.cssgrid.GridResponsiveLayout) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.layout.sample.GridResponsiveness/preview).

|

***

<a name="loio77e1dcc27c494d60ba0a03759b706e89__section_r5v_3h5_zcb"/>

### Demo Kit Improvements

|**API Reference Tree**

We have improved the *API Reference* tree to use proper nesting of the OpenUI5 symbols based on a strict hierarchical structure. Fewer elements are now displayed on the root level, thus improving the user experience and shortening the time the user spends trying to find a specific symbol in the tree structure.

 ![](loio1e5ae735b1004f4eb807106d68ad71e2_HiRes.png) 

|

