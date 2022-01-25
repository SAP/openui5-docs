<!-- loiod1ffe611194b4c7891772b0cce84648e -->

| loio |
| -----|
| d1ffe611194b4c7891772b0cce84648e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/d1ffe611194b4c7891772b0cce84648e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/d1ffe611194b4c7891772b0cce84648e)</div>

## Step 5: Using Object Page Layout as a Detail Page

In this step, we add `sap.uxap.ObjectPageLayout` to the detail page to display more information about each product.

The `ObjectPageLayout` control provides a layout that allows apps to easily display information related to a business object.

As of version 1.52, the control can have the same dynamic header that is used in the `sap.f.DynamicPage`. This ensures the availability of the SAP Fiori features, such as, having breadcrumbs navigation, navigation actions, and expanding/collapsing the header by tapping/clicking the title area or by selecting the available arrow buttons. For more information, see [Object Page Headers](Object_Page_Headers_d2ef009.md).

Compared to `sap.f.DynamicPage`, the `sap.uxap.ObjectPageLayout` can provide a more structured page content using an optional anchor bar and block content wrapped in sections and subsections that structure the information. For more information, see [Object Page Layout](Object_Page_Layout_2e61ab6.md).

***

<a name="loiod1ffe611194b4c7891772b0cce84648e__section_ed2_4dd_lbb"/>

### Preview

   
  
<a name="loiod1ffe611194b4c7891772b0cce84648e__fig_r1j_pst_mr"/>`ObjectPageLayout` with dynamic header for the detail page

 ![](loioda38488f47f941a0b53509d22ef9027c_HiRes.gif "ObjectPageLayout with dynamic header for the detail
					page") 

***

<a name="loiod1ffe611194b4c7891772b0cce84648e__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [Flexible Column Layout App - Step 5](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.05/preview).

***

<a name="loiod1ffe611194b4c7891772b0cce84648e__section_qhh_ylj_l4b"/>

### webapp/manifest.json \[MODIFY\]

``` json
{
	"_version": "1.12.0",
	"sap.app": {
		"id": "sap.ui.demo.fiori2",
		"type": "application",
		"applicationVersion": {
			"version": "1.0.0"
		}
	},
	"sap.ui5": {
		"rootView": {
			"viewName": "sap.ui.demo.fiori2.view.App",
			"type": "XML",
			"async": true,
			"id": "fcl"
		},
		"dependencies": {
			"minUI5Version": "1.60.0",
			"libs": {
				"sap.ui.core": {},
				"sap.m": {},
				"sap.f": {}*HIGHLIGHT START*,
				"sap.uxap": {}*HIGHLIGHT END*
			}
		},
		"config": {
			"fullWidth": true
		}
	}
}
```

First, we add the related libraries that we will need to the dependencies in the `manifest.json`.

***

<a name="loiod1ffe611194b4c7891772b0cce84648e__section_s1m_xlj_l4b"/>

### webapp/view/Detail.view.xml \[MODIFY\]

``` xml
<mvc:View
*HIGHLIGHT START*	xmlns="sap.uxap"
	xmlns:m="sap.m"
	xmlns:f="sap.f"
	xmlns:form="sap.ui.layout.form"*HIGHLIGHT END*
	xmlns:mvc="sap.ui.core.mvc">
*HIGHLIGHT START*	<ObjectPageLayout
		id="ObjectPageLayout"
		showTitleInHeaderContent="true"
		alwaysShowContentHeader="false"
		preserveHeaderStateOnScroll="false"
		headerContentPinnable="true"
		isChildPage="true"
		upperCaseAnchorBar="false">
	</ObjectPageLayout>*HIGHLIGHT END*
</mvc:View>
```

We add an instance of the `sap.uxap.ObjectPageLayout` control.

***

<a name="loiod1ffe611194b4c7891772b0cce84648e__section_hqw_vlj_l4b"/>

### webapp/view/Detail.view.xml \[MODIFY\]

``` xml
<mvc:View
	xmlns="sap.uxap"
	xmlns:m="sap.m"
	xmlns:f="sap.f"
	xmlns:form="sap.ui.layout.form"
	xmlns:mvc="sap.ui.core.mvc">
	<ObjectPageLayout
		id="ObjectPageLayout"
		showTitleInHeaderContent="true"
		alwaysShowContentHeader="false"
		preserveHeaderStateOnScroll="false"
		headerContentPinnable="true"
		isChildPage="true"
		upperCaseAnchorBar="false">
*HIGHLIGHT START*		<headerTitle>
			<ObjectPageDynamicHeaderTitle>
				<actions>
					<m:ToggleButton
						text="Edit"
						type="Emphasized"/>
					<m:Button
						text="Delete"
						type="Transparent"/>
					<m:Button
						text="Copy"
						type="Transparent"/>
					<m:Button
						icon="sap-icon://action"
						type="Transparent"/>
				</actions>
			</ObjectPageDynamicHeaderTitle>
		</headerTitle>*HIGHLIGHT END*

	</ObjectPageLayout>
</mvc:View>
```

We add the recommended dynamic header with an instance of the `ObjectPageDynamicHeaderTitle` in the `headerTitle` aggregation of the `ObjectPageLayout`. For more information, see [Object Page Dynamic Header](Object_Page_Dynamic_Header_6e340c1.md) and [Object Page Headers Comparison](Object_Page_Headers_Comparison_9c9d94f.md).

***

<a name="loiod1ffe611194b4c7891772b0cce84648e__section_rhj_slj_l4b"/>

### webapp/view/Detail.view.xml \[MODIFY\]

``` xml
		...
		<headerTitle>
			<ObjectPageDynamicHeaderTitle>
				<actions>
					<m:ToggleButton
						text="Edit"
						type="Emphasized"/>
					<m:Button
						text="Delete"
						type="Transparent"/>
					<m:Button
						text="Copy"
						type="Transparent"/>
					<m:Button
						icon="sap-icon://action"
						type="Transparent"/>
				</actions>
			</ObjectPageDynamicHeaderTitle>
		</headerTitle>

*HIGHLIGHT START*		<headerContent>
			<m:FlexBox wrap="Wrap" fitContainer="true" alignItems="Stretch">
				<f:Avatar
					displaySize="L"
					displayShape="Square"
					class="sapUiTinyMarginEnd">
				</f:Avatar>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Main Category"/>
				</m:VBox>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Subcategory"/>
				</m:VBox>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Price"/>
				</m:VBox>
			</m:FlexBox>
		</headerContent>*HIGHLIGHT END*

	</ObjectPageLayout>
</mvc:View>
```

We add content in the `headerContent` aggregation. We're using `sap.f.Avatar` as the recommended SAP Fiori control for displaying images.

***

<a name="loiod1ffe611194b4c7891772b0cce84648e__section_yhv_qlj_l4b"/>

### webapp/view/Detail.view.xml \[MODIFY\]

``` xml
		...
		<headerContent>
			<m:FlexBox wrap="Wrap" fitContainer="true" alignItems="Stretch">
				<f:Avatar
					displaySize="L"
					displayShape="Square"
					class="sapUiTinyMarginEnd">
				</f:Avatar>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Main Category"/>
				</m:VBox>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Subcategory"/>
				</m:VBox>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Price"/>
				</m:VBox>
			</m:FlexBox>
		</headerContent>

*HIGHLIGHT START*		<sections>
			<ObjectPageSection title="General Information">
				<subSections>
					<ObjectPageSubSection>
						<blocks>
							<form:SimpleForm
								maxContainerCols="2"
								editable="false"
								layout="ResponsiveGridLayout"
								labelSpanL="12"
								labelSpanM="12"
								emptySpanL="0"
								emptySpanM="0"
								columnsL="1"
								columnsM="1">
								<form:content>
									<m:Label text="Product ID"/>
									<m:Label text="Description"/>
									<m:Label text="Supplier"/>
								</form:content>
							</form:SimpleForm>
						</blocks>
					</ObjectPageSubSection>
				</subSections>
			</ObjectPageSection>

			<ObjectPageSection title="Suppliers">
				<subSections>
					<ObjectPageSubSection>
						<blocks>
							<m:Table
								id="suppliersTable"
								items="{path : 'products>/ProductCollectionStats/Filters/1/values'}">
								<m:columns>
									<m:Column/>
								</m:columns>
								<m:items>
									<m:ColumnListItem type="Navigation">
										<m:cells>
											<m:ObjectIdentifier text="{products>text}"/>
										</m:cells>
									</m:ColumnListItem>
								</m:items>
							</m:Table>
						</blocks>
					</ObjectPageSubSection>
				</subSections>
			</ObjectPageSection>
		</sections>*HIGHLIGHT END*
	</ObjectPageLayout>
</mvc:View>
```

Finally, we add page content in two separate sections with blocks. For more information, see [Object Page Blocks](Object_Page_Blocks_4527729.md).

**Parent topic:** [Flexible Column Layout App](Flexible_Column_Layout_App_c4de2df.md "In this tutorial, we showcase how to structure your OpenUI5 app using the layout patterns that comply with the SAP Fiori design guidelines.")

**Next:** [Step 4: Adding a Detail Page](Step_4_Adding_a_Detail_Page_4e4315c.md "In this step, we add an empty detail page.")

**Previous:** [Step 6: Adding a Floating Footer](Step_6_Adding_a_Floating_Footer_555ed73.md "In this step, we add a floating footer to the detail page.")

