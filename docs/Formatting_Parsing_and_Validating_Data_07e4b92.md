<!-- loio07e4b920f5734fd78fdaa236f26236d8 -->

| loio |
| -----|
| 07e4b920f5734fd78fdaa236f26236d8 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/07e4b920f5734fd78fdaa236f26236d8) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/07e4b920f5734fd78fdaa236f26236d8)</div>

## Formatting, Parsing, and Validating Data

Data that is presented on the UI often has to be converted so that is human readable and fits to the locale of the user. On the other hand, data entered by the user has to be parsed and validated to be understood by the data source. For this purpose, you use formatters and data types.

***

![](loio40f0541313154bb0b5de72e2bd1c9207_LowRes.png)

-   [Views](Views_91f27e3.md)
-   [Models](Models_e1b6259.md)

Formatters are used to define the formatting of data on the UI while data types work in both directions: they format the data on the UI and parse and validate user input that is entered.

You can either use standard formatters and data types or define your own custom objects. OpenUI5 provides standard formatter classes that can be used to define custom data types and custom formatters.

If an error occurs during formatting or parsing, the following exception occurs: `sap/ui/model/FormatException` / `sap/ui/model/ParseException`.

> ### Note:  
> For some controls like `sap/m/Input` you can also use API properties that define the data type and add additional features like restricted input options, for example, `<Input **type="Number"**/>`.

***

<a name="loio07e4b920f5734fd78fdaa236f26236d8__section_rgn_hc5_xcb"/>

### Formatters

***

> ### Note:  
> When using formatter functions, the binding is automatically switched to "one-way". So you can’t use a formatter function for "two-way" scenarios, but you can use [Data Types](Formatting_Parsing_and_Validating_Data_07e4b92.md#loio07e4b920f5734fd78fdaa236f26236d8__section_DataTypes).

A simple formatter can be defined directly in the controller. For example, you can format name data with the first letter in upper case:

``` js
myFormatter: function(sName) {
    return sName.charAt(0).toUpperCase() + sName.slice(1);
}
```

> ### Note:  
> We recommend to use a separate `formatter.js` file that groups the formatters and makes them globally available in your app. You can then load the formatters in any controller by defining a dependency and instantiating the formatter file in a `formatter` variable. For more information, see [Step 22: Custom Formatters](Step_22_Custom_Formatters_0f8626e.md) in the *Walkthrough* tutorial.

When the formatter is defined in the controller, you can use it, for example, in an XML view:

``` xml
<Text text="{
    path : 'person/name',
    *HIGHLIGHT START*formatter : '.myFormatter'*HIGHLIGHT END*
}" />
```

> ### Note:  
> You can also use predefined formatter functions for standard uses cases, like `formatMessage` from module `sap/base/strings/formatMessage`.

> ### Caution:  
> The automatic type determination for OData V4 interacts with `targetType` and can, thus, influence a formatter’s input values. For more information on type determination in OData V4, see [Type Determination](Type_Determination_53cdd55.md).

***

<a name="loio07e4b920f5734fd78fdaa236f26236d8__section_DataTypes"/>

### Data Types

***

#### Simple Types

If you also want to validate and parse input values, you use data types. All data types inherit from the abstract `sap.ui.model.Type` class.

A subclass of this class is `sap.ui.model.SimpleType`. The currently available types inherit from `SimpleType` class.

For simple data types, you can generate the following parameters in the constructor:

-   `formatOptions`: Format options define how a value is formatted and displayed in the UI.

-    `constraints`: Constraints are optional and define how an input value entered in the UI should look like. During parsing the value is validated against these constraints. For example, an `Integer` type has a constraint for `maximum` that is automatically validated when parsing the input values.


``` xml
<mvc:View 
   xmlns:core="sap.ui.core" 
   xmlns:mvc="sap.ui.core.mvc" 
   core:require="{
      Integer: 'sap/ui/model/type/Integer'
   }">
   ...
  <Input value="{
      path: '/number',
      type: 'Integer',
      *HIGHLIGHT START*formatOptions*HIGHLIGHT END*: {
          minIntegerDigits: 3
      },
          *HIGHLIGHT START*constraints*HIGHLIGHT END*: {
      maximum: 1000
      }
  }" />
   ...
</mvc:View>
```

> ### Note:  
> This sample uses `core:require` to ensure the type module is imported and to enable the use of the short type name `Integer` instead of the full name in the declaration of data binding. For more information, see [Require Modules in XML View and Fragment](Require_Modules_in_XML_View_and_Fragment_b11d853.md).

For a complete list of all simple types, see [API Reference: `sap.ui.model.Type`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.type/overview). 

***

#### OData Types

These types support OData V2 and V4 including relevant property facets as constraints. The OData types represent the OData EDM primitive types. For more information, see [Primitive Data Types in the OData documentation](http://www.odata.org/documentation/odata-version-2-0/overview/).

For a complete list of all OData types, see [API Reference: `sap.ui.model.odata.type`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.type). 

> ### Note:  
> Also see the information on automatic type determination in OData V4 under [Type Determination](Type_Determination_53cdd55.md).

***

#### Custom Data Types

You can also define a custom data type based on `sap.ui.model.SimpleType` by specifying a custom implementation for `formatValue`, `parseValue`, and `validateValue`:

```
sap.ui.define([
    "sap/ui/model/SimpleType"
], function (SimpleType) {
    "use strict";
    return SimpleType.extend("sap.ui.demo.myCustomType", {

        formatValue: ...

        parseValue: ...

        validateValue: ...

    });
});
```

> ### Example:  
> [Step 5: Adding a Flag Button](Step_5_Adding_a_Flag_Button_69a25bf.md) of the *Testing* tutorial shows how to implement a custom data type.

-   **[Simple Data Types](Simple_Data_Types_91f06be.md)**  

-   **[Formatter Classes](Formatter_Classes_35cbd6c.md)**  


**Related Information**  


[Binding Syntax](Binding_Syntax_e2e6f41.md "You bind UI elements to data of a data source by defining a binding path to the model that represents the data source in the app.")

