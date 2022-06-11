<!-- loioe5ee491f69224f038a0c147480dbd436 -->

| loio |
| -----|
| e5ee491f69224f038a0c147480dbd436 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/e5ee491f69224f038a0c147480dbd436) | [demo kit latest release](https://sdk.openui5.org/topic/e5ee491f69224f038a0c147480dbd436)</div>

## Step 8: Enhancing the Detail Page

With routing implemented, the model of the detail page is updated for each product. In this step, we enhance the detail page to show information specific for the selected product.

***

<a name="loioe5ee491f69224f038a0c147480dbd436__section_yfh_d31_12b"/>

### Preview

   
  
<a name="loioe5ee491f69224f038a0c147480dbd436__fig_zfh_d31_12b"/>Enhanced detail page displaying information specific to the selected product

 ![](images/loiob687506e7e55437193741a31ff739b7b_HiRes.gif "Enhanced detail page displaying information specific to the selected
					product") 

***

<a name="loioe5ee491f69224f038a0c147480dbd436__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [Flexible Column Layout App - Step 8](https://sdk.openui5.org/sample/sap.f.tutorial.fiori2.08/preview).

***

<a name="loioe5ee491f69224f038a0c147480dbd436__section_hml_l4j_l4b"/>

### webapp/view/Detail.view.xml \[MODIFY\]

```xml
<mvc:View
	controllerName="sap.ui.demo.fiori2.controller.Detail"
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
		<headerTitle>
			<ObjectPageDynamicHeaderTitle>
				<expandedHeading>
					<m:Title text="{products>Name}" wrapping="true" class="sapUiSmallMarginEnd"/>
				</expandedHeading>

				<snappedHeading>
					<m:FlexBox wrap="Wrap" fitContainer="true" alignItems="Center">
						<m:FlexBox wrap="NoWrap" fitContainer="true" alignItems="Center" class="sapUiTinyMarginEnd">
							<f:Avatar
								src="https://sdk.openui5.org/{products>ProductPicUrl}"
								displaySize="S"
								displayShape="Square"
								class="sapUiTinyMarginEnd"/>
							<m:Title text="{products>Name}" wrapping="true"/>
						</m:FlexBox>
					</m:FlexBox>
				</snappedHeading>

				<actions>
				...
```

Using the `expandedHeading` and `snappedHeading` aggregations, we specify different content to be displayed in the title area depending on whether the header is expanded or collapsed.

***

<a name="loioe5ee491f69224f038a0c147480dbd436__section_aym_k4j_l4b"/>

### webapp/view/Detail.view.xml \[MODIFY\]

```xml
		...
		<headerContent>
			<m:FlexBox wrap="Wrap" fitContainer="true" alignItems="Stretch">
				<f:Avatar
					src="https://sdk.openui5.org/{products>ProductPicUrl}"
					displaySize="L"
					displayShape="Square"
					class="sapUiTinyMarginEnd">
				</f:Avatar>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Main Category"/>
					<m:Text text="{products>MainCategory}"/>
				</m:VBox>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Subcategory"/>
					<m:Text text="{products>Category}"/>
				</m:VBox>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Price"/>
					<m:ObjectNumber number="{products>CurrencyCode} {products>Price}" emphasized="false"/>
				</m:VBox>
			</m:FlexBox>
		</headerContent>
		...
```

We adjust the `headerContent` so that the `sap.f.Avatar` displays the specific image of the selected product and the header displays the product's Main Category, Category and Price information, which is provided in the `products.json` we're using.

***

<a name="loioe5ee491f69224f038a0c147480dbd436__section_b2m_j4j_l4b"/>

### webapp/view/Detail.view.xml \[MODIFY\]

```xml
		...
		<sections>
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
									<m:Text text="{products>ProductId}"/>
									<m:Label text="Description"/>
									<m:Text text="{products>Description}"/>
									<m:Label text="Supplier"/>
									<m:Text text="{products>SupplierName}"/>
								</form:content>
							</form:SimpleForm>
						</blocks>
					</ObjectPageSubSection>
				</subSections>
			</ObjectPageSection>
			...
```

We adjust the *General Information* section to display Product ID, Description and Supplier of the selected product.

**Parent topic:** [Flexible Column Layout App](Flexible_Column_Layout_App_c4de2df.md "In this tutorial, we showcase how to structure your OpenUI5 app using the layout patterns that comply with the SAP Fiori design guidelines.")

**Next:** [Step 7: Routing](Step_7_Routing_7f65131.md "In this step, we utilize the sap.f.routing.Router.")

**Previous:** [Step 9: Adding a Detail-Detail Page](Step_9_Adding_a_Detail_Detail_Page_e4d21fd.md "In this step, we create a detail-detail page using sap.f.DynamicPage, which is opened by choosing a supplier from the detail page.")

