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


<table>
<tr>
<th valign="top">

 **Feature Supported?** 



</th>
<th valign="top">

 `sap.f.GridContainer` 



</th>
<th valign="top">

 `sap.f.GridList` 



</th>
<th valign="top">

 `sap.ui.layout.cssgrid.CSSGrid` 



</th>
<th valign="top">

 `sap.ui.layout.Grid` 



</th>
</tr>
<tr>
<td valign="top">

 **Complies with the grid specification according to the HTML Standard** 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Number of columns supported** 



</td>
<td valign="top">

Unlimited



</td>
<td valign="top">

Unlimited



</td>
<td valign="top">

Unlimited



</td>
<td valign="top">

Up to 12



</td>
</tr>
<tr>
<td valign="top">

 **Can configure row height, column width, and gap dimensions** 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Supports auto calculation of rows per item** 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Can fill empty spaces in the grid** 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Items flow direction** 



</td>
<td valign="top">

Horizontal only



</td>
<td valign="top">

Horizontal and vertical



</td>
<td valign="top">

Horizontal and vertical



</td>
<td valign="top">

Horizontal only



</td>
</tr>
<tr>
<td valign="top">

 **Can configure item position** 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

**Can configure item dimensions**

The ability to define how many rows and columns an item should take.



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Supports columns breathing** 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

**Supports templating**

The possibility to use one of the predefined layout templates or to create a custom template for specific layouts.



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Supports screen-size breakpoints** 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Supports container-size breakpoints** 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>1</sup> 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Supports indentation** 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Can control items visibility based on breakpoints** 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Supports keyboard handling** 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif)<sup>2</sup> 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Supports growing** 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Supports sorting, filtering and grouping** 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Supports headers and footer**s



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
<tr>
<td valign="top">

 **Supports selection and highlighting** 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
<td valign="top">

 ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) 



</td>
</tr>
</table>

1\) By using the `customLayout` aggregation.  
 2\) Two-dimensional keyboard navigation is supported. Users can navigate through the contained controls using the arrow keys.

-   **[sap.f.GridContainer](sap_f_GridContainer_cca5ee5.md "The GridContainer allows you to align tiles, cards or other controls in
		configuration, such as an overview page.")**  
The `GridContainer` allows you to align tiles, cards or other controls in configuration, such as an overview page.
-   **[sap.f.GridList](sap_f_GridList_2fc256b.md "The GridList allows you to use different types of layouts responsible for the positioning and responsiveness of the
		content.")**  
The `GridList` allows you to use different types of layouts responsible for the positioning and responsiveness of the content.
-   **[sap.ui.layout.cssgrid.CSSGrid](sap_ui_layout_cssgrid_CSSGrid_d6fc40b.md "The CSSGrid is a flexible layout, based on the two-dimensional, browser-native grid system, using the standard CSS
		property display with value grid. It allows for flexible positioning of user interface elements, inside
		horizontal and vertical grid structures.")**  
The `CSSGrid` is a flexible layout, based on the two-dimensional, browser-native grid system, using the standard CSS property `display` with value `grid`. It allows for flexible positioning of user interface elements, inside horizontal and vertical grid structures.
-   **[sap.ui.layout.Grid](sap_ui_layout_Grid_43ae317.md "A flexible layout that positions its items in a 12-column flow layout.")**  
A flexible layout that positions its items in a 12-column flow layout.

**Related Information**  


[API Reference: `sap.ui.layout.cssgrid.CSSGrid`](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.cssgrid.CSSGrid)

[Samples: `sap.ui.layout.cssgrid.CSSGrid`](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.cssgrid.CSSGrid)

[API Reference: `sap.ui.layout.Grid`](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.Grid)

[Samples: `sap.ui.layout.Grid`](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.Grid)

[API Reference: `sap.f.GridContainer`](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer)

[Samples: `sap.f.GridContainer`](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer)

[API Reference: `sap.f.GridList`](https://openui5.hana.ondemand.com/#/api/sap.f.GridList)

[Samples: `sap.f.GridList`](https://openui5.hana.ondemand.com/#/entity/sap.f.GridList)

