<!-- loio08197fa68e4f479cbe30f639cc1cd22c -->

| loio |
| -----|
| 08197fa68e4f479cbe30f639cc1cd22c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/08197fa68e4f479cbe30f639cc1cd22c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/08197fa68e4f479cbe30f639cc1cd22c)</div>

## sap.ui.table

Table-like controls, mainly for desktop scenarios.

> Note:
> The following sections only provide additional information for some of the controls. For a complete list of all controls and their documentation, see the [API Reference](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.html) and the [Samples](https://openui5.hana.ondemand.com/explored.html). 
> 
> 

***

### Row Virtualization

To improve rendering and memory performance, only the number of rows that are visible on the user interface are created internally for `sap.ui.table.Table` \(this is called "row virtualization"\). For example, if the table has enough space to render 20 rows, exactly 20 rows are created internally.

> Note:
> Imagine an OData service with 10 million entries. Keeping 10 million row controls, either inside or outside the DOM, is simply not technically feasible for most client devices. Also, a single table row usually contains additional controls inside each cell, such as `sap.m.Labels` or `sap.ui.unified.Currency` controls. The number of used control instances would then be multiplied by the number of columns for every row. Instead of creating all of these OpenUI5 controls for every data entry, the table virtualizes the rows, and in this way only a limited set of control instances are created for each table control instance.
> 
> 

***

### OData Model

OData as a RESTful protocol provides a specified and a generalized way to access back-end services via HTTP requests. The OpenUI5 OData model provides a stable module for querying OData services via the network. All `sap.ui.table.*` controls fully support data bindings over OData V2. Since OData services can hold millions of entries, and these entries have to be loaded somehow to the client and rendered, the `sap.ui.table.*` controls implement advanced paging mechanisms based on the underlying `ODataListBinding` and `ODataTreeBinding`. The OpenUI5 OData bindings take care of all necessary back-end requests to retrieve the currently-needed data entries. This is done as efficiently as possible with the minimum amount of back-end requests.

**Related information**  


[OData V2 Model](OData_V2_Model_.md#loio6c47b2b39db9404582994070ec3d57a2)

[API Reference: `sap.ui.table`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.table.html)

[Tables: Which One Should I Choose?](Tables_Which_One_Should_I_Choose_148892f.md)

[Supported Library Combinations](Supported_Library_Combinations_363cd16.md)

[Browser and Platform Support](Browser_and_Platform_Support_74b59ef.md)

