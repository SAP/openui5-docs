<!-- loio7d914317c0b64c23824bf932cc8a4ae1 -->

| loio |
| -----|
| 7d914317c0b64c23824bf932cc8a4ae1 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/7d914317c0b64c23824bf932cc8a4ae1) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/7d914317c0b64c23824bf932cc8a4ae1)</div>

## Extension for Data Aggregation

The OData V4 Model supports features of the OData Extension for Data Aggregation V4.0 specification.

The binding parameter `$$aggregation` at [`sap.ui.model.odata.v4.ODataModel#bindList`](https://openui5.hana.ondemand.com/#api/sap.ui.model.odata.v4.ODataModel/methods/bindList) holds the information needed for data aggregation. It may be changed by [`sap.ui.model.odata.v4.ODataListBinding#setAggregation`](https://openui5.hana.ondemand.com/#api/sap.ui.model.odata.v4.ODataListBinding/methods/setAggregation). It cannot be combined with an explicit system query option `$apply` because it implicitly derives `$apply`. You can find more information also in the [OData Extension for Data Aggregation V4.0 specification](http://docs.oasis-open.org/odata/odata-data-aggregation-ext/v4.0/odata-data-aggregation-ext-v4.0.html).

Two scenarios are supported:

-   You can provide properties for grouping and aggregation. An appropriate system query option `$apply` is derived from those and the list binding still provides a flat list of contexts \("rows"\), but with additional aggregated properties \("columns"\). In addition, you can request grand total values for aggregatable properties. In this case, an extra row appears at the beginning of the flat list of contexts and contains the grand total values as well as empty values for all other properties.

    ```
    
    					    **Example XML View With Grand Total**
    
    
    					    ``` js
        <table:Table fixedRowCount="1"
         rows="{
          path : '/BusinessPartners',
          parameters : {
           $$aggregation : {
            aggregate : {
             SalesAmountSum  : {
              grandTotal : true,
              name : 'SalesAmount',
              with : 'sap.unit_sum'
             }
            },
            group : {
             Region : {}
            }
           },
           $count : true,
           $filter : 'SalesAmountSum gt 1000000',
           $orderby : 'SalesAmountSum desc'
          }}">
         <table:Column template="Region">
          <Label text="Region"/>
         </table:Column>
         <table:Column hAlign="End">
          <Label text="Sales Amount"/>
          <table:template>
           <Text text="{path : 'SalesAmountSum', type : 'sap.ui.model.odata.type.Decimal'}" />
          </table:template>
         </table:Column>
         <table:Column>
          <Label text="Currency"/>
          <table:template>
           <Text text="{path : 'SalesAmountSum@Analytics.AggregatedAmountCurrency',
            type : 'sap.ui.model.odata.type.String'}" />
          </table:template>
         </table:Column>
        </table:Table>
        ```
    
    
    				
    ```

-   You can provide group levels to determine a hierarchy of expandable group levels in addition to the leaf nodes determined by the `groupable` and `aggregatable` properties. Only a **single** group level is currently supported and it cannot be expanded yet. Group levels cannot be combined with filtering or with the system query option `$count : true`.


> Note:
> Multi-unit situations are not supported with data aggregation. An error is thrown if the `sap.ui.model.odata.v4.ODataListBinding` detects a multi-unit situation.
> 
> Given a service with groupable properties **G1,…,Gn**, an aggregatable property **A** with related unit property **U**. An aggregated OData request is said to return a multi-unit situation, if the following conditions are fulfilled for the requested aggregation levels **G1,…,Gj** :
> 
> 1.  The result contains two or more entities with identical values for the groupable properties **G1,…,Gj**.
> 
> 2.  The entities from **1.** have **different** values for the unit-property **U** and any value for **A**.
> 
> 
> 

> Note:
> The grand total calculation is currently only supported for the standard aggregation functions `sum`, `min`, and `max` as well as for custom aggregates that use these functions. This also applies to displaying subtotals of group levels.
> 
> 

