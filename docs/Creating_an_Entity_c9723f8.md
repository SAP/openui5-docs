<!-- loioc9723f8265f644af91c0ed941e114d46 -->

| loio |
| -----|
| c9723f8265f644af91c0ed941e114d46 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/c9723f8265f644af91c0ed941e114d46) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/c9723f8265f644af91c0ed941e114d46)</div>

## Creating an Entity

The `sap.ui.model.odata.v4.ODataListBinding#create` method creates a new entity. Users can interact with a newly created entity even before it has been sent to the server.

To create new entities, [`ODataListBinding#create`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/create) uses the list binding's update group ID as group ID. For more information how this group ID is determined, see the documentation for the binding-specific parameter `$$updateGroupID` of [`ODataModel#bindList`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/methods/bindList).

A newly created entity can be inserted at the start or at the end of the list. This new entity is transient until it is successfully submitted, see [`Context#isTransient`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/isTransient). The initial data for the created entity can be supplied via the parameter `oInitialData` and modified via property bindings. Properties that are not part of the initial data show the default value from the service metadata on the UI, but they are not sent to the server. If there is no default value, null is used instead, even if the property is not nullable. Updates for the transient entity are collected and added to the POST request which creates the entity on the server.

Inserting an entity at the end of the list is done via the `bAtEnd` parameter in the `create` call. This is only possible, if the list's length has been requested via the system query option `$count`.

To delete transient entities, use [`Context#delete`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/delete). Transient entities are also deleted when you reset the changes for the list binding on which the entity has been created, see [`ODataListBinding#resetChanges`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/resetChanges) and [`ODataModel#resetChanges`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/methods/resetChanges). The promise returned by [`Context#created`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/created) is rejected in all cases where the created entity is deleted before it is created in the backend. As long as the list binding has a transient entity, [`ODataListBinding#hasPendingChanges`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/hasPendingChanges) returns `true` and the following methods of [`ODataListBinding`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding) raise an error: `refresh`, `filter`, and `sort`. The deletion of another entity of the same list binding is possible.

> Note:
> The position of the created entity may change after the methods `refresh`, `filter`, or `sort` of an [`ODataListBinding`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding).
> 
> 

If you have called [`ODataListBinding#create`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/create) on a list binding where the update group ID has [`SubmitMode.API`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.SubmitMode) and the creation of the entity on the server fails, the creation is repeated with the next call of [`submitBatch`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/methods/submitBatch) for this group. If the update group ID has [`SubmitMode.Auto`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.SubmitMode) or [`SubmitMode.Direct`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.SubmitMode) and the creation fails, the creation is repeated automatically with the next update for the entity. `submitBatch` can also be used for update group IDs with `SubmitMode.Auto` to repeat, independently of an update. The error returned by the server is passed to the [`MessageManager`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.message.MessageManager) and the promise you get via [`Context.created`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/created) is not rejected. Each time the data for the created entity is sent to the server, a [`Context.createSent`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/createSent) event is fired. Each time the client receives a response for the creation, a [`Context.creatCompleted`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/createCompleted) event is fired, independent of whether the creation was successful, or not.

If you have called [`ODataListBinding#create`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/create) on a list binding with an application group ID, and the creation of the entity on the server fails, the creation is repeated with the next call of [`ODataModel#submitBatch`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/methods/submitBatch) for this group. If the update group ID is `$auto` or `$direct`, and the creation fails, the creation is repeated automatically with the next update for the entity. The error is passed to the [`MessageManager`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.message.MessageManager) and the promise you get via [`Context#created`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/created) is not rejected. Each time the data for the created entity is sent to the server, a [`createSent`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/createSent) event is fired. Each time the client receives a response for the creation, a [`createCompleted`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/events/createCompleted) event is fired, independent of whether the creation was successful, or not.

> Note:
> Lock the UI each time the \(`POST`\) request for the creation is sent to the server and unlock it, when the reponse from the server for that \(`POST`\) request is processed, because updates in between result in errors. If the update group ID is [`SubmitMode.API`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.SubmitMode), you can lock the UI when calling [`ODataModel#submitBatch`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/methods/submitBatch) and unlock it again when the promise returned by `ODataModel#submitBatch` is resolved or rejected. However, if the update group ID is `SubmitMode.Auto` or `SubmitMode.Direct`, use the `createSent` event to lock the related UI and the `createCompleted` event to unlock it.
> 
> 

```
// suppose this list binding has no own update group; it uses the model's update group instead (an application group)
...
        onCreateSalesOrder : function (oEvent) {
            var oContext = this.getView().byId("SalesOrders").getBinding("items")
                    .create({
                        "Note" : "My new Sales Order",
                        "NoteLanguage" : "E",
                        "BuyerID" : "0100000000",
                        "CurrencyCode" : "EUR"
                    });
 
            // Note: This promise fails only if the transient entity is deleted
            oContext.created().then(function () {
                    // sales order successfully created
                }, function (oError) {
                    // handle rejection of entity creation; if oError.canceled === true then the transient entity has been deleted 
                });
        },
 
        onDeleteSalesOrder : function () {
            var oSalesOrderContext = this.getView().byId("SalesOrders").getSelectedItem().getBindingContext();
 
            oSalesOrderContext.delete("$auto").then(function () {
                    // sales order successfully deleted
               }, function (oError) {
                    // do error handling
               });
        },
 
        onSaveSalesOrder : function () {
            var oView = this.getView();
 
            function resetBusy() {
                oView.setBusy(false);
            }
 
            // lock UI until submitBatch is resolved, to prevent errors caused by updates while submitBatch is pending
            oView.setBusy(true);
             
            oView.getModel().submitBatch(oView.getModel().getUpdateGroupId()).then(resetBusy, resetBusy);
        },
...
```

> Note:
> To ensure that for a list binding all expanded data is available as soon as the promise returned by [`Context#created`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/created) is resolved, an additional single `GET` request for the newly created entity is sent automatically once the `POST` request has arrived.
> 
> If you want to skip this additional single `GET` request, call [`ODataListBinding#create`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/create) with parameter `bSkipRefresh=true`.
> 
> 

The `promise` returned by [`Context#created`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/created) is resolved when the entity represented by this context has been created in the backend. Once the promise is resolved, [`Context#getPath`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/getPath) returns a path including the key predicate of the new entity. For returning the path including the key predicates, all key properties need to be available.

**Related information**  


[sap.ui.model.odata.v4.ODataListBinding](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding)

[sap.ui.model.odata.v4.ODataModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel)

[sap.ui.model.odata.v4.Context](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context)

[sap.ui.core.message.MessageManager](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.message.MessageManager.html)

