<!-- loio9373793b290d429ba1bc6aea1ce5482f -->

| loio |
| -----|
| 9373793b290d429ba1bc6aea1ce5482f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9373793b290d429ba1bc6aea1ce5482f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9373793b290d429ba1bc6aea1ce5482f)</div>

## Step 8: Binding Paths: Accessing Properties in Hierarchically Structured Models

In step 6 , we stated that the fields in a resource model are arranged in a flat structure; in other words, there can be no hierarchy of properties; however, this is true only for resource models. The properties within JSON and OData models almost always are arranged in a hierarchical structure. Therefore, we should take a look at how to reference fields in a hierarchically structured model object.

***

### Preview

   
  
<a name="loio9373793b290d429ba1bc6aea1ce5482f__fig_r1j_pst_mr"/>Second panel with additional data

 ![](loio12705f5341f24febb905a50d37bf32db_HiRes.png "Second panel with additional data") 

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 8](https://openui5.hana.ondemand.com/explored.html#/sample/sap.ui.core.tutorial.databinding.08/preview).

***

### webapp/index.js

``` js
sap.ui.require([
	"sap/ui/model/json/JSONModel",
	"sap/ui/core/mvc/XMLView",
	"sap/ui/model/resource/ResourceModel"
], function (JSONModel, XMLView, ResourceModel) {
	"use strict";

	// Attach an anonymous function to the SAPUI5 'init' event
	sap.ui.getCore().attachInit(function () {
		var oModel = new JSONModel({
			firstName: "Harry",
			lastName: "Hawk",
			enabled: true*HIGHLIGHT START*,
			address: {
				street: "Dietmar-Hopp-Allee 16",
				city: "Walldorf",
				zip: "69190",
				country: "Germany"
			}
*HIGHLIGHT END*
		});

		// Assign the model object to the SAPUI5 core
		sap.ui.getCore().setModel(oModel);

		var oResourceModel = new ResourceModel({
			bundleName: "sap.ui.demo.db.i18n.i18n",
			supportedLocales: ["", "de"],
			fallbackLocale: ""
		});

		sap.ui.getCore().setModel(oResourceModel, "i18n");

		// Display the XML view called "App"
		new XMLView({
			viewName: "sap.ui.demo.db.view.App"
		}).placeAt("content");
	});
});

```

The JSON model object now contains an additional sub-object called `address`. Within this object are four properties: `street`, `city`, `zip`, and `country`.

***

### webapp/view/App.view.xml

``` xml
<mvc:View
	xmlns="sap.m"
	*HIGHLIGHT START*xmlns:form="sap.ui.layout.form"*HIGHLIGHT END*
	xmlns:l="sap.ui.layout"
	xmlns:mvc="sap.ui.core.mvc">
	<Panel headerText="{i18n>panel*HIGHLIGHT START*1*HIGHLIGHT END*HeaderText}" class="sapUiResponsiveMargin" width="auto">
		<form:SimpleForm editable="true" layout="ColumnLayout">
			<Label text="{i18n>firstName}"/>
			<Input value="{/firstName}" valueLiveUpdate="true" width="200px" enabled="{/enabled}"/>
			<Label text="{i18n>lastName}"/>
			<Input value="{/lastName}" valueLiveUpdate="true" width="200px" enabled="{/enabled}"/>
			<Label text="{i18n>enabled}"/>
			<CheckBox selected="{/enabled}"/>
		</form:SimpleForm>
	</Panel>
	*HIGHLIGHT START*<Panel headerText="{i18n>panel2HeaderText}" class="sapUiResponsiveMargin" width="auto">
		<content>
			<l:VerticalLayout>
				<Label labelFor="address" text="{i18n>address}:"/>
				<FormattedText class="sapUiSmallMarginBottom"
					htmlText="{/address/street}&lt;br&gt;{/address/zip} {/address/city}&lt;br&gt;{/address/country}"
					id="address" 
					width="200px"/>
			</l:VerticalLayout>
		</content>
	</Panel>*HIGHLIGHT END*
</mvc:View>
```

We add a new panel to the XML view with a new `Label` and `Text` pair of elements.

The text property of the `Label` element is bound to the i18n resource bundle field `address`.

The text property of the `Text` element is bound to three i18n properties: `/address/street`, `/address/zip`, `/address/city`, and `/address/country`. The resulting address format is achieved by separating each one of these model property references with a hard-coded newline character while `zip` and `city` are separated by a space.

***

### webapp/i18n/i18n.properties

``` prefs
# Field labels
firstName=First Name
lastName=Last Name
enabled=Enabled
*HIGHLIGHT START*address=Address
*HIGHLIGHT END*

# Screen titles
panel*HIGHLIGHT START*1*HIGHLIGHT END*HeaderText=Data Binding Basics 
*HIGHLIGHT START*panel2HeaderText=Address Details*HIGHLIGHT END*
```

***

### webapp/i18n/i18n\_de.properties

``` prefs
# Field labels
firstName=Vorname
lastName=Nachname
enabled=Aktiviert
address=Adresse


# Screen titles
panel*HIGHLIGHT START*1*HIGHLIGHT END*HeaderText=Data Binding Grundlagen
*HIGHLIGHT START*panel2HeaderText=Adressdetails*HIGHLIGHT END*
```

> ### Note:  
> The resource bundle files now contain new properties for the **Address** and a new panel header text. Both panel properties have been numbered.
> 
> In the XML view, inside the curly brackets for the binding path of the `Text` element, notice that the first character is a forward slash. This is required for binding paths that make absolute references to properties in JSON and OData models, but must not be used for resource models. After the first forward slash character, the binding path syntax uses the object names and the property name separated by forward slash characters \(`{/address/street}`\).
> 
> As has been mentioned previously, all binding path names are case-sensitive.

**Parent topic:** [Data Binding](Data_Binding_e531093.md "In this tutorial, we will explain the concepts of data binding in OpenUI5.")

**Next:** [Step 7: \(Optional\) Resource Bundles and Multiple Languages](Step_7_Optional_Resource_Bundles_and_Multiple_Languages_4e593b4.md "The reason we have resource bundles is to allow an app to run in multiple languages without the need to change any code. To demonstrate this feature, we will create a German version of the app – in fact all we need to do is create a German version of the resource bundle file. In our code, the German locale needs to be activated for the ResourceModel.")

**Previous:** [Step 9: Formatting Values](Step_9_Formatting_Values_6fdf0ac.md "We also want to provide our users a way of contacting Harry Hawk. Therefore we will add a link that sends an e-mail to Harry. To achieve that we will convert our data in the model to match the sap.m.URLHelper.normalizeEmail API. As soon as the user changes the name, the e-mail will also change. We will need a custom formatter function for this.")

**Related Information**  


[JSON Model](JSON_Model_96804e3.md#loio96804e3315ff440aa0a50fd290805116 "The JSON model can be used to bind controls to JavaScript object data, which is usually serialized in the JSON format.")

