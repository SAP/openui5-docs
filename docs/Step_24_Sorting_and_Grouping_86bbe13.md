<!-- loio86bbe132b9924c8496b70824af94a209 -->

| loio |
| -----|
| 86bbe132b9924c8496b70824af94a209 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/86bbe132b9924c8496b70824af94a209) | [demo kit latest release](https://sdk.openui5.org/topic/86bbe132b9924c8496b70824af94a209)</div>

## Step 24: Sorting and Grouping

To make our list of invoices even more user-friendly, we sort it alphabetically instead of just showing the order from the data model. Additionally, we introduce groups and add the company that ships the products so that the data is easier to consume.

***

### Preview

  
  
**The list is now sorted and grouped by the shipping company**

![](images/loio33f71b44bb644d1fa2a0ab14f1fcc02a_LowRes.png "The list is now sorted and grouped by the shipping company")

***

<a name="loio86bbe132b9924c8496b70824af94a209__section_sxl_41l_syb"/>

### Coding

You can view and download all files at [Walkthrough - Step 24](https://sdk.openui5.org/entity/sap.m.tutorial.walkthrough/sample/sap.m.tutorial.walkthrough.24).

***

<a name="loio86bbe132b9924c8496b70824af94a209__section_txl_41l_syb"/>

### webapp/view/InvoiceList.view.xml

```xml
<mvc:View
   controllerName="ui5.walkthrough.controller.InvoiceList"
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <List
      id="invoiceList"
      class="sapUiResponsiveMargin"
      width="auto"
      items="{
         path : 'invoice>/Invoices',
         sorter : {
            path : 'ProductName' 
         }
      }" >
      ...
   </List>
</mvc:View>
```

We add a declarative sorter to our binding syntax. As usual, we transform the simple binding syntax to the object notation, specify the path to the data, and now add an additional `sorter` property. We specify the data path by which the invoice items should be sorted, and UI5 will take care of the rest. By default, the sorting is ascending, but you could also add a property `descending` with the value `true` inside the sorter property to change the sorting order.

If we run the app now we can see a list of invoices sorted by the name of the products.

***

### webapp/view/InvoiceList.view.xml

```xml
<mvc:View
    controllerName="ui5.walkthrough.controller.InvoiceList"
    xmlns="sap.m"
    xmlns:mvc="sap.ui.core.mvc">
    <List
        id="invoiceList"
        headerText="{i18n>invoiceListTitle}"
        class="sapUiResponsiveMargin"
        width="auto"
        items="{
            path : 'invoice>/Invoices',
            sorter : {
                path : 'ShipperName',
                group : true
            }

        }">
        ...
    </List>
</mvc:View>
```

We modify the view and add a different sorter, or better; we change the sorter and set the attribute `group` to true. We also specify the path to the `ShipperName` data field. This groups the invoice items by the shipping company.

As with the sorter, no further action is required. The list and the data binding features of OpenUI5 will do the trick to display group headers automatically and categorize the items in the groups. We could define a custom group header factory if we wanted by setting the `groupHeaderFactory` property, but the result looks already fine.

**Related Information**  


[API Reference: `sap.ui.model.Sorter`](https://sdk.openui5.org/api/sap.ui.model.Sorter)

[Sample: List - Grouping](https://sdk.openui5.org/entity/sap.m.List/sample/sap.m.sample.ListGrouping)

