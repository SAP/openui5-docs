<!-- loio22ee78b422614b40ad4c1938dc23d967 -->

| loio |
| -----|
| 22ee78b422614b40ad4c1938dc23d967 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/22ee78b422614b40ad4c1938dc23d967) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/22ee78b422614b40ad4c1938dc23d967)</div>

## Context API

The OData V4 model's list and context bindings create `sap.ui.model.odata.v4.Context` objects which enhance `sap.ui.model.Context` and provide the following methods:

-   `getObject` or `getProperty` for synchronous and `requestObject` or `requestProperty` for asynchronous access to values; the methods to access a property can provide the value in internal or external format

-   `getBinding` to retrieve the binding which created the context

-   `getIndex` to return the context's list index provided the context has been created by an `ODataListBinding`


> Note:
> For `getObject` and `requestObject`, the data is cloned if the given path points to a non-primitive type. This ensures that internal OData model values cannot be modified.
> 
> When a property is read in external format, the format is solely determined by the type defined in the OData meta data of the property, and not by the type or formatter specified for the binding.
> 
> 

``` js

// assume oEvent is an event fired when a button is pressed in an item of a table bound to /SalesOrderList
sOrderID = oEvent.getSource().getBindingContext().getProperty("SalesOrderID"); // the SalesOrderID in the same item

// get a value in external format e.g. "1.234,23" instead of 1234.23
sGrossAmount = oEvent.getSource().getBindingContext().getProperty("GrossAmount", true);
```

For more information, see [sap.ui.model.odata.v4.Context](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context) in the Demo Kit.

