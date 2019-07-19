<!-- loio9d87f925dfbb4e99b9e2963693aa00ef -->

| loio |
| -----|
| 9d87f925dfbb4e99b9e2963693aa00ef |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9d87f925dfbb4e99b9e2963693aa00ef) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9d87f925dfbb4e99b9e2963693aa00ef)</div>

## CSS Styling Issues

This section lists some of the most important rules relating to CSS styling in OpenUI5.

OpenUI5 controls are styled with CSS, and as applications can provide their own CSS, they can adapt the styling. However, the deeper such adaptations are, the more likely is it that they break with future OpenUI5 updates or with other libraries and apps getting involved. If you follow the rules listed below, you will reduce the risk of this happening.

***

<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__1"/>

### Don't override control class styling directly

OpenUI5 does not guarantee the stability of style class names across versions. If the naming of style classes is changed in future versions, styling rules will no longer be applied to targeted elements. In addition, overriding control class styles directly might lead to style clashes when applications are run in shared runtime environments \(like SAP Fiori launchpad\).

Add your own namespaced classes instead.

Examples<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__table_ehh_rkk_jq"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Bad Example</th>
			<th>Good Example</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> 

```

.sapMInputBaseError {
	font-weight: bold;
}
```
			</td>
			<td>Add a custom CSS class to the control in those situations where you want additional styling: `oButton.addStyleClass("poaAppError");`Then provide the style for this class:

```

.poaAppError {
	font-weight: bold;
}

```
			</td>
		</tr>
	</tbody>
</table>

***

<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__2"/>

### Don't style DOM element names directly

Styling DOM elements directly will lead to unpredictable results, as OpenUI5 does not guarantee the stability of the inner-control DOM-tree over time. In addition, this might lead to styling clashes when applications run in shared runtime environments \(like SAP Fiori launchpad\) or when custom HTML is added. It is better to limit styling changes to specifically used CSS classes.

Examples<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__table_mdl_qcq_jq"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Bad Example</th>
			<th>Good Example</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> ``` html
div {
	width: 120px;
}
```
			</td>
			<td> 

```

.myStyleClass {
	width: 120px;
}
```
			</td>
		</tr>
	</tbody>
</table>

***

<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__3"/>

### Don't use generated IDs in CSS selectors

OpenUI5 applications can create dynamic IDs for elements. Do not use these IDs as selectors in custom CSS as they can change over time. It is better to add and use CSS classes instead.

Examples<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__table_lzk_5dq_jq"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Bad Example</th>
			<th>Good Example</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> 

```

#__view1__button0 {
	font-weight: bold;
}
```
			</td>
			<td>Add a style class as described above and then define the following: 

```

.myEmphasizedButton {
	font-weight: bold;
}
```
			</td>
		</tr>
	</tbody>
</table>

***

<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__4"/>

### Don't create selectors that are not namespaced

Custom selectors and CSS classes that are not namespaced might lead to style clashes in shared runtime environments like SAP Fiori launchpad, or when other JavaScript libraries are included that might use the same CSS class names.

Examples<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__table_j2n_l2q_jq"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Bad Example</th>
			<th>Good Example</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> 

```

.title {
	font-weight: bold;
}
```
			</td>
			<td> 

```

.poaAppTitle {
	font-weight: bold;
}
```
			</td>
		</tr>
	</tbody>
</table>

***

<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__5"/>

### Don't use hard-coded colors, font sizes and images if the app should be themable

Themability of applications relies on LESS calculations within the OpenUI5 theme CSS. Hard-coding colors, fonts and images in applications and custom controls means that these colors are not modified by theming, which leads to design issues or accessibility issues \(for example, in the High Contrast Black \(HCB\) theme\). You can use special CSS classes instead that are supplied by these LESS calculations.

Examples<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__table_twd_s2q_jq"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Bad Example</th>
			<th>Good Example</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> 

```

.myCustomHTML {
	color: #FFF;
	background-color: blue;
}
```
			</td>
			<td>Add the CSS classes `sapThemeTextInverted` and `sapThemeHighlight-asBackgroundColor` to your custom HTML element.</td>
	</tbody>
</table>

See also: [CSS Classes for Theme Parameters](CSS_Classes_for_Theme_Parameters_ea08f53.md).

***

<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__6"/>

### Don't use theming parameters for attributes they were not intended for

OpenUI5 applications come with a built-in set of parameters which are used for theme-dependent styling, mainly for colors. They are accessible using the `sap.ui.core.theming.Parameters.get()` API \(and for library builds using the OpenUI5 build mechanism, also in the \*.less files in control libraries\). These theme parameters have descriptive names, meaning that by looking at a parameter name, you can see the usage it has been defined for.

To ensure that you do not use combinations of theme colors which may clash after future theme changes, do not use background colors for fonts or vice versa, for example, and do not use border colors for anything else but borders.

Examples<a name="loio9d87f925dfbb4e99b9e2963693aa00ef__table_qsf_kfq_jq"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Bad Example</th>
			<th>Good Example</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> ``` js
var sColor = sap.ui.core.theming.Parameters.get("sapUiButtonBorderColor");
$(oSomeDomElement).css("background-color", sColor);
```
			</td>
			<td> ``` js
var sColor = sap.ui.core.theming.Parameters.get("sapUiButtonBorderColor");
$(oSomeDomElement).css("border-color", sColor);
```
			</td>
		</tr>
	</tbody>
</table>

See also: [Namespace sap.ui.core.theming.Parameters](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.theming.Parameters.html).

