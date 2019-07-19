<!-- loio10ca58b701414f7f93cd97156f898f80 -->

| loio |
| -----|
| 10ca58b701414f7f93cd97156f898f80 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/10ca58b701414f7f93cd97156f898f80) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/10ca58b701414f7f93cd97156f898f80)</div>

## Automatic determination of $expand and $select

With automatic determination of `$expand` and `$select` \("auto-$expand/$select" in short\), the OData V4 Model computes `$expand` and `$select` query options for service requests from binding paths specified for control properties. This has the following advantages:

1.  You don't have to add or change `$select` or `$expand` in the binding parameters yourself.

2.  Auto-$expand/$select only selects data needed for the UI, so that you get a minimal response size and improved performance.


You switch on auto-$expand/$select by setting the flag `autoExpandSelect` during [model construction](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/constructor).

It is still possible to specify `$expand` and `$select` in the binding parameters. This is useful if you need to access properties which are not bound on the UI. When auto-$expand/$select is switched on, it is not possible to change `$expand` and `$select` via the binding's [changeParameters](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/changeParameters) API. You don't have specify **key properties** in the binding's `$select` parameter if they aren't bound on the UI. These are selected automatically because keys are required in many scenarios, for example, to compute the edit-URL to update an entity.

In auto-$expand/$select mode, a parent binding aggregates the binding paths and query options of its child bindings in its `$select` and `$expand` options, so that they do not send own data services requests. This aggregation is only possible in the following cases:

1.  If the request for the parent binding is **not sent** and the child binding is a list or context binding which has only OData system query options in its parameters, or is a property binding.

2.  If the request for the parent binding is **already sent** and the request already contains the aggregation for the child binding in its `$expand` and `$select`.


In other cases the child binding is not aggregated and sends an own request.

The list binding for the table in the following sample leads to the following request \(reduced to `$expand` and `$select` parameters\):

`SalesOrderList?$select=BuyerName,LifecycleStatus,Note,SalesOrderID&$expand=SO_2_BP($select=BusinessPartnerID,CompanyName)`

``` xml
<Table items="{/SalesOrderList}"
  ...
  <items>
    <ColumnListItem>
      <cells> <Text text="{BuyerName}"/> </cells>
      <cells> <Text text="{SO_2_BP/CompanyName}"/> </cells>
      <cells> <Input enabled="{= %{LifecycleStatus} === 'N' }" value="{Note}"/> </cells>
    </ColumnListItem>
  </items>
</Table>
```

If you use a list binding with factory function with auto-$expand/$select, you need to specify the binding parameters `$expand` and `$select` for all properties that may be needed by the factory function.

> Note:
> During automatic determination of `$expand` and `$select` the factory function is called with a "virtual" context, that returns `undefined` for `[getProperty](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/getProperty)` calls.
> 
> 

