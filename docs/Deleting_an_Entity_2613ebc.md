<!-- loio2613ebc835764abd9aefd2e6fa8b7392 -->

| loio |
| -----|
| 2613ebc835764abd9aefd2e6fa8b7392 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/2613ebc835764abd9aefd2e6fa8b7392) | [demo kit latest release](https://sdk.openui5.org/topic/2613ebc835764abd9aefd2e6fa8b7392)</div>

## Deleting an Entity

The `Context.delete` method deletes an entity on the server and updates the user interface accordingly.

When you delete the entity from a list binding, the corresponding row is removed. When you delete the entity from a context binding, the binding and all dependent bindings lose the reference.

**Example: Delete From a Table**

```js

onDeleteSalesOrder : function () {
    var oTable = this.getView().byId("SalesOrders"),
        oSalesOrderContext = oTable.getSelectedItem().getBindingContext();
 
    oSalesOrderContext.delete("$auto").then(function () {
        oTable.removeSelections();
        MessageBox.alert("Deleted Sales Order",
            {icon : MessageBox.Icon.SUCCESS, title : "Success"});
    }, function (oError) {
        MessageBox.alert("Could not delete Sales Order: "
            + oError.message, {icon : MessageBox.Icon.ERROR, title : "Error"});
    });
},
```

**Related Information**  


[Context.delete](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/delete)

