<!-- loio5a184109b1ec44e7ab7e43d40ef56847 -->

| loio |
| -----|
| 5a184109b1ec44e7ab7e43d40ef56847 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5a184109b1ec44e7ab7e43d40ef56847) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5a184109b1ec44e7ab7e43d40ef56847)</div>

## What's New in OpenUI5 1.101

With this release OpenUI5 is upgraded from version 1.100 to 1.101.

***

<a name="loio5a184109b1ec44e7ab7e43d40ef56847__section_qwl_pb5_zcb"/>

### Improved Features

<a name="loio5a184109b1ec44e7ab7e43d40ef56847__table_tpj_dvq_mfb"/> 


<table>
<tr>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

**Drag and Drop**

We have now enabled drag and drop for use on mobile devices for iOS 15.1 and higher releases and the latest Chrome 98 for Android.

> ### Note:  
> The availability of drag and drop depends on whether the respective browser supports drag and drop.

For more information, see [Drag and Drop](Drag_and_Drop_3ddb6cd.md).



</td>
</tr>
<tr>
<td valign="top">

We have prevented the overwriting of the high contrast setting of Windows for all OpenUI5 themes when using Chrome and Edge browsers.



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V2 Model**

The new `sap.ui.model.odata.v2.Context#delete` method deletes a binding's `Context` irrespective of its status, including inactive, transient, and persisted contexts.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v2.Context%23methods/delete).



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   We now support the setting of a different binding context for a relative list binding with transient contexts.

-   `sap.ui.model.odata.v4.AnnotationHelper#format` now evaluates the `com.sap.vocabularies.common.v1.Timezone` annotation of properties of the `Edm.DateTimeOffset` type. A composite binding with an `sap.ui.model.odata.type.DateTimeWithTimezone` type is generated, showing the date/time and the time zone. For more information, see [AnnotationHelper](Meta_Model_for_OData_V4_7f29fb3.md#loio7f29fb3ce5964d8090038a9d3cdf5060__section_AnnoHelp).

-   We provide a new sample application that demonstrates how data in different controls can be kept in sync. The application also shows important aspects of consuming a draft-enabled back-end service.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel/sample/sap.ui.core.sample.odata.v4.Draft).




</td>
</tr>
</table>

***

<a name="loio5a184109b1ec44e7ab7e43d40ef56847__section_rqn_wd5_zcb"/>

### Improved Controls

<a name="loio5a184109b1ec44e7ab7e43d40ef56847__table_qcq_dvq_mfb"/> 


<table>
<tr>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

**`sap.m.List, sap.m.Table, sap.m.Tree`**

For better user experience with a more visual approach and a more conversational tone, these tables can now use another control, for example, the `sap.m.IllustratedMessage` control, based on the new `noData` aggregation. This control can be used if no data is available for a table. For more information, see the [API Reference for the `noData` aggregation](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase) and the [API Reference for `IllustratedMessage`](https://openui5.hana.ondemand.com/#/api/sap.m.IllustratedMessage). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Wizard`**

-   We have introduced the `navigationChange` event. It is fired when the current visible step is changed by either tapping on the `sap.m.WizardProgressNavigator` or scrolling through the steps. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Wizard) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Wizard/sample/sap.m.sample.WizardSingleStep). 

-   We have also removed the experimental flag for the `sap.m.WizardRenderMode` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.WizardRenderMode).




</td>
</tr>
<tr>
<td valign="top">

**sap.m.upload.UploadSet**

You can now sort, group, and filter the items within `UploadSet`.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.upload.UploadSet) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.upload.UploadSet).



</td>
</tr>
</table>

***

<a name="loio5a184109b1ec44e7ab7e43d40ef56847__section_cps_cg5_zcb"/>

### Deprecations

<a name="loio5a184109b1ec44e7ab7e43d40ef56847__table_p1z_dvq_mfb"/> 


<table>
<tr>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://openui5.hana.ondemand.com/#/api/deprecated). 



</td>
</tr>
</table>

***

<a name="loio5a184109b1ec44e7ab7e43d40ef56847__section_g3r_bf5_zcb"/>

### SAP Fiori Elements

<a name="loio5a184109b1ec44e7ab7e43d40ef56847__table_fm5_dvq_mfb"/> 


<table>
<tr>
<th valign="top">

Description



</th>
</tr>
</table>

