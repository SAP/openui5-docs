<!-- loioc6e0122ca9874844a214018bec02e74a -->

| loio |
| -----|
| c6e0122ca9874844a214018bec02e74a |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/c6e0122ca9874844a214018bec02e74a) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/c6e0122ca9874844a214018bec02e74a)</div>

## Properties and Property Bindings

You can use various types of binding for the properties in XML composite controls.

The fragment definition XML file defined in the previous section looks a lot like any other fragment that you might already be using in XML views. In this particular case, it defines only one nested `sap.m.Text` element. The text property is bound with the normal binding syntax to a special model, `$this`. `$this` refers to the interface of the `SimpleText` XML composite control.

Similar to other controls, you have the following options to use binding for the XML definition of an XML composite control:

 <a name="loioc6e0122ca9874844a214018bec02e74a__table_csk_5pg_c1b"/>Property Binding

|Binding

|Sample

|Use

|Comments

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>---------</th>
			<th>--------</th>
			<th>-----</th>
			<th>----------</th>
		</tr>
	</thead>
	<tbody>

			<td> `text="{$this>/text}"` 
			</td>
			<td>Maps a property of the inner control interface to a property of your XML composite control interface.
			</td>
		</tr>
		<tr>
			<td>Expression binding
			</td>
			<td> `text="{=${$this>/text} + 'additionalText'}"` 
			</td>
			<td>Adds 'additionalText' to the value of the property of the inner control.
			</td>
			<td>One-way binding only
			</td>
		</tr>
		<tr>
			<td>Composite binding
			</td>
			<td> `text="{$this>/text} - {$this>/text1}"` 
			</td>
			<td>Concatenation of the two properties `text` and `text1` 
			</td>
			<td>One-way binding only
			</td>
		</tr>
	</tbody>
</table>

