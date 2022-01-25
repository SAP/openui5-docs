<!-- loiob0f5c531e5034a27952cc748954cbe39 -->

| loio |
| -----|
| b0f5c531e5034a27952cc748954cbe39 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b0f5c531e5034a27952cc748954cbe39) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b0f5c531e5034a27952cc748954cbe39)</div>

## Suspend and Resume

You can suspend a [`list binding`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/suspend) or [`context binding`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataContextBinding/methods/suspend) with its suspend method. A suspended binding does not send data service requests nor does it fire change events. You can only suspend absolute bindings or bindings which are quasi-absolute. A quasi-absolute binding is a relative binding with a context which is not a [`sap.ui.model.odata.v4.Context`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context). You can only suspend a binding which is not yet suspended. For a relative binding having a V4 context, you may suspend the **root binding** of its binding hierarchy which is the \(quasi-\) absolute ancestor binding of this binding. The binding's method `getRootBinding` provides the root binding; for \(quasi-\) absolute bindings it returns the binding itself.

You can resume a suspended list or context binding with its `resume` method.

Typical use cases for suspend and resume are:

1.  **Trigger read requests for controls in the view later not when the view is initialized:**

    In some situations you may want to suppress OData requests and change events triggered by an OData V4 binding for a certain period of time. This is useful for value help dialogs, such as the value help for the `/BusinessPartnerList` when creating a sales order in the [`SalesOrders OData V4 sample`](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel/sample/sap.ui.core.sample.odata.v4.SalesOrders)*SalesOrders OData V4* sample in Demo Kit.

2.  **Avoid intermediate request when modifying the binding multiple times**

    You want to add a filter and change the sorting of a list binding. If the binding is not suspended, it will trigger a request after calling the `filter` method, and a second request after calling the `sort` method. If it is suspended, only one request with the updated filter and sort criteria is sent on `resume`.


The code below shows a snippet from the [`SalesOrders OData V4 sample`](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel/sample/sap.ui.core.sample.odata.v4.SalesOrders) which delays the request to `/BusinessPartnerList` until the *Create Sales Order* dialog is displayed.

> ### Note:  
> The `suspended` flag in the binding info triggers a call to the suspend method of the corresponding binding once it is created.

> ### Example:  
> View
> 
> ```
> <Dialog id="CreateSalesOrderDialog" title="Create New Sales Order">
> ...
>     <Input id="NewBuyerID" suggestionItems="{path : '/BusinessPartnerList', suspended : true}">
>         <suggestionItems>
>             <core:ListItem key="{BusinessPartnerID}" additionalText="{CompanyName}"  text="{BusinessPartnerID}"/>
>         </suggestionItems>
>     </Input>
> ...
> </Dialog>
> ```

The controller code to open the dialog resumes the list binding on `/BusinessPartnerList` and thus triggers the request.

> ### Example:  
> Controller
> 
> ```
> var oBPListBinding = this.byId("NewBuyerID").getBinding("suggestionItems");
>  
> if (oBPListBinding.isSuspended()) {
>     oBPListBinding.resume();
> }
> ```

When a binding is suspended, all methods which may trigger CRUD requests for this binding, for example `ODataListBinding.create` throw an error. This is also true for dependent bindings of a suspended binding. However methods that cause the binding to be refreshed completely are allowed. These methods are:

-   [`ODataContextBinding.changeParameters`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataContextBinding/methods/changeParameters) 

-   [`ODataContextBinding.refresh`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataContextBinding/methods/refresh)

-   [`ODataListBinding.changeParameters`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/changeParameters)

-   [`ODataListBinding.refresh`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/refresh)

-   [`ODataListBinding.filter`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/filter)

-   [`ODataListBinding.sort`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/sort)

-   [`ODataListBinding.setAggregation`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/setAggregation)

-   [`ODataListBinding.updateAnalyticalInfo`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/updateAnalyticalInfo)


> ### Caution:  
> It is not allowed to suspend operation bindings.

