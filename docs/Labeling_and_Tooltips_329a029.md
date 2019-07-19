<!-- loio329a029f39e249a1bf89e3ffc006c8e1 -->

| loio |
| -----|
| 329a029f39e249a1bf89e3ffc006c8e1 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/329a029f39e249a1bf89e3ffc006c8e1) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/329a029f39e249a1bf89e3ffc006c8e1)</div>

## Labeling and Tooltips

The following guidelines help you properly label your controls in order to have good accessibility.

***

<a name="loio329a029f39e249a1bf89e3ffc006c8e1__section_ujj_dpb_t2b"/>

### General Considerations

Top 5 things to do for better screen reader support for labels

1.  Label all elements and element containers correctly and completely.

2.  Provide text alternatives for visual labels

    Use tooltips only in rare cases. They should not be used as a replacement for a label.

    Use the `alt` attribute for images

3.  Describe controls and give additional information as part of the UI

    Use `ariaDescribedBy` where needed.

4.  Identify regions correctly according to their purpose.

    Use containers with a correct meaning and Landmark roles.

5.  Provide accessible alternatives and describe how to use them \(for example in the documentation of the application\).


***

Rules and Guidelines for Labeling and Tooltips<a name="loio329a029f39e249a1bf89e3ffc006c8e1__table_vzj_4r3_5s"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Rules and Guidelines</th>
			<th>Examples/Clarification</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>Non-decorative `sap.m.Image`/`sap.ui.core.Icon` should provide a meaningful alternative description in the `alt` property.</td>
			<td>

 > Note:
 > ```
 > <Image id="image_not_decorative" src="IMAGE_PATH" alt="This is an image showing an elephant" decorative=false>
 > ```
			</td>
		</tr>
		<tr>
			<td>Interactive `sap.m.Image`/`sap.ui.core.Icon` \(that has a press handler\) should not be decorative.</td>
			<td>

 > Note:
 > ```
 > <Image src="IMAGE_PATH" alt="This is an image with a press handler" decorative=false press=onImagePress>
 > ```
			</td>
		</tr>
		<tr>
			<td>Icon-only `sap.m.Button` should have a tooltip.</td>
			<td>

 > Note:
 > ```
 > <Button icon="sap-icon://action" press="onPress" alt="An action button" ariaLabelledBy="actionButtonLabel"/>
 > ```
			</td>
		</tr>
		<tr>
			<td>Labels should **not** have a tooltip.</td>
			<td>This could lead to ambiguity.</td>
		</tr>
		<tr>
			<td>Input elements should have labels.</td>
			<td>Every input needs a label for its description and purpose. Even if the app doesn't include one, you can set one in `sap.ui.core.InvisibleText`. The placeholder text should not be used as a label.</td>
		</tr>
		<tr>
			<td>Tables should have titles</td>
			<td>Tables with hidden titles or in containers with titles \(for example,single tables in tab strip panels\) should be labeled with `sap.ui.core.InvisibleText` in combination with `arialabelledby`.</td>
		</tr>
		<tr>
			<td>Button that has a text, should **not** have a tooltip.</td>
			<td>

 > Note:
 > ```
 > <Button text="Default" press="onPress" />
 > ```
			</td>
		</tr>
		<tr>
			<td> `Aria-labelledby` and `aria-describedby` associations should point to existing DOM elements.</td>
			<td>

 > Note:
 > ```
 >  <Page title="Page">
 >   <content>   
 > <Button text="Home" ariaLabelledBy="invisibleId"/>   
 > <core:InvisibleText id="invisibleId" text="I am a hidden label"/>  
 > </content> 
 > </Page>
 > ```
			</td>
		</tr>
		<tr>
			<td>Labels should be connected with the labelled elements via `labelfor`.</td>
			<td>

 > Note:
 > ```
 > <Label text="Name" labelFor="I1"> 
 > <Input id="I1">
 > ```
			</td>
		</tr>
	</tbody>
</table>

> Note:
> If you want to enlarge the size of the standard tooltips, you need to change the system font size. Tooltips are rendered by the browser using native window API and thus their size cannot be influenced by the OpenUI5 framework.
> 
> 

