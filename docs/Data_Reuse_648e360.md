<!-- loio648e360fa22d46248ca783dc6eb44531 -->

| loio |
| -----|
| 648e360fa22d46248ca783dc6eb44531 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/648e360fa22d46248ca783dc6eb44531) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/648e360fa22d46248ca783dc6eb44531)</div>

## Data Reuse

The OData V4 model keeps data with respect to bindings, which allows different views on the same data, but also means that data is not automatically shared between bindings. There are mechanisms for sharing data to avoid redundant requests and to keep the same data in different controls in sync.

***

<a name="loio648e360fa22d46248ca783dc6eb44531__section_relativeBindings"/>

### Relative Bindings

An OData V4 binding may or may not trigger own data requests. Data sharing between a parent binding and a dependent binding is possible if the dependent binding does not send its own data requests. Both bindings will then use the same data storage and may share data that is accessed by both bindings. To this end, the dependent binding has to be relative to a `sap.ui.model.odata.v4.Context`, and the dependent binding must not have any binding parameters. The only exception is the `$$noPatch` binding parameter of the OData V4 property binding.

The following example shows a typical list-detail scenario with a list of objects and the details of the selected object:

``` xml
<mvc:View id="list">
    <Table items="{/SalesOrderList}">
        <ColumnListItem>
            <Text text="{SalesOrderID}"/>
            <Text text="{SO_2_BP/CompanyName}"/>
            <Text text="{GrossAmount}"/>
            <Text text="{Currency}"/>
        </ColumnListItem>
    </Table>
</mvc:View>
 
<mvc:View id="detail">
    <Text text="{SalesOrderID}"/>
    <Text text="{SO_2_BP/CompanyName}"/>
    <Text text="{NetAmount}"/>       
    <Text text="{Currency}"/>
    <Text text="{Note}"/>
</mvc:View>
```

As we are using the model feature `autoExpandSelect`, we are getting a tailored `$select` clause in the `GET` request, and only the properties displayed in the table are read from the back end:

`GET SalesOrderList?$select=Currency,GrossAmount,SalesOrderID&$expand=SO_2_BP($select=BusinessPartnerID,CompanyName)&$skip=0&$top=100`

Upon selection of an object in the list, the row context is used as the binding context for the detail section. Note that this row context will always be a V4 context, `sap.ui.model.odata.v4.Context`. Setting the binding context resolves the property bindings of the detail section. Missing properties are requested with the following request. Note that properties already available are not requested again.

`GET SalesOrderList('0500000001')?$select=NetAmount,Note`

Editing any properties shown in the list or the detail section will automatically be reflected in the other place as well.

The OData V4 model can help you to get such a row context in the detail view controller, without knowledge about the list view. Mark the table's list binding in the list view with the `$$getKeepAliveContext` parameter; for more information see [`sap.ui.model.odata.v4.ODataModel#bindList`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel%23methods/bindList). Then call [`sap.ui.model.odata.v4.ODataModel#getKeepAliveContext`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel%23methods/getKeepAliveContext) with a binding path to the entity. If a marked list with the matching collection path exists and has a context with that path, this context is set to **keep-alive** \(see [Extending the Lifetime of a Context that is not Used Exclusively by a Table Collection](Data_Reuse_648e360.md#loio648e360fa22d46248ca783dc6eb44531__section_ELC) below\) and returned. Otherwise, the function returns `undefined`.

The following example assumes that the binding path of the sales order is given via the routing, with "key" matching the key predicate of the order. If `getKeepAliveContext` does not return a context, the controller creates a hidden context binding and uses its bound context as the binding context of the object page.

**Sample list view**

``` xml
<mvc:View id="list">
    <Table items="{
        path: '/SalesOrderList', 
        parameters: {
            $$getKeepAliveContext: true
        }}">
        <ColumnListItem>
            <Text text="{SalesOrderID}"/>
            <Text text="{SO_2_BP/CompanyName}"/>
            <Text text="{GrossAmount}"/>
            <Text text="{Currency}"/>
        </ColumnListItem>
    </Table>
</mvc:View>
```

**Detail view controller \(extract\)**

``` js
...
onPatternMatched : function (oEvent) {
    var oContext,
        // Note: We assume that the key predicate is encoded correctly because it has been
        // taken from an existing context when calling Router#navTo
        sPath = "/SalesOrderList" + oEvent.getParameter("arguments").key,
        oView = this.getView();
 
    oContext = oView.getModel().getKeepAliveContext(sPath);
    if (!oContext) {
        oContext = oView.getModel().bindContext(sPath).getBoundContext();
    }
    oView.setBindingContext(oContext);
...
```

***

<a name="loio648e360fa22d46248ca783dc6eb44531__section_g5j_v1r_mgb"/>

### Return Values of Bound Actions

The data of the returned entity is synchronized into the binding parameter of the bound action if the following conditions apply:

-   The conditions for a return value context as described for the `execute` method of `sap.ui.model.odata.v4.ODataContextBinding` are fulfilled.

    For more information, see the [API Reference: `sap.ui.model.odata.v4.ODataContextBinding#execute`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataContextBinding%23methods/execute). 

-   The returned entity has the same key predicate as the binding parameter.


***

<a name="loio648e360fa22d46248ca783dc6eb44531__section_uz4_fzq_xlb"/>

### Shared Requests

The same data needs to be requested only once for use cases like value help controls where the following conditions apply:

-   The same view on the same resource is used in different bindings.

-   The data is immutable, i.e. it does not change on the server and is not changed on the client.


For this, you may use the `$$sharedRequest` binding parameter for all the list bindings that do not need to request the data individually.

> ### Note:  
> A binding becomes read-only by using the `$$sharedRequest` parameter.

**Example:** Using the `$$sharedRequest` binding parameter:

``` xml

...
<Table items="{/SalesOrderList}">
    ...
   <ColumnListItem>
      <Select selectedKey="{BuyerID}"
            forceSelection="false"
            items="{path: '/BusinessPartnerList', templateShareable: false,
               parameters : {$$sharedRequest:true}}">
         <items>
            <core:ListItem key="{BusinessPartnerID}" text="{CompanyName}"/>
         </items>
      </Select>
   </ColumnListItem>
</Table>
...
```

The `$$sharedRequest` binding parameter is used automatically for list bindings of [value list](Value_Lists_ab267a6.md) models. Note that you can also set the `$$sharedRequest` parameter on the model, which means that all list bindings created within this model receive `$$sharedRequest=true` by default. For more information, see the [API Reference: `sap.ui.model.odata.v4.ODataModel#Constructor`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel%23constructor). 

***

<a name="loio648e360fa22d46248ca783dc6eb44531__section_ELC"/>

### Extending the Lifetime of a Context that is not Used Exclusively by a Table Collection

If, due to filtering or sorting of the list, the entity shown in the detail view is no longer part of the list, then the context pointing to this entity is destroyed. As a consequence, its data also vanishes inside the detail view. To prevent this drawback, `sap.ui.model.odata.v4.Context#setKeepAlive` can be used. This method allows you to extend the lifetime of a context, so that the context does not get destroyed when the corresponding entity is no longer part of the list.

**Example:**

``` js
...
  
// Optional: First remove the keep-alive setting for the previous context of the detail view
oOldContext = oView.getBindingContext();
if (oOldContext) {
    oOldContext.setKeepAlive(false);
}
  
// Share data between collection and view for a selected context, e.g. the second context
oNewContext = oTable.getItems()[1].getBindingContext();
oView.setBindingContext(oNewContext);
  
// Mandatory: Prevent destruction of the new context using the keep-alive setting
oNewContext.setKeepAlive(true, /*fnOnBeforeDestroy*/ function () {
    // React destruction of a kept-alive context
    var oDetail = oView.byId("detail");
 
    if (oDetail.getBindingContext() === oNewContext) {
        oDetail.setVisible(false);
    }
});
```

The data of the kept-alive context shown in list and detail view will be in sync, even if the kept-alive context is not shown in the list and loaded again later.

The optional callback function `fnOnBeforeDestroy` is called when the kept-alive context is destroyed. This happens if:

-   the list binding is relative and its context is changed,
-   the list binding is destroyed,
-   the context is deleted,
-   due to a refresh, the entity is no longer accessible via its previous path.

If you want to get [server messages](Server_Messages_in_the_OData_V4_Model_fbe1cb5.md) for the kept-alive context, but not for the list, use the `bRequestMessages` parameter. The messages for this context are requested immediately and with each subsequent refresh. You can then get the latest messages as a side effect via [`v4.Context#requestSideEffects`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/requestSideEffects).

