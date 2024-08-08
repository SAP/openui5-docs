<!-- loio9252ee4015f24fc49c71c295394d1b8d -->

| loio |
| -----|
| 9252ee4015f24fc49c71c295394d1b8d |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/9252ee4015f24fc49c71c295394d1b8d) | [demo kit latest release](https://sdk.openui5.org/topic/9252ee4015f24fc49c71c295394d1b8d)</div>

## Step 10: Property Formatting Using Data Types

OpenUI5 offers a set of simple data types, including `Boolean`, `Currency`, `Date` and `Float`. You can apply these data types to controls to ensure that the value displayed on the screen is formatted correctly. If the field is open for input, this also ensures that the user input meets the requirements of that data type. Let's add a new field called *Sales Amount* of type `Currency`.

***

### Preview

  
  
**An input field for a currency amount is added to the second panel**

![The graphic has an explanatory text](images/loiod15f8bc61efe47d9af2afdeea943cd9c_LowRes.png "An input field for a currency amount is added to the second panel")

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 10](https://sdk.openui5.org/entity/sap.ui.core.tutorial.databinding/sample/sap.ui.core.tutorial.databinding.10).

1.  Add two new JSON model properties, `salesAmount` and `currencyCode`, to the `data.json` file.

    **webapp/model/data.json**

    ```
    {
    	"firstName": "Harry",
    	"lastName": "Hawk",
    	"enabled": true,
    	"address": {
    		"street": "Dietmar-Hopp-Allee 16",
    		"city": "Walldorf",
    		"zip": "69190",
    		"country": "Germany"
    	},
    	"salesAmount": 12345.6789,
    	"currencyCode": "EUR"
    }
    ```

2.  Add the highlighted XML code to the `App.view.xml` file.

    **webapp/view/App.view.xml**

    ```xml
    ...
    	<Panel headerText="{i18n>panel1HeaderText}" class="sapUiResponsiveMargin" width="auto">
    		<form:SimpleForm editable="true" layout="ColumnLayout">
    			<Label text="{i18n>firstName}"/>
    			<Input value="{/firstName}" valueLiveUpdate="true" width="200px" enabled="{/enabled}"/>
    			<Label text="{i18n>lastName}"/>
    			<Input value="{/lastName}" valueLiveUpdate="true" width="200px" enabled="{/enabled}"/>
    			<Label text="{i18n>enabled}"/>
    			<CheckBox selected="{/enabled}"/>
    		</form:SimpleForm>
    	</Panel>
    	<Panel headerText="{i18n>panel2HeaderText}" class="sapUiResponsiveMargin" width="auto">
    		<content>
    			<l:HorizontalLayout>
    				<l:VerticalLayout>
    					<Label labelFor="address" text="{i18n>address}:"/>
    					<FormattedText class="sapUiSmallMarginBottom"
    						htmlText="{/address/street}&lt;br&gt;{/address/zip} {/address/city}&lt;br&gt;{/address/country}"
    						id="address" width="200px"/>
    					<Link href="{
    							parts: [
    								'/firstName',
    								'/lastName'
    							],
    							formatter: '.formatMail'
    						}"
    						text="{i18n>sendEmail}"/>
    				</l:VerticalLayout>
    				<l:VerticalLayout>
    					<Label labelFor="salesAmount" text="{i18n>salesAmount}:"/>
    					<Input description="{/currencyCode}" enabled="{/enabled}" id="salesAmount"
    						value="{
    							parts: [
    								{path: '/salesAmount'},
    								{path: '/currencyCode'}
    							],
    							type: 'sap.ui.model.type.Currency',
    							formatOptions: {showMeasure: false}
    						}" width="200px"/>
    				</l:VerticalLayout>
    			</l:HorizontalLayout>
    		</content>
    	</Panel>
    </mvc:View>
    ```

    We've created a new pair of `Label` and `Input` elements for the `salesAmount` model property. The description property of the `Input` element is bound to the `currencyCode` model property. The value property of the `Input` element is bound to the model properties `salesAmount` and `currencyCode`. The `{showMeasure: false}` parameter switches off the display of the currency symbol within the input field itself. This isn't necessary because the currency symbol is displayed using the `Input` element's description property.

3.  Add the highlighted texts to the `properties` files. Remember, you need to enter special characters \(non-Latin-1\) using Unicode escape characters.

    **webapp/i18n/i18n.properties**

    ```ini
    # Field labels
    firstName=Vorname
    lastName=Nachname
    enabled=Enabled
    address=Address
    salesAmount=Sales Amount
    ...
    ```

    **webapp/i18n/i18n\_de.properties**

    ```ini
    # Field labels
    firstName=Vorname
    lastName=Nachname
    enabled=Aktiviert
    address=Adresse
    salesAmount=Verk\u00e4ufe bis zum heutigen Datum
    ...
    ```


**Parent topic:**[Data Binding Tutorial](Data_Binding_Tutorial_e531093.md "In this tutorial, we explain the concepts of data binding in OpenUI5.")

**Next:**[Step 9: Formatting Values](Step_9_Formatting_Values_6fdf0ac.md "We'd also like to provide our users with a way of contacting Harry Hawk, so we're adding a link that sends an e-mail to Harry. To do this, we convert our data in the model to match the sap.m.URLHelper.normalizeEmail API. As soon as the user changes the name, the e-mail also changes. We need a custom formatter function for this.")

**Previous:**[Step 11: Validation Using sap/ui/core/Messaging](Step_11_Validation_Using_sap_ui_core_Messaging_b8c4e53.md "So far, we have created a currency field that can format itself correctly. The currency data type also has the ability to validate that user input adheres to the requirements of a currency; however, data type validation functions are managed by OpenUI5, which of itself has no mechanism for reporting error messages back to the UI; therefore, we need a mechanism for reporting error messages raised by validation functions back to the user. In this step, we will enable validation for the entire app with a feature known as the &quot;Messaging&quot;. Once this is done, any validation error messages generated based on the user input will be passed to Messaging, which in turn will connect them to the appropriate view and control that caused the error.")

**Related Information**  


[Formatting, Parsing, and Validating Data](Formatting_Parsing_and_Validating_Data_07e4b92.md "Data that is presented on the UI often has to be converted so that is human readable and fits to the locale of the user. On the other hand, data entered by the user has to be parsed and validated to be understood by the data source. For this purpose, you use formatters and data types.")

