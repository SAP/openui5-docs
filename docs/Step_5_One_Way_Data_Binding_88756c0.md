<!-- loio88756c08fe144ba08ff1762ad92fc07c -->

| loio |
| -----|
| 88756c08fe144ba08ff1762ad92fc07c |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/88756c08fe144ba08ff1762ad92fc07c) | [demo kit latest release](https://sdk.openui5.org/topic/88756c08fe144ba08ff1762ad92fc07c)</div>

## Step 5: One-Way Data Binding

Unlike the two-way binding behavior we've seen, one-way data binding is also possible. In this case, data travels in one direction only: from the model, through the binding instance, to the consumer \(usually the property of a control\), but never in the other direction. Let's modify the previous example to use one-way data binding. This shows how you can switch off the flow of data from the user interface back to the model if needed.

***

### Preview

  
  
**Two input fields and a checkbox**

![The graphic has an explanatory text](images/loio61d68f167778425bbdd2abd7d550ae65_LowRes.png "Two input fields and a checkbox")

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 5](https://sdk.openui5.org/entity/sap.ui.core.tutorial.databinding/sample/sap.ui.core.tutorial.databinding.05).

***

### webapp/Component.js

Insert the highlighted code into the `Component.js` file. The `init` function calls the init function of its parent, retrieves the default model instance bound to the component, and sets the default binding mode to one-way data binding.

```js
sap.ui.define([
	"sap/ui/core/UIComponent",
	"sap/ui/model/BindingMode"
], (UIComponent, BindingMode) => {
	"use strict";

	return UIComponent.extend("ui5.databinding.Component", {
		metadata : {
			interfaces: ["sap.ui.core.IAsyncContentCreation"],
			manifest: "json"
		},

		init() {
			// call the init function of the parent
			UIComponent.prototype.init.apply(this, arguments);

			this.getModel().setDefaultBindingMode(BindingMode.OneWay);
		}
	});
});
```

Now, regardless of the state the checkbox is in, the input fields remain open for input, because one-way data binding ensures that data flows only from the model to the UI, but never in the other direction.

The binding mode \(one-way or two-way\) is set on the model itself. Therefore, unless you specifically alter it, a binding instance will always be created using the model's default binding mode.

If you wish to alter the binding mode, you've got two options:

-   Alter the model's default binding mode. This is the approach we used above.

-   Specify the data binding mode for a specific binding instance by using the `oBindingInfo.mode` parameter. This change only applies to this data binding instance. Any other binding instances will continue to use the model's default binding mode.For more information, see [API Reference: `sap.ui.base.ManagedObject.bindProperty`](https://sdk.openui5.org/api/sap.ui.base.ManagedObject/methods/bindProperty). 


> ### Note:  
> There are two important points to understand about alterations to a model object's data binding mode:
> 
> -   If you alter the default binding mode of a model \(as in the example above\), **all** binding instances created after that point in time will use the altered binding mode, unless you explicitly say otherwise.
> 
> -   Altering a model's default binding mode doesn't affect already existing binding instances.

**Parent topic:**[Data Binding Tutorial](Data_Binding_Tutorial_e531093.md "In this tutorial, we explain the concepts of data binding in OpenUI5.")

**Next:**[Step 4: Two-Way Data Binding](Step_4_Two_Way_Data_Binding_c72b922.md "In the examples we've looked at so far, we've displayed the value of a model property using a read-only field. We'll now change the user interface to display first and last name fields using sap.m.Input fields. We're also adding a check box control to enable or disable both input fields. This setup illustrates a feature known as &quot;two-way data binding&quot;. As the view now contains more controls, we're also moving the view definition into an XML file.")

**Previous:**[Step 6: Resource Models](Step_6_Resource_Models_9790d9a.md "Business applications often require language-specific (translatable) text used as labels and descriptions on the user interface.")

