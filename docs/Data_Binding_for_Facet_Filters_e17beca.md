<!-- loioe17becae8bf446ac92f169b726373f0a -->

| loio |
| -----|
| e17becae8bf446ac92f169b726373f0a |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e17becae8bf446ac92f169b726373f0a) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e17becae8bf446ac92f169b726373f0a)</div>

## Data Binding for Facet Filters

`FacetFilter` fully supports the OpenUI5 data binding concept.

As the information for the facet filter usually resides in the application backend, data binding is commonly used to populate the `FacetFilter` properties and aggregations.

Applications using OData do not bind the `FacetFilterItem.selected` property since this is not available from the backend service. Fortunately, selections are maintained internally on the client by the `FacetFilterList` until the list is destroyed.

**Related information**  


[Facet Filter Selection](Facet_Filter_Selection_ef860fc.md)

