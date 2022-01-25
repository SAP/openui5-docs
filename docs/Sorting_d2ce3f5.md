<!-- loiod2ce3f51e5e34198b0c1a7f6ddd98def -->

| loio |
| -----|
| d2ce3f51e5e34198b0c1a7f6ddd98def |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d2ce3f51e5e34198b0c1a7f6ddd98def) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d2ce3f51e5e34198b0c1a7f6ddd98def)</div>

## Sorting

The OData V4 model supports server side sorting on lists.

To use server side sorting, set the operation mode to [sap.ui.model.odata.OperationMode.Server](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.odata.OperationMode.html%23.Server) as described unter [Filtering](Filtering_5338bd1.md).

`ODataListBinding` allows to set static and dynamic sorters:

-   For setting a static sorter, the `$orderby` system query option in the binding parameters is used. The static sorter value is sent with every data service request for the binding. The static sorter cannot be overwritten for an existing binding.

-   The dynamic sorter is a [sap.ui.model.odata.Sorter](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.Sorter.html) instance, or an array thereof in which case the sorters are concatenated. You can set the initial value for the dynamic sorter in [ODataModel.bindList](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/methods/bindList), or declaratively in an XML view with the sorter property in an aggregation's binding information. For setting the dynamic sorter, the [ODataListBinding.sort](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataListBinding/methods/sort) method is used. The sorter that is given here overwrites the initial value specified on binding construction.


Dynamic sorters are transformed to an OData `$orderby` system query option value and the static sorters are always appended as secondary sort criterion. In this example, the equipments are first ordered by `Category` \(dynamic sorter\) and then by `Name` \(secondary sort criterion, static sorter\). For a description of the `group` property, see [getGroup](https://openui5.hana.ondemand.com/#/api/sap.ui.model.Sorter/methods/getGroup).

**Example: Dynamic and static sorters**

```
`#js`
<Table growing="true" growingThreshold="5" id="Equipments"
    items="{
            path : '/Equipments',
            parameters : {
                $$operationMode : 'Server',
                $orderby : 'Name',                             <-- static sorter
                $select : 'Category,EmployeeId,ID,Name'
            },
            sorter : {                                      <-- dynamic sorter; can be overwritten by calling sort on the list binding
                path : 'Category',
                group : true                                <-- optional, see parameter `vGroup` of [sap.ui.model.Sorter](https://openui5.hana.ondemand.com/#/api/sap.ui.model.Sorter/constructor)
            }
        }">
```

In this example, the equipments are first ordered by `Category` \(dynamic sorter\) and then by `Name` \(secondary sort criterion, static sorter\).

