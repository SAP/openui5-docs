<!-- loioe5ee491f69224f038a0c147480dbd436 -->

| loio |
| -----|
| e5ee491f69224f038a0c147480dbd436 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e5ee491f69224f038a0c147480dbd436) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e5ee491f69224f038a0c147480dbd436)</div>

## Step 8: Enhancing the Detail Page

With routing implemented, the model of the detail page is updated for each product. In this step, we enhance the detail page to show information specific for the selected product.

***

<a name="loioe5ee491f69224f038a0c147480dbd436__section_yfh_d31_12b"/>

### Preview

   
  
Enhanced detail page displaying information specific to the selected product<a name="loioe5ee491f69224f038a0c147480dbd436__fig_zfh_d31_12b"/>

 ![](loiob687506e7e55437193741a31ff739b7b_HiRes.gif "Enhanced detail page displaying information specific to the selected
					product") 

***

<a name="loioe5ee491f69224f038a0c147480dbd436__section_fd2_4dd_lbb"/>

### Coding

You can view and download all files at [SAP Fiori 2.0 App - Step 8](https://openui5.hana.ondemand.com/#/sample/sap.f.tutorial.fiori2.08/preview).

``` xml
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
*HIGHLIGHT START*				<expandedHeading>
					<m:Title text="{products>Name}" wrapping="true" class="sapUiSmallMarginEnd"/>
				</expandedHeading>

				<snappedHeading>
					<m:FlexBox wrap="Wrap" fitContainer="true" alignItems="Center">
						<m:FlexBox wrap="NoWrap" fitContainer="true" alignItems="Center" class="sapUiTinyMarginEnd">
							<f:Avatar
								src="https://openui5.hana.ondemand.com/{products>ProductPicUrl}"
								displaySize="S"
								displayShape="Square"
								class="sapUiTinyMarginEnd"/>
							<m:Title text="{products>Name}" wrapping="true"/>
						</m:FlexBox>
					</m:FlexBox>
				</snappedHeading>*HIGHLIGHT END*

				<actions>
				...
```

Using the `expandedHeading` and `snappedHeading` aggregations, we specify different content to be displayed in the title area depending on whether the header is expanded or collapsed.

``` xml
		...
		<headerContent>
			<m:FlexBox wrap="Wrap" fitContainer="true" alignItems="Stretch">
				<f:Avatar
*HIGHLIGHT START*					src="https://openui5.hana.ondemand.com/{products>ProductPicUrl}"*HIGHLIGHT END*
					displaySize="L"
					displayShape="Square"
					class="sapUiTinyMarginEnd">
				</f:Avatar>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Main Category"/>
*HIGHLIGHT START*					<m:Text text="{products>MainCategory}"/>*HIGHLIGHT END*
				</m:VBox>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Subcategory"/>
*HIGHLIGHT START*					<m:Text text="{products>Category}"/>*HIGHLIGHT END*
				</m:VBox>
				<m:VBox justifyContent="Center" class="sapUiSmallMarginEnd">
					<m:Label text="Price"/>
*HIGHLIGHT START*					<m:ObjectNumber number="{products>CurrencyCode} {products>Price}" emphasized="false"/>*HIGHLIGHT END*
				</m:VBox>
			</m:FlexBox>
		</headerContent>
		...
```

We adjust the `headerContent` so that the `sap.f.Avatar` displays the specific image of the selected product and the header displays the product's Main Category, Category and Price information, which is provided in the `products.json` we're using.

``` xml
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
*HIGHLIGHT START*									<m:Text text="{products>ProductId}"/>*HIGHLIGHT END*
									<m:Label text="Description"/>
*HIGHLIGHT START*									<m:Text text="{products>Description}"/>*HIGHLIGHT END*
									<m:Label text="Supplier"/>
*HIGHLIGHT START*									<m:Text text="{products>SupplierName}"/>*HIGHLIGHT END*
								</form:content>
							</form:SimpleForm>
						</blocks>
					</ObjectPageSubSection>
				</subSections>
			</ObjectPageSection>
			...
```

We adjust the *General Information* section to display Product ID, Description and Supplier of the selected product.

