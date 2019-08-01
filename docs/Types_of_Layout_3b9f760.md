<!-- loio3b9f760da5b64adf8db7f95247879086 -->

| loio |
| -----|
| 3b9f760da5b64adf8db7f95247879086 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3b9f760da5b64adf8db7f95247879086) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3b9f760da5b64adf8db7f95247879086)</div>

## Types of Layout

Overview of the possible layouts for an `sap.f.FlexibleColumnLayout`, as defined in the `sap.f.LayoutType` enumeration.

Although the `FlexibleColumnLayout` can display 2 or 3 pages at one time, they can never have equal width \(50%/50% or 33%/33%/33%\). One of the pages is always larger \(expanded\) or even takes up the full width of the control \(fullscreen\). This is intentional because users should have a clear indication of what to focus their attention on at any given moment, for example, a list of items, one particular item, one item’s details.

Transitioning from a one-column layout to any two-column layout, and then to any three-column layout is seen by the user as new columns appearing/disappearing on desktop/tablet or the next column replacing the previous one - on phone \(small screen size\). The app does not need to provide separate logic for the different screen sizes, but only change the layout based on the user input and desired behavior. The `FlexibleColumnLayout` will internally manage column visibility and resizing. If at any time, the browser size changes, this will be reflected by the control automatically.

There are 9 allowed variations of width and visibility for the 3 columns. They are represented with the values of the `layout` property, which is of type `sap.f.LayoutType`.

The table below shows how each of the 9 layout types affects the column visibility and width, based on the control size:

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Layout Types</th>
			<th>Desktop / Tablet / Phone</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> **`OneColumn`** This is the default layout type for a `FlexibleColumnLayout`. Only the `Begin` column is displayed, no matter the control size. Use to show the first logical information level \(master page\) only.</td>
			<td>  

![](loiod7914916d4674c3481d67658eae465a1_LowRes.png) 
			</td>
		</tr>
		<tr>
			<td> **`TwoColumnsBeginExpanded`** Use this layout type to display two logical levels of information \(master and detail pages, master being expanded\) on desktop/tablet, or the second logical level of information only \(detail page\) on phone. On desktop/tablet the transition from `OneColumn` to `TwoColumnsBeginExpanded` is seen by the user as the `Begin` column shrinking and `Mid` column opening, while on phone it's seen as the `Mid` column replacing the `Begin` column.</td>
			<td>  

![](loio9a603876f70a47aeabf08c030a5e9daa_LowRes.png) 
			</td>
		</tr>
		<tr>
			<td> **`TwoColumnsMidExpanded`** Similar to `TwoColumnsBeginExpanded`, but this time the `Mid` column is the wider one.</td>
			<td>  

![](loioc0d69368378f4d0dac00d62801fd64e5_LowRes.png) 
			</td>
		</tr>
		<tr>
			<td> **`MidColumnFullScreen`** Use this layout to display the second logical level of information \(detail page\) only. The `Mid` column takes up the whole available control width for all control sizes.

 > Note:
 > On small screen sizes, the layouts `TwoColumnsBeginExpanded`, `TwoColumnsMidExpanded` and `MidColumnFullScreen` all lead to the same result for the user – the `Mid` column taking up the whole control width. However, if the user resizes the browser and makes space, the control will automatically apply the rules of the current layout for the new width.
			</td>
			<td>  

![](loioa01d72d41f014168b9438d12e650f4ad_LowRes.png) 
			</td>
		</tr>
		<tr>
			<td> **`ThreeColumnsMidExpanded`** Use this layout to display up to three logical levels of information side by side \(master, detail, and detail-detail pages\), when the user should focus primarily on the content of the `Mid` column \(as it is wider than the other two\). On desktop, all three columns will be displayed, on tablet – the `Mid` and `End` columns only \(with a layout arrow to access the `Begin` column\), and on phone – the `End` column only.</td>
			<td>  

![](loiod1f89e8ad3f9409aa14e8e98a07f8bb4_LowRes.png) 
			</td>
		</tr>
		<tr>
			<td> **`ThreeColumnsEndExpanded`** Similar to `ThreeColumnsMidExpanded`, but this time the `End` column is expanded, and this is where the user is supposed to focus their attention.</td>
			<td>  

![](loio2cef71c4c5e64dea975c6b44196d2ca7_LowRes.png) 
			</td>
		</tr>
		<tr>
			<td> **`ThreeColumnsMidExpandedEndHidden`** Use this layout to show the `Begin` and `Mid` columns only \(`Mid` being expanded\), while the `End` column is hidden but accessible with a layout arrow. The difference between this layout and the `TwoColumnsMidExpanded` layout is that for `TwoColumnsMidExpanded` the user cannot access the `End` column at all, as only two logical levels of information are offered \(the third may not be loaded yet\), while for `ThreeColumnsMidExpandedEndHidden` the `End` column is not empty, but just not currently displayed. Its content is loaded and easily accessible \(most commonly already seen by the user, and now hidden so more space can be freed for the other columns\).</td>
			<td>  

![](loio21a31d26b82d4c8ea2d17fe28a792026_LowRes.png) 
			</td>
		</tr>
		<tr>
			<td> **`ThreeColumnsBeginExpandedEndHidden`** Similar to `ThreeColumnsMidExpandedEndHidden`, but this time the `Begin` column is expanded. A layout arrow is provided to shrink the `Begin` column, thus transitioning the layout to `ThreeColumnsMidExpandedEndHidden`.</td>
			<td>  

![](loioe98b27beff5145b79cd3a7a7392f9167_LowRes.png) 
			</td>
		</tr>
		<tr>
			<td> **`EndColumnFullScreen`** Use this layout to display the third logical level of information \(detail-detail page\) only. The `End` column takes up the whole available control width for all screen sizes.

 > Note:
 > On small screen sizes all three-column layouts and `EndColumnFullScreen` lead to the same result for the user – the `End` column taking up the whole control width. However, if the user resizes the browser and makes space, the control will automatically apply the rules of the current layout for the new width.
			</td>
			<td>  

![](loio1129d11a2aa3466c937db16d8e9c149a_LowRes.png) 
			</td>
		</tr>
	</tbody>
</table>

For each value of the layout property, the `FlexibleColumnLayout` displays a different combination of columns, based on the available control width \(or screen width, if the control takes up the whole screen\).

|Control size|Columns|
|------------|-------|
|Up to 960px \(Phone\)|1 column max|
|960px – 1280px \(Tablet\)|2 column max|
|1280px and above \(Desktop\)|3 column max|

**Related information**  


[API Reference: `sap.f.LayoutType`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.f.LayoutType.html)

