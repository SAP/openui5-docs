<!-- loio648e360fa22d46248ca783dc6eb44531 -->

| loio |
| -----|
| 648e360fa22d46248ca783dc6eb44531 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/648e360fa22d46248ca783dc6eb44531) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/648e360fa22d46248ca783dc6eb44531)</div>

## Data Reuse

***

The OData V4 model keeps data with respect to bindings. This allows different views on the same data, but it also means that data is not automatically shared between bindings. Here, we explain mechanisms for sharing data to avoid redundant requests and to keep the same data in different controls in sync.

***

<a name="loio648e360fa22d46248ca783dc6eb44531__section_fkt_g1r_mgb"/>

### Relative Bindings

An OData V4 binding may or may not trigger own data requests. Data sharing between a parent binding and a dependent binding is possible if the dependent binding does not raise its own data requests. Both bindings will then use the same data storage and may share data that is accessed by both bindings. To this end, the dependent binding has to be relative to a V4 context, `sap.ui.model.odata.v4.Context`, and the dependent binding must not have any binding parameters. The only exception is the binding parameter `$$noPatch` of the OData V4 property binding.

The following example shows a typical master-detail scenario with a list of objects and the details of the selected object:

``` xml
<mvc:View id="master">
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

Upon selection of an object in the list, the row context is used as the binding context for the detail section. Note that this row context will always be a V4 context, `sap.ui.model.odata.v4.Context`. Setting the binding context resolves the context binding of the detail section. Missing properties are requested with the following request. Note that properties already present in the list are not requested again.

`GET SalesOrderList('0500000001')?$select=NetAmount,Note`

Editing of any properties shown in the list, as well as the details section in either place, will automatically be reflected in the other place as well.

***

<a name="loio648e360fa22d46248ca783dc6eb44531__section_g5j_v1r_mgb"/>

### Return Values of Bound Actions

The data of the returned entity is synchronized into the binding parameter of the bound action if the following conditions apply:

-   The conditions for a return value context as described for the `execute` method of `sap.ui.model.odata.v4.ODataContextBinding` are fulfilled.

    For more information, see the [API Reference: `sap.ui.model.odata.v4.ODataContextBinding#execute`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataContextBinding%23methods/execute). 

-   The returned entity has the same key as the binding parameter.


***

<a name="loio648e360fa22d46248ca783dc6eb44531__section_uz4_fzq_xlb"/>

### Shared Requests

The same data needs to be requested only once for use cases like value help controls where the following conditions apply:

-   The same view on the same resource is used in different bindings.

-   The data is immutable, i.e. it does not change on the server and is not changed on the client.


For this, you may use the `$$sharedRequest` binding parameter for all the list bindings that do not need to request the data individually.

> Note:
> These bindings have to be immutable.
> 
> 

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

The `$$sharedRequest` binding parameter is used automatically for list bindings of [value list](Value_Lists_ab267a6.md) models.

