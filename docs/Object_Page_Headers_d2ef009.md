<!-- loiod2ef0099542d44dc868719d908e576d0 -->

| loio |
| -----|
| d2ef0099542d44dc868719d908e576d0 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d2ef0099542d44dc868719d908e576d0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d2ef0099542d44dc868719d908e576d0)</div>

## Object Page Headers

The `sap.uxap.ObjectPageLayout` control has two types of header - classic header and dynamic header.

***

<a name="loiod2ef0099542d44dc868719d908e576d0__section_qj3_tpk_sbb"/>

### Overview

The `sap.uxap.ObjectPageLayout` control implements the snapping header concept. This means that the upper part of the header \(Header Title\) always stays visible, while the lower part \(Header Content\) can scroll out of view.

The common pattern is that the most important information describing the object, such as title, subtitle, and image is in the Header Content area when the header is expanded, and moves to the Header Title area when the header is collapsed \(snapped - its lower part scrolled out of view\).

   
  
`sap.uxap.ObjectPageLayout` header in expanded state<a name="loiod2ef0099542d44dc868719d908e576d0__fig_odn_ypk_sbb"/>

 ![](loio329ff57b73e54ddca241e9ff693cd6c8_HiRes.png "sap.uxap.ObjectPageLayout header in expanded state") 

The following image shows the collapsed \(snapped\) header is where the Header Content area is scrolled out and not visible, and the main information is visible in the Header Title area.

   
  
`sap.uxap.ObjectPageLayout` Header in Collapsed \(snapped\) State<a name="loiod2ef0099542d44dc868719d908e576d0__fig_odw_ypk_sbb"/>

 ![](loiof4ec6baca13b4bd993715464cbf4461f_HiRes.png "sap.uxap.ObjectPageLayout Header in Collapsed (snapped) State") 

***

<a name="loiod2ef0099542d44dc868719d908e576d0__section_chx_wpk_sbb"/>

### The Classic Header

Up to version 1.52, only `sap.uxap.ObjectPageHeader` could have been used to build up the `sap.uxap.ObjectPageLayout` header.

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Header area</th>
			<th> `sap.uxap.ObjectPageLayout` aggregation</th>
			<th>App must provide:</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Header Title</td>
			<td> `headerTitle` \(0..1\)</td>
			<td>An instance of the `sap.uxap.ObjectPageHeader` control</td>
		</tr>
		<tr>
			<td>Header Content</td>
			<td> `headerContent` \(0..n\)</td>
			<td>An array of arbitrary controls.

 > Note:
 > `sap.uxap.ObjectPageHeaderContent` control is used internally to display the controls.
			</td>
		</tr>
	</tbody>
</table>

The app provides an instance of `sap.uxap.ObjectPageHeader` as the value of the `headerTitle` aggregation, and arbitrary controls as the value of the `headerContent` aggregation \(which are internally added to an instance of the `sap.uxap.ObjectPageHeaderContent` control\).

***

<a name="loiod2ef0099542d44dc868719d908e576d0__section_sxg_s5k_sbb"/>

### The Dynamic Header \(Since Version 1.52\)

As of version 1.52, a new `sap.uxap.ObjectPageDynamicHeaderTitle` control can be used to build a dynamic header for `sap.uxap.ObjectPageLayout`.

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Header Area</th>
			<th> `sap.uxap.ObjectPageLayout` aggregation</th>
			<th>App Must Provide:</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Header Title</td>
			<td> `headerTitle` \(0..1\)</td>
			<td>An instance of the `sap.uxap.ObjectPageDynamicHeaderTitle` control</td>
		</tr>
		<tr>
			<td>Header Content</td>
			<td> `headerContent` \(0..n\)</td>
			<td>An array of arbitrary controls.

 > Note:
 > `sap.uxap.ObjectPageDynamicHeaderContent` control is used internally to display the controls.
			</td>
		</tr>
	</tbody>
</table>

Again, the app provides an instance of `sap.uxap.ObjectPageDynamicHeaderTitle` as the value of the `headerTitle` aggregation and a list of controls for the `headerContent` aggregation \(`sap.uxap.ObjectPageLayout` uses internally `sap.uxap.ObjectPageDynamicHeaderContent` to lay out the controls\).

**Related information**  


[API Reference: `sap.uxap.ObjectPageLayout`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.uxap.ObjectPageLayout.html)

[API Reference: `sap.uxap.ObjectPageHeader`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.uxap.sap.uxap.ObjectPageHeader.html)

[API Reference: `sap.uxap.ObjectPageDynamicHeaderTitle`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.uxap.ObjectPageDynamicHeaderTitle.html)

