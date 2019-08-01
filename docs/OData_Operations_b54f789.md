<!-- loiob54f7895b7594c61a83fa7257fa9d13f -->

| loio |
| -----|
| b54f7895b7594c61a83fa7257fa9d13f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b54f7895b7594c61a83fa7257fa9d13f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b54f7895b7594c61a83fa7257fa9d13f)</div>

## OData Operations

The OData V4 model supports OData operations \(`ActionImport`, `FunctionImport`, bound `Actions` and bound `Functions`\). Unbound parameters are limited to primitive values.

***

### Simple Function Bindings

You gain access to a `FunctionImport` by binding it to a view element. If there are no parameters and there is no need to control the point in time when the function is called, you can simply bind the OData path like this:

``` js
<Text text="{path: '/GetNumberOfAvailableItems()', type: 'sap.ui.model.odata.type.Int16'}"/>
```

This binding path represents the function's return value. The model calls the function immediately when a control requests this value.

The type must be specified if the return value is a primitive type.

***

### Deferred Operation Bindings

Often it is not feasible for the operation to be called immediately, for example if there are parameters that the user has to enter first. In such cases, use an ODataContextBinding as element binding at a layout element in the view, for example a `<Form>` or a `<VBox>` \(see the [ODataContextBinding](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ODataContextBinding.html) API documentation in the Demo Kit\). Mark the operation as **deferred** by inserting an ellipsis \("..."\) in the brackets, for example `GetNextAvailableItem(...)`. Access the return value from child elements using relative bindings. When used like this, the context binding is called an **operation binding** or more specifically, a **function binding** or **action binding** depending on the type of OData operation it is used for.

If the operation binding defers operation execution, you need to call its `execute` method to execute the operation. See below for an example.

**View:**

``` xml
<Form id="getNextAvailableItem" binding="{/GetNextAvailableItem(...)}">
    <Label text="Description"/>
    <Text text="{Description}"/>
    <Button text="Call the function" press="onGetNextAvailableItem"/>
</Form>
```

**Controller:**

``` js
onGetNextAvailableItem : function (oEvent) {
    this.getView().byId("getNextAvailableItem").getObjectBinding().execute();
}
```

In the above example, the function import is bound to a form \(which has an ID that we need later\). The text field showing a property of the result is a child of this form. It has a relative binding to the property `"Description"`.

If the function returns a primitive value or a collection, the binding for the result must be `"{value}"` as shown in the 2 examples below:

**View:**

``` xml
<Form id="getNumberOfAvailableItems" binding="{/GetNumberOfAvailableItems(...)}">
    <Label text="Number of available items:"/>
    <Text text="{value}"/>
    <Button text="Call the function" press="onGetNumberOfAvailableItems"/>
</Form>
```

```
<VBox id="getAvailableItems" binding="{path : '/GetAvailableItems(...)', parameters : {$select : 'ProductName', 'ProductId'}}">
    <List id="xyz" items="{value}">
        <items>
            <ObjectListItem title="{ProductName}" />
        </items>
    </List>
</VBox>
```

`execute` returns a promise which is resolved if the operation was successful and rejected with an error if this was not the case. Note that the promise is **not** fufilled with the action's result: Use dependent bindings to access the result.

`refresh` is silently ignored on a deferred function binding as long as it has not yet been executed. Afterwards, a `refresh` calls the function again.

***

### Action Bindings

Action bindings must be deferred, otherwise the application cannot control when the action is executed. A deferred action binding is declared exactly like a deferred function binding:

**View:**

``` xml
<Form id="Submit" binding="{/Submit(...)}">
    <Button text="Submit the action" press="onSubmit"/>
</Form>
```

You append "\(...\)" even though the action's resource URL does not contain them. However, they are needed to mark the binding as deferred. In `execute`, the binding uses the metadata to distinguish between action and function and to build the correct operation resource path.

`refresh` is always silently ignored on a deferred action binding to prevent the action from being executed accidentally \(for example by calling the `refresh` method on the ODataModel instance `oModel.refresh()`\).

***

### Operation Parameters

Operation parameters can be set by calling the function `setParameter` on the operation binding, as shown in this example:

**Controller:**

``` js
onSubmit : function (oEvent) {
    this.getView().byId("Submit").getObjectBinding().setParameter("Comment", sComment).execute();
}
```

***

### Bound Actions and Functions

So far, the examples always used operations at root level, addressed via an action import or function import. However, it is also possible to bind an action or a function to another resource of the service. This can be an entity, a collection of entities or an entity property.

Bound actions or functions are controlled in the same way as unbound operations; append `(...)` to the binding path for the control's property.

To call actions or functions bound to a single entity, entity property, or navigation property use a relative binding. The following sample calls the "invoice created" action on the sales order selected in the corresponding table:

``` js
var oModel = this.getView().getModel(),
    oTable = this.getView().byId("SalesOrders"),
    oSalesOrderContext = oTable.getSelectedItem().getBindingContext(),
    oAction = oMoodel.bindContext("name.space.InvoiceCreated(...)", oSalesOrderContext);
 
oAction.execute().then(
    function () {
        MessageToast.show("Invoice created for sales order " + oSalesOrderContext.getProperty("SalesOrderID"));
    },
    function (oError) {
        MessageBox.alert(oError.message, {
            icon : MessageBox.Icon.ERROR,
            title : "Error"});
        });
    }
);
```

To call actions or functions bound to a collection specified by an OData entity set, you can create a context binding with an absolute path, or with a relative path for the operation \(for example `name.space.DestroyOutdated(...)"`\) and the header context of a list binding as parent context. The following sample shows a button press event handler which calls the `destroy outdated` action on the `LeaveRequests` entity set.

``` js
var oModel = this.getView().getModel();
 
oModel.bindContext("/LeaveRequests/name.space.DestroyOutdated(...)").execute();
```

The same example with a relative binding and the header context of the list binding as parent context:

``` js
var oModel = this.getView().getModel(),
    // assume there is a table with ID "leaveRequests" and its items aggregation bound to "/LeaveRequests"
    oListBinding = this.byId("leaveRequests").getBinding("items"),
    oHeaderContext = oListBinding.getHeaderContext();

oModel.bindContext("name.space.DestroyOutdated(...)", oHeaderContext).execute(); 
```

> Note:
> -   The path of an operation binding may also start with a navigation property.
> 
>     Example: The operation binding has a relative path `BP_2_PRODUCT/name.space.Change(...)`. You set its binding context from the selected item in a table bound to `/BusinessPartners`. When you call `execute` on the operation binding, the "change" action is executed with the selected business partner's navigation property `BP_2_PRODUCT` as binding parameter.
> 
> -   The parent binding of a deferred operation must not be a deferred operation itself.
> 
> 
> 

***

<a name="loiob54f7895b7594c61a83fa7257fa9d13f__section_osx_m5l_gdb"/>

### Advertised Operations

According to the [OData 4.0 specification \("11.5.2 Advertising Available Operations within a Payload"\)](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part1-protocol/odata-v4.0-errata03-os-part1-protocol-complete.html#_Toc453752309) services may return available actions and functions bound to a particular entity as part of the entity representation within the payload. Data for an advertised operation within an entity is sent as property starting with `#<namespace>.<action>` of that entity. If the entity does not advertise the operation, it does not contain this property. To access the advertised operation in a binding, the same format has to be used. See the following example:

> Note:
> Enable a button to trigger an action **AcSetIsOccupied** available on entity type of entity set **EMPLOYEES** depending on advertisement of this action on the entity **EMPLOYEES\('1'\)**
> 
> 

```
<FlexBox binding="{/EMPLOYEES('1')}">
    <Button text="Set occupied" enabled="{= !!%{#com.sap.gateway.default.iwbep.tea_busi.v0001.AcSetIsOccupied} }"/>
</FlexBox>
```

Here a button is enabled only if the action **AcSetIsOccupied** is advertised for the entity **EMPLOYEES\('1'\)**. The `%` operator is used to set the internal type to `any` because the advertised action is sent as an object. The double negation `!!` converts this object to a boolean value that is needed by the `enabled` control property.

If no advertised action was returned in the payload, `undefined` \(or `null` in OData 4.01 in case of advertised non-availability\) is returned as value for the binding. This translates to false in the expression above.

If there is an additional list of non-binding parameter names to identify a specific overload, then they need to be given in the binding path as well, for instance: `%{#Model.RemainingVacation(Year)}`.

> Note:
> The bound action advertisement is added to $select automatically if the model parameter [`autoExpandSelect`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/constructor) is set.
> 
> 

To access the metadata of an operation, the double hash \(`##`\) syntax has to be used as is illustrated in the next example:

> Note:
> Binding against metadata of an action
> 
> ```
> var oContext = oModel.createBindingContext("/EMPLOYEES('1')/##com.sap.gateway.default.iwbep.tea_busi.v0001.AcSetIsOccupied");
> var oMetaModel = oContext.getModel();
> oMetaModel.requestObject("0/$ReturnType/$Type", oContext).then(alert);
> ```
> 
> 

Here a context is created pointing to the metadata of the action and afterwards the type is accessed using this context.

This approach can also be used with XML templating where [`createBindingContext`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/methods/createBindingContext) is called internally.

***

<a name="loiob54f7895b7594c61a83fa7257fa9d13f__section_qnb_qyv_tz"/>

### Access Operation Results

You can access the results of the operation by calling `getObject()` from the bound context.

``` js
// let oOperation be the operation's context binding
oOperation.execute().then(function () {
    *HIGHLIGHT START*// Note: execute does not deliver the results
*HIGHLIGHT END*
    var oResults = oOperation.getBoundContext().getObject();
    ...
});
```

The promise returned by the operation binding's [`execute`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataContextBinding/methods/execute) method may resolve with a *return value context* provided the conditions specified in [`execute`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataContextBinding/methods/execute) are met. The operation binding may be bound to an entity or a collection of entities.

The typical use case for *return value context* is when you call a bound operation with a context **C1** defining its binding parameter and the bound operation returns a *different version* of the entity used as binding parameter. **C1** is the binding context of an "object page" container displaying properties of the corresponding entity. You need to replace **C1** as binding context of the object page by the*return value context*. This way, the *different version* of the entity is displayed without a further read request. If the bound operation returns the entity used as binding parameter, the changes will automatically be copied to the binding parameter.

If the operation binding fulfills the conditions for returning a context, you can set the parameter `$$inheritExpandSelect` for the binding: The request for the bound operation is then sent with the same `$expand` and `$select` query options used to load the operation's binding parameter. This way you guarantee that all fields of the object page are available in the operation response.

Sample object page to display an **Artist** entity

```
<form:SimpleForm id="objectPage">
    <Toolbar>
        <Button text="Edit" enabled="{IsActiveEntity}" press=".onEdit"/>
    </Toolbar>
    <Label text="ID"/> <Text text="{ArtistID}"/>
    <Label text="Is Active"/> <Text text="{IsActiveEntity}"/>
    <Label text="Name"/> <Input value="{Name}" />
    ...
</form:SimpleForm>
```

Controller code to display the active version of **Artist 42** initially and switch to draft version on *Edit*

```
// display "active" version of artist initially
onInit : function () {
    var oActiveArtistContext = oModel
        	.bindContext("/Artists(ArtistID='42',IsActiveEntity=true)")
        	.getBoundContext();
    this.byId("objectPage").setBindingContext(oActiveArtistContext);
},
 
// display the "inactive" version of the entity returned by the "EditAction"
onEdit : function () {
    var that = this;
    oModel.bindContext("name.space.EditAction(...)", this.byId("objectPage").getBindingContext(), {$$inheritExpandSelect : true})
        .execute()
        .then(function (oInactiveArtistContext) {
            that.byId("objectPage").setBindingContext(oInactiveArtistContext);
        });
}
```

**Related information**  


[OData Version 4.0 Part 1, 11.5 Operations](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)

[ODataContextBinding](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.v4.ODataContextBinding.html)

