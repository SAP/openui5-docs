<!-- loiof1bd982c780445c6ae2ccdf2b3f478da -->

| loio |
| -----|
| f1bd982c780445c6ae2ccdf2b3f478da |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f1bd982c780445c6ae2ccdf2b3f478da) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f1bd982c780445c6ae2ccdf2b3f478da)</div>

## Keyboard Handling for Two-Dimensional Navigation

The following keys and key combinations are used for navigation in two-dimensional item containers \(for example, calenders and tables\).

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Key combination</th>
			<th>Behavior</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> *LEFT*</td>
			<td>If focus is on an item, move focus one item to the **left**. If focus is on the first item of a row, move focus to the last item of the previous row. If focus is on the first item, do nothing.</td>
		</tr>
		<tr>
			<td> *RIGHT*</td>
			<td>If focus is on an item, move focus one item to the **right**. If focus is on the last item of a row, move focus to the first item of the next row. If focus is on the last item, do nothing.</td>
		</tr>
		<tr>
			<td> *UP*</td>
			<td>If focus is on an item, move focus to the item **above**. If focus is on the first item of a column, do nothing.</td>
		</tr>
		<tr>
			<td> *DOWN*</td>
			<td>If focus is on an item, move focus to the item **below**. If focus is on the last item of a column, do nothing.</td>
		</tr>
		<tr>
			<td>*PAGE UP*</td>
			<td> If focus is on an item, move focus **up** by page size.
 > Note:
 > Page size can be set by apps; default page size is 5 rows.

 If there are less items available than page size, move focus to the first item. If focus is on the first item, do nothing.</td>
		</tr>
		<tr>
			<td>*PAGE DOWN*</td>
			<td> If focus is on an item, move focus **down** by page size.
 > Note:
 > Page size can be set by apps; default page size is 5 rows.

 If there are less items available than page size, move focus to the first item. If focus is on the last item, do nothing.</td>
		</tr>
		<tr>
			<td>* ALT PAGE UP *</td>
			<td> If focus is on an item, move focus **left** by page size.
 > Note:
 > Page size can be set by apps; default page size is 5 columns.

 If there are less items available than page size, move focus to the first item. If focus is on the first item, do nothing.</td>
		</tr>
		<tr>
			<td>* ALT PAGE DOWN *</td>
			<td> If focus is on an item, move focus **right** by page size.
 > Note:
 > Page size can be set by apps; default page size is 5 columns.

 If there are less items available than page size, move focus to the first item. If focus is on the first item, do nothing.</td>
		</tr>
		<tr>
			<td>*HOME*</td>
			<td>If focus is on an item, move focus to the **first** item on the same row. If focus is on the first item of a row, move focus to the first item.</td>
		</tr>
		<tr>
			<td>*END*</td>
			<td>If focus is on an item, move focus to the **last** item of the same row. If focus is on the last item of a row, move focus to the last item.</td>
		</tr>
		<tr>
			<td>* CTRL HOME *</td>
			<td>If focus is on an item, move focus to the **first** item of the same column. If focus is on the first item of a column, move focus to the first item.</td>
		</tr>
		<tr>
			<td>* CTRL END *</td>
			<td>If focus is on an item, move focus to the **last** item of the same column. If focus is on the last item of a column, move focus to the last item.</td>
		</tr>
	</tbody>
</table>

