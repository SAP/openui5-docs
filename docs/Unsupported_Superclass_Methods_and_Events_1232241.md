<!-- loio1232241b99d7437ba3614698d53dfa4b -->

| loio |
| -----|
| 1232241b99d7437ba3614698d53dfa4b |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/1232241b99d7437ba3614698d53dfa4b) | [demo kit latest release](https://sdk.openui5.org/topic/1232241b99d7437ba3614698d53dfa4b)</div>

## Unsupported Superclass Methods and Events

Certain methods derived from OpenUI5 model and binding superclasses are not supported in OData V4 model classes or have limited support.

The following methods and events are affected by this. For more information, see the corresponding API documentation for each method and event in the Demo Kit.

<a name="loio1232241b99d7437ba3614698d53dfa4b__table_yby_zws_xv"/>Unsupported Methods


<table>
<tr>
<th valign="top">

Class



</th>
<th valign="top">

Method



</th>
</tr>
<tr>
<td valign="top">

`sap.ui.model.odata.v4.ODataMetaModel`

\(See [sap.ui.model.odata.v4.ODataMetaModel](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataMetaModel) in the Demo Kit\)



</td>
<td valign="top">

`bindTree`

`getOriginalProperty`

`isList`

`refresh`

`setLegacySyntax`



</td>
</tr>
<tr>
<td valign="top">

`sap.ui.model.odata.v4.ODataModel`

\(See [sap.ui.model.odata.v4.ODataModel](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel) in the Demo Kit\)



</td>
<td valign="top">

`bindTree`

`destroyBindingContext`

`getObject`

`getOriginalProperty`

`getProperty`

`isList`

`setLegacySyntax`



</td>
</tr>
<tr>
<td valign="top">

`sap.ui.model.odata.v4.ODataContextBinding`

\(See [sap.ui.model.odata.v4.ODataContextBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding) in the Demo Kit\)



</td>
<td valign="top">

`isInitial`

`refresh` \(limited support only\)

`resume` \(limited support only\)

`suspend` \(limited support only\)



</td>
</tr>
<tr>
<td valign="top">

`sap.ui.model.odata.v4.ODataListBinding`

\(See [sap.ui.model.odata.v4.ODataListBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding) in the Demo Kit\)



</td>
<td valign="top">

`getDistinctValues`

`isInitial`

`refresh` \(limited support only\)

`resume` \(limited support only\)

`suspend` \(limited support only\)



</td>
</tr>
<tr>
<td valign="top">

`sap.ui.model.odata.v4.ODataPropertyBinding`

\(See [sap.ui.model.odata.v4.ODataPropertyBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataPropertyBinding) in the Demo Kit\)



</td>
<td valign="top">

`isInitial`

`refresh` \(limited support only\)

`resume`

`setValue` \(limited support only\)

`suspend`



</td>
</tr>
</table>

<a name="loio1232241b99d7437ba3614698d53dfa4b__table_ccv_gys_xv"/>Unsupported Events


<table>
<tr>
<th valign="top">

Class



</th>
<th valign="top">

Event



</th>
</tr>
<tr>
<td valign="top">

`sap.ui.model.odata.v4.ODataMetaModel`

\(See [sap.ui.model.odata.v4.ODataMetaModel](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataMetaModel) in the Demo Kit\)



</td>
<td valign="top">

`parseError`

`propertyChange`

`requestCompleted`

`requestFailed`

`requestSent`



</td>
</tr>
<tr>
<td valign="top">

`sap.ui.model.odata.v4.ODataModel`

\(See [sap.ui.model.odata.v4.ODataModel](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel) in the Demo Kit\)



</td>
<td valign="top">

`parseError`

`propertyChange`

`requestCompleted`

`requestFailed`

`requestSent`



</td>
</tr>
</table>

**Related Information**  


[sap.ui.model.odata.v4.ODataMetaModel](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataMetaModel)

[sap.ui.model.odata.v4.ODataModel](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel)

[sap.ui.model.odata.v4.ODataContextBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding)

[sap.ui.model.odata.v4.ODataListBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding)

[sap.ui.model.odata.v4.ODataPropertyBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataPropertyBinding)

