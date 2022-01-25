<!-- loioda7f3fc826f7418d9cc3b5a61285a08d -->

| loio |
| -----|
| da7f3fc826f7418d9cc3b5a61285a08d |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/da7f3fc826f7418d9cc3b5a61285a08d) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/da7f3fc826f7418d9cc3b5a61285a08d)</div>

## Drag-and-Drop Metadata

To influence the drag-and-drop behavior, use the metadata definition of a control.

***

<a name="loioda7f3fc826f7418d9cc3b5a61285a08d__section_itw_shl_bfb"/>

### Overview

You can use the `dnd` key for the drag-and-drop behavior of a control. Here is an example that shows you how the `dnd` key can be used:

``` js
Control.extend('my.CustomControl', {
      metadata : {
          properties : {
              value : { type : 'string' },
              width : { type : 'sap.ui.core.CSSSize', defaultValue : 'auto' }
          },
          *HIGHLIGHT START*dnd*HIGHLIGHT END* : { draggable: false, droppable: true },
          aggregations : {
              header : { type : "sap.ui.core.Control", multiple : false, *HIGHLIGHT START*dnd*HIGHLIGHT END* : true },
              items : { type: 'sap.ui.core.Control', multiple : true, *HIGHLIGHT START*selector*HIGHLIGHT END* : "#{id}-items", *HIGHLIGHT START*dnd*HIGHLIGHT END* : {

                       draggable: true, dropppable: true, layout: "Horizontal"
              } },
          }
     }

```

You can use the following attributes in the metadata of a control for drag and drop:

-   `draggable`: Defines whether the control or aggregation is draggable

    Default value of `draggable` is `false`.

-   `droppable`: Defines whether dropping is allowed for the control or within the control and/or from one of its aggregations to another one

    Default value of `droppable` is `false`.

-   `layout`: Defines the arrangement of the items in the aggregation

    Possible values are `Vertical` \(for example, rows in a table\) and `Horizontal` \(for example, columns in a table\). Default value of `layout` is `Vertical`.

-   `selector`: Defines the location of the aggregation in the control DOM

    This setting is recommended for the aggregation with cardinality `0..n`.


**Related Information**  


[API Reference: `sap.ui.core.Element.extend`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Element/methods/sap.ui.core.Element.extend)

