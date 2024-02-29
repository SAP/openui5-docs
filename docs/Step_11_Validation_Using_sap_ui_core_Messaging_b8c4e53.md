<!-- loiob8c4e534cdb440e9a5bbff86f9572bd6 -->

| loio |
| -----|
| b8c4e534cdb440e9a5bbff86f9572bd6 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/b8c4e534cdb440e9a5bbff86f9572bd6) | [demo kit latest release](https://sdk.openui5.org/topic/b8c4e534cdb440e9a5bbff86f9572bd6)</div>

## Step 11: Validation Using `sap/ui/core/Messaging`

So far, we have created a currency field that can format itself correctly. The currency data type also has the ability to validate that user input adheres to the requirements of a currency; however, data type validation functions are managed by OpenUI5, which of itself has no mechanism for reporting error messages back to the UI; therefore, we need a mechanism for reporting error messages raised by validation functions back to the user. In this step, we will enable validation for the entire app with a feature known as the "Messaging". Once this is done, any validation error messages generated based on the user input will be passed to `Messaging`, which in turn will connect them to the appropriate view and control that caused the error.

***

### Preview

  
  
**A message appears**

![](images/loioe67207b43d08410e82e74ad57ffbc022_HiRes.png "A message appears")

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 11](https://sdk.openui5.org/entity/sap.ui.core.tutorial.databinding/sample/sap.ui.core.tutorial.databinding.11).

***

### webapp/manifest.json

Enter the highlighted line into the `manifest.json` file to generally enable validation in the app.

```js
...
"sap.ui5": {
	"handleValidation": true,
	"dependencies": {
		"minUI5Version": "1.120.0",
		"libs": {
			"sap.m": {},
			"sap.ui.core": {},
			"sap.ui.layout": {}
		}
	},
...
```

You can now enter a non-numeric value into the *Sales Amount* field and either press [Enter\] or move the focus to a different UI control. This action triggers either the `onenter` or `onchange` event, and then OpenUI5 executes the validation function belonging to the `sap.ui.model.type.Currency` data type.

Now that validation handling has been enabled in the manifest, any validation error messages will be picked up by `Messaging`, which in turn checks its list of registered objects and then passes the error message back to the correct view for display.

Note that the field in error has a red border: ![](images/loio44db88e92bc445b2b00e1b8e53b5ca9a_HiRes.png)

However, the error message itself will only be displayed when that particular field has focus: ![](images/loioe67207b43d08410e82e74ad57ffbc022_HiRes.png)

**Parent topic:**[Data Binding Tutorial](Data_Binding_Tutorial_e531093.md "In this tutorial, we will explain the concepts of data binding in OpenUI5.")

**Next:**[Step 10: Property Formatting Using Data Types](Step_10_Property_Formatting_Using_Data_Types_9252ee4.md "OpenUI5 provides a set of simple data types such as Boolean, Currency, Date and Float. These data types can then be applied to controls in order to ensure that the value presented on the screen is formatted correctly, and, if the field is open for input, that the value entered by the user adheres to the requirements of that data type. We will now add a new field called Sales Amount of type Currency.")

**Previous:**[Step 12: Aggregation Binding Using Templates](Step_12_Aggregation_Binding_Using_Templates_97830de.md "Aggregation binding (or &quot;list binding&quot;) allows a control to be bound to a list within the model data and allows relative binding to the list entries by its child controls.")

**Related Information**  


[Error, Warning, and Info Messages](Error_Warning_and_Info_Messages_62b1481.md "OpenUI5 provides a central place for storing and managing info, warning, and error messages.")

