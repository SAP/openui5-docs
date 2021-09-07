<!-- loiof081cf0a64784c62aa653e80036659f0 -->

| loio |
| -----|
| f081cf0a64784c62aa653e80036659f0 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f081cf0a64784c62aa653e80036659f0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f081cf0a64784c62aa653e80036659f0)</div>

## What's New in OpenUI5 1.82

With this release OpenUI5 is upgraded from version 1.81 to 1.82.

***

<a name="loiof081cf0a64784c62aa653e80036659f0__section_z2h_fh5_zcb"/>

### Third-Party Library Upgrades


<table>
<tr>
<td>

**`Handlebars.js` Library**

The `Handlebars.js` library has been upgraded from version 4.4.3 to 4.7.6.



</td>
</tr>
<tr>
<td>

**Upgrade to New jQuery Version**

We have upgraded the third-party jQuery library from jQuery 2.2.3 to jQuery 3.5.1. Several measures have been implemented to make this new version of jQuery delivered with OpenUI5 as compatible to the previous version as feasible. In particular, we have introduced a compatibility layer to ensure that most of your existing application or control code won't need adjustment. This could, however, introduce incompatibilities to the new jQuery version. For more information, see [Upgrading from a Version Below 1.82](Upgrading_from_a_Version_Below_1.82_147eef9.md) to understand any current and possible future impact.



</td>
</tr>
</table>

***

<a name="loiof081cf0a64784c62aa653e80036659f0__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td>

**Badge Implementation**

Badges display very short and important information that attracts the user’s attention. We have made improvements in these controls to implement badge:

-   `**sap.ui.integration.widgets.Card**` – the badge is no longer in experimental state. For more information, see the [Text Badge](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/badge) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/badge) in the Card Explorer.
-   `**sap.m.Button**` - the badge acts both as a visual eye catcher and as a counter to display a maximum of 4 digits or characters. It can be applied to any button type, but we recommend that you only use it on the `Default`, `Ghost`, `Transparent`, and `Emphasized` button types.

     ![](loio205fd119d9a64cdb957c4efa70ad4367_LowRes.png) 

    For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Button/sample/sap.m.sample.ButtonWithBadge).

-   The **`<ui-integration-card>` HTML custom element** now supports text badges. For more information, see the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/htmlConsumption) in the Card Explorer.



</td>
</tr>
</table>

***

<a name="loiof081cf0a64784c62aa653e80036659f0__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

**Five New Icons Available in the *SAP Fiori Tools* Icon Font**

 ![](loio8bfb35f3b630408abb4d49f9d6b52f8d_LowRes.png) 

Find the icon that fits your needs via the [OpenUI5 Icon Explorer](https://openui5.hana.ondemand.com/test-resources/sap/m/demokit/iconExplorer/webapp/index.html).



</td>
</tr>
<tr>
<td>

**OpenUI5 OData V2 Model**

With the new version of the OpenUI5 OData V2 model, we introduced the new `ignoreMessages` binding parameter for the `sap.ui.model.odata.ODataPropertyBinding`. If `ignoreMessages` is set to `true`, model messages are not propagated to the binding. This is useful if a part of a composite binding is required for formatting, but not displayed itself.

Depending on their format options, some composite types, such as `sap.ui.model.type.Currency`, automatically ignore model messages for some of their parts. Setting this parameter to `true` or `false` overrules this default behavior.



</td>
</tr>
<tr>
<td>

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The new `$$ignoreMessages` binding parameter is available for `sap.ui.model.odata.v4.ODataPropertyBinding`. If `$$ignoreMessages` is set to `true`, model messages are not propagated to the binding. This is useful if a part of a composite binding is required for formatting, but not displayed itself. Depending on their format options, some composite types such as `sap.ui.model.type.Currency` or `sap.ui.model.odata.type.Unit` automatically ignore model messages for some of their parts. Explicitly setting this parameter overrules this default.
-   The `sap.ui.model.odata.v4.Context#requestProperty` method now also works for properties that are not part of the `$select` option of the underlying binding and were not fetched previously.
-   The `sap.ui.model.odata.v4.Context#requestSideEffects` method now supports absolute paths. These must start with the entity container of the service, for example `/com.sap.gateway.default.iwbep.tea_busi.v0001.Container/TEAMS`.
-   `The sap.ui.model.odata.v4.Context#delete` method is now supported for kept-alive contexts. A context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.



</td>
</tr>
</table>

***

<a name="loiof081cf0a64784c62aa653e80036659f0__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td>

`**sap.ui.integration.widgets.Card**`

We have updated the UI5 Web Components dependency of the Adaptive Cards to the v1.0.0-rc.8 version. With this update the Adaptive Cards receive the theming and custom theming support. Now you can use both High Contrast Black and High Contrast White themes, or add a custom theme, as the Web Components are compatible with the UI Theme Designer tool. For more information, see the [High Contrast Black](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html?sap-ui-theme=sap_fiori_3_hcb#/explore/adaptive) and the [High Contrast White](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html?sap-ui-theme=sap_fiori_3_hcw#/explore/adaptive) samples in the Card Explorer.



</td>
</tr>
</table>

