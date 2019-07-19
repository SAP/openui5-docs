<!-- loio32d4b9c2b981425dbc374d3e9d5d0c2e -->

| loio |
| -----|
| 32d4b9c2b981425dbc374d3e9d5d0c2e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/32d4b9c2b981425dbc374d3e9d5d0c2e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/32d4b9c2b981425dbc374d3e9d5d0c2e)</div>

## Grid Controls

OpenUI5 provides several different grid layouts that are suitable for different use cases.

***

<a name="loio32d4b9c2b981425dbc374d3e9d5d0c2e__section_r2d_sdw_hhb"/>

### `sap.f.GridContainer`

The `sap.f.GridContainer` is a layout control used to align tiles, cards, or other controls in configuration, such as an overview page. It provides a regular grid system in which all rows have the same height and all columns have the same width. Each item can be configured to take different number of rows and columns inside that mesh. If rows span is unknown for an item, it is automatically calculated by the `GridContainer`, based on the height of the item.

***

<a name="loio32d4b9c2b981425dbc374d3e9d5d0c2e__section_vmk_v43_4fb"/>

### `sap.f.GridList`

The `sap.f.GridList` is a layout control that provides the flexibility to display list items in a two-dimensional grid. It extends the `sap.m.ListBase` control and therefore receives all of its features. The layout used is based on the CSS display grid and the control has a default configuration that displays the list items in a grid.

***

<a name="loio32d4b9c2b981425dbc374d3e9d5d0c2e__section_b1w_bp3_4fb"/>

### `sap.ui.layout.cssgrid.CSSGrid`

The `sap.ui.layout.cssgrid.CSSGrid` is a layout control, used to create full-page layouts or user interface elements. It is based on the browser-native CSS display grid and works by the HTML standard specification of a grid. This grid is two-dimensional, meaning that it is possible to specify both rows and columns. The dimensions and position of a single item can be configured, for example, an item can take two rows and two columns from the grid. The control can be used along with the `sap.m.FlexBox` control as a one-dimensional alternative for layouting.

***

<a name="loio32d4b9c2b981425dbc374d3e9d5d0c2e__section_xlx_bp3_4fb"/>

### `sap.ui.layout.Grid`

The `sap.ui.layout.Grid` control defines how many columns are displayed depending on the available screen size with a maximum of 12. The height of a single row is always based on the content of the highest item in that row.

***

<a name="loio32d4b9c2b981425dbc374d3e9d5d0c2e__section_csk_543_4fb"/>

### Overview of Grids and Supported Features

| **Feature Supported?** | `sap.f.GridContainer` | `sap.f.GridList` | `sap.ui.layout.cssgrid.CSSGrid` | `sap.ui.layout.Grid` |
|------------------------|-----------------------|------------------|---------------------------------|----------------------|
| **Complies with the grid specification according to the HTML Standard** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Supports Internet Explorer and version 15 or below of Microsoft Edge** | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif)<sup>1</sup> | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif)<sup>1</sup> | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
| **Number of columns supported** |Unlimited|Unlimited|Unlimited|Up to 12|
| **Can configure row height, column width, and gap dimensions** | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Supports auto calculation of rows per item** | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Can fill empty spaces in the grid** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Items flow direction** |Horizontal only|Horizontal and vertical|Horizontal and vertical|Horizontal only|
| **Can configure item position** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Can configure item dimensions** The ability to define how many rows and columns an item should take.| ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Supports columns breathing** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
| **Supports templating** The possibility to use one of the predefined layout templates or to create a custom template for specific layouts.| ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>2</sup> | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>2</sup> | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Supports screen-size breakpoints** | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>2</sup> | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>2</sup> | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
| **Supports container-size breakpoints** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>2</sup> | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>2</sup> | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
| **Supports indentation** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
| **Can control items visibility based on breakpoints** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
| **Supports keyboard handling** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Supports growing** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Supports sorting, filtering and grouping** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Supports headers and footer**s| ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
| **Supports selection and highlighting** | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |

1\) Microsoft Internet Explorer 11 has limited support for the underlying `display:grid` technology. Specific layouts are enabled for Internet Explorer 11. Microsoft Edge supports `display:grid` for versions above 16.  
 2\) By using the `customLayout` aggregation.

**Related information**  


[API Reference: `sap.ui.layout.cssgrid.CSSGrid`](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.cssgrid.CSSGrid)

[Samples: `sap.ui.layout.cssgrid.CSSGrid`](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.cssgrid.CSSGrid)

[API Reference: `sap.ui.layout.Grid`](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.Grid)

[Samples: `sap.ui.layout.Grid`](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.Grid)

[API Reference: `sap.f.GridContainer` \(Experimental\)](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer)

[Samples: `sap.f.GridContainer` \(Experimental\)](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer)

[API Reference: `sap.f.GridList`](https://openui5.hana.ondemand.com/#/api/sap.f.GridList)

[Samples: `sap.f.GridList`](https://openui5.hana.ondemand.com/#/entity/sap.f.GridList)

