<!-- loio50079678e0cc4c8298f764580fc223d3 -->

| loio |
| -----|
| 50079678e0cc4c8298f764580fc223d3 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/50079678e0cc4c8298f764580fc223d3) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/50079678e0cc4c8298f764580fc223d3)</div>

## Troubleshooting Common RTL Issues

The following table outlines some common issues that occur when implementing right-to-left \(RTL\) support for OpenUI5 controls and their solutions.

***

RTL Issues and Solutions<a name="loio50079678e0cc4c8298f764580fc223d3__table_d53_pj3_ns"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Issue</th>
			<th>Solution</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>For mirrored images, the mirroring does not show a correct RTL image, or animations are removed from GIF images when mirroring.</td>
			<td>Create the correct RTL version of the image manually and put it into the `img-RTL` folder, using the same name and path. In most cases, this means just copying the original LTR image. In rare cases, an image may have some content that needs mirroring and other content that does not. In this case, the graphic needs to be adapted manually.</td>
		</tr>
		<tr>
			<td>Image mirroring is only supported for GIF, PNG and JPEG images. Other types like .cur, .ico and .svg are not supported.</td>
			<td>Create the correct RTL version of the image manually and put it into the `img-RTL` folder, using the same name and path.</td>
		</tr>
		<tr>
			<td>The background position in CSS is correctly mirrored, but the LTR version of the control works fine with the default background position: `left top`. This is not explicitly written in the CSS and is therefore not mirrored.</td>
			<td>Specify the background position explicitly to display the RTL version correctly.</td>
		</tr>
		<tr>
			<td>Text is incorrectly aligned because the CSS `text-align` property is not converted.</td>
			<td> Do not use `text-align:left` if you want the text to change sides in RTL mode, but use `text-align:start` instead. `start` and `end` are handled automatically by the browser. Only use `right` and `left` if you want the text to stay on the same side in RTL mode.
 > Note:
 > `start` and `end` are not supported by Internet Explorer 9, 10 and 11. These browser versions use the default alignment, which is the same as `begin`. You need to add specific rules for the LTR and RTL case that specify `right` and `left` respectively. For example, for alignment to `end`:
 > ```
 > 												```
 > html[data-sap-ui-browser^=ie] .sapUiTableEndAlign{text-align: right;} 
 >  html[dir=rtl][data-sap-ui-browser^=ie] .sapUiTableEndAlign{text-align: left;}
 > ```
 > ```
			</td>
		</tr>
		<tr>
			<td>If style is set using JavaScript \(for example, in the renderer or behavior of a control\), the conversion does not take place and the result looks incorrect.</td>
			<td>Consider the RTL mode in your calculations, or when possible, use the CSS file instead \(which is automatically handled\) and write a CSS class.</td>
		</tr>
		<tr>
			<td>The alignment of popups with the parent element is unaffected by RTL mode and is therefore often incorrect.</td>
			<td> `sap.ui.core.Popup.Dock` has been extended by adding `Begin*` and"`End*`. Those will change sides in RTL mode. Use these instead of `Left*` and `Right*` if the popup alignment should change sides.</td>
		</tr>
		<tr>
			<td>When JavaScript calculations are used to determine positions or dimensions, existing implementations might imply LTR mode and result in an incorrect layout.</td>
			<td>Make these algorithms RTL-compliant by checking the SAPUI5 RTL configuration.</td>
		</tr>
		<tr>
			<td>Some text elements inside the control may look incorrect, for instance parentheses may be shown in the wrong position, pointing to the wrong direction. For example **\(very\) short text** might be rendered as **very\) short text\)** in RTL mode.</td>
			<td>This is a result of the browser's `bidi` algorithm considering the directionality of the characters used. As soon as there is LTR text in the control, the parentheses will be fine again. For controls that have mixed contents, see [API Properties for Right-to-Left Support in Text-Displaying Controls](API_Properties_for_Right-to-Left_Support_in_Text-Displaying_Controls_7e7cd0a.md) </td>
		</tr>
		<tr>
			<td>When images are added as `CSS generated content` \(with `:before` or `:after` selector\), Internet Explorer 9 and 10 automatically mirror the image. Double-mirroring results in an incorrectly mirrored image.</td>
			<td>The LTR image needs to be provided without mirroring \(use `html[dir=rtl]` and the respective browser selector\).</td>
		</tr>
		<tr>
			<td>When a control has a `textAlign` property \(or something similar\), you need to use additional API properties to ensure the correct alignment of the text according to the directionality.</td>
			<td>Use the [API Properties for Right-to-Left Support in Text-Displaying Controls](API_Properties_for_Right-to-Left_Support_in_Text-Displaying_Controls_7e7cd0a.md) . Additionally, the static helper method `sap.ui.core.Renderer.getTextAlign(oTextAlign, oTextDirection)` is available. This method calculates the effective value of the CSS `text-align` property considering the property setting and the current or given RTL mode.</td>
		</tr>
	</tbody>
</table>

