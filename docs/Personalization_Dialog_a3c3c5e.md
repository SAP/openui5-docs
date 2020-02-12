<!-- loioa3c3c5eb54bc4cc38e6cfbd8e90c6a01 -->

| loio |
| -----|
| a3c3c5eb54bc4cc38e6cfbd8e90c6a01 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a3c3c5eb54bc4cc38e6cfbd8e90c6a01) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a3c3c5eb54bc4cc38e6cfbd8e90c6a01)</div>

## Personalization Dialog

The `sap.m.P13nDialog` control provides a dialog to personalize tables, such as adapting the order of columns or filtering table content.

For more information about this control, see the [API Reference](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.m.P13nDialog.html) and the [samples](https://openui5.hana.ondemand.com/explored.html#/entity/sap.m.P13nDialog/samples).

***

### Overview

The `P13nDialog` control offers you a personalization dialog and allows the consuming application to define various settings for tables using panels. The panels represent the settings on the user interface. In order to register them to the control, the `sap.m.P13nPanel` aggregation is used.

***

### Details

The following panels are available in the `P13nDialog` control:

-   `sap.m.P13nSortPanel`

    Defines the sorting in a column in an ascending or descending order.

-   `sap.m.P13nFilterPanel`

    Defines filter conditions for a column.

-   `sap.m.P13nGroupPanel`

    Defines the grouping of columns.

-   `sap.m.P13nDimMeasurePanel`

    Defines the chart-specific settings.


The following buttons are available in the dialog:

-   *OK*

    Closes the personalization dialog.

    In some cases, the consuming application must transfer the settings of the end user to the table, for example, when sorting and filtering.

-   *Cancel*

    Closes the personalization dialog.

    All changes made by the end user in the dialog that is currently open are rejected.

-   *Restore*

    Personalization dialog remains open.

    All changes made by the end user are set back to the initial state.

    > Note:
    > The control only provides the visual representation of the table settings on the user interface. The consuming application must ensure the settings are actually changed in the table.
    > 
    > 


