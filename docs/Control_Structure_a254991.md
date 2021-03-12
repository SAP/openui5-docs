<!-- loioa254991b7bb040059a95b6a7f551ee51 -->

| loio |
| -----|
| a254991b7bb040059a95b6a7f551ee51 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a254991b7bb040059a95b6a7f551ee51) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a254991b7bb040059a95b6a7f551ee51)</div>

## Control Structure

The `sap.f.FlexibleColumnLayout` contains 3 instances of `sap.m.NavContainer` – one for each column.

It is logically similar to `sap.m.SplitContainer`, however, there are two main differences:

-   Displays up to 3 columns side by side \(as opposed to 2 columns\)
-   The width of the columns is not fixed, but flexible \(determined by the `layout` property\)

The following table respresents how the `FlexibleColumnLayout` roughly relates to the `NavContainer` and `SplitContainer` controls.

|Control

|API

|Number of Pages Displayed

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>---------</th>
			<th>-----</th>
			<th>---------------------------</th>
		</tr>
	</thead>
	<tbody>

			<td> `pages` \(aggregation\)
			</td>
			<td>1 page at a time
			</td>
		</tr>
		<tr>
			<td> `sap.m.SplitContainer` 
			</td>
			<td>`masterPages` \(aggregation\)
`detailPages` \(aggregation\)
			</td>
			<td>Up to 2 pages at a time \(2 instances of `NavContainer`\)
			</td>
		</tr>
		<tr>
			<td> `sap.f.FlexibleColumnLayout` 
			</td>
			<td>`beginColumnPages` \(aggregation\)
`midColumnPages` \(aggregation\)

`endColumnPages` \(aggregation\)

`layout` \(property of type `sap.f.LayoutType`, determining the relative widths of the 3 `NavContainers`\)
			</td>
			<td>Up to 3 pages at a time \(3 instances of `NavContainer`\)
			</td>
		</tr>
	</tbody>
</table>

