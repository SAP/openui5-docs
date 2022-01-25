<!-- loiob39a11b47d994e9cb81c7e80946ed976 -->

| loio |
| -----|
| b39a11b47d994e9cb81c7e80946ed976 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b39a11b47d994e9cb81c7e80946ed976) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b39a11b47d994e9cb81c7e80946ed976)</div>

## What's New in OpenUI5 1.96

With this release OpenUI5 is upgraded from version 1.95 to 1.96.

***

<a name="loiob39a11b47d994e9cb81c7e80946ed976__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td valign="top">

**Enabling Apps to Comply with a Content Security Policy \(CSP\) without `eval()` and Inline Styles**

The OpenUI5 framework now allows you to run applications in environments with stricter CSPs. Large parts of OpenUI5 don't require `eval()` or similar functions, as well as inline styles, any longer. For details about the supported policies as well as recommendations on writing CSP-compliant applications, see [Content Security Policy](Content_Security_Policy_fe1a6db.md).

> ### Note:  
> To run in a CSP-enabled environment, your apps need to be prepared for the policy used. See [Content Security Policy](Content_Security_Policy_fe1a6db.md).



</td>
</tr>
<tr>
<td valign="top">

**New Theme Available for SAP Fiori User Experience \(Experimental\)**

We have introduced a new theme, the preview version of the *Horizon* visual theme for SAP Fiori \(theme ID: `sap_horizon`\), as an addition to the existing themes. To preview the new theme, see [https://openui5.hana.ondemand.com/?sap-ui-theme=sap\_horizon\#/controls](https://openui5.hana.ondemand.com/?sap-ui-theme=sap_horizon#/controls).

> ### Note:  
> The theme has the status 'experimental' and is thus subject to change. It must not be used as a basis for custom themes as long as the status is 'experimental'.



</td>
</tr>
</table>

***

<a name="loiob39a11b47d994e9cb81c7e80946ed976__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 Models**

We have provided the new `sap.ui.model.ListBinding#getFilters` method. It is available in all list bindings inheriting from `sap.ui.model.ListBinding`, for example in `sap.ui.model.odata.v4.ODataListBinding` and `sap.ui.model.odata.v2.ODataListBinding`. We also provide getters for `sap.ui.model.Filter`.



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V2 Model**

We have introduced the new `sap.ui.model.odata.v2.Context#created` method. For created records, the method returns a promise that resolves when the record is created in the back end. The promise is rejected if the record is deleted before being persisted in the back end.



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   You can now specify `$select` in addition to the `$$inheritExpandSelect` binding parameter of an [operation binding](OData_Operations_b54f789.md).

-   We have complemented the [OData V4 tutorial](OData_V4_bcdbde6.md) with additional chapters showing how to reuse data in a list-detail scenario.

-   You can now use [`Common.ValueListWithFixedValues`](https://github.com/SAP/odata-vocabularies/blob/main/vocabularies/Common.xml#L672:~:text=%3CTerm%20Name=%22-,ValueListWithFixedValues,-%22) in combination with [`Common.ValueListRelevantQualifiers`](https://github.com/SAP/odata-vocabularies/blob/main/vocabularies/Common.xml#L666:~:text=%3CTerm%20Name=%22-,ValueListRelevantQualifiers,-%22) if only one value list qualifier is relevant at a time. The `sap.ui.model.odata.v4.ODataMetaModel#requestValueListInfo` method returns the relevant value list for the `""` qualifier and provides the original qualifier as the `$qualifier` property of the value list mapping.




</td>
</tr>
</table>

***

<a name="loiob39a11b47d994e9cb81c7e80946ed976__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.MaskInput`**

We have introduced the `showClearIcon` property. If set to `true`, when there is text input it shows an additional icon that allows users to clear their input. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.MaskInput).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.MultiComboBox`**

We have implemented a checkbox that allows users to select all options, placed on top of the suggestions pop-up in the `sap.m.MultiComboBox` control. You can enable it using the `showSelectAll` property. The checkbox gives users the possibility to easily select/deselect all options, also when filtering them. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.MultiComboBox/sample/sap.m.sample.MultiComboBoxSelectAll). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   The List and Table cards now allow their content items to be grouped. You can use the new `group` manifest extension to configure the titles of the groups and the order of the items in these groups. For more information, see the [List Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/list) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/grouping) in the Card Explorer.

-   List cards now support attributes on an item level. They can show up to six attributes of their items’ attributes, which are displayed in one or two columns. For more information, see the [List Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/list) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/attributes) in the Card Explorer.

-   We have added a new `configurationChange` event, which is fired when some configuration settings are changed as a result of user interaction \(for example - filter change\). For more information, see the [Integration Cards API](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/api) section and the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/configurationChanges) in the Card Explorer.

-   We have introduced a new `sideIndicatorsAlignment` property to the `sap.f.cards.NumericHeader`. This property controls the alignment of the side indicators in the numeric header. It can have two values `Begin` \(default\) or `End`. For more information, see the [Numeric Header](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/headers/numeric) section in the Card Explorer.




</td>
</tr>
</table>

***

<a name="loiob39a11b47d994e9cb81c7e80946ed976__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://openui5.hana.ondemand.com/#/api/deprecated). 



</td>
</tr>
</table>

