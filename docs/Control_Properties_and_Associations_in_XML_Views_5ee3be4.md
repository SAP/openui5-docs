<!-- loio5ee3be4727864bb08b991414e0428e38 -->

| loio |
| -----|
| 5ee3be4727864bb08b991414e0428e38 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/5ee3be4727864bb08b991414e0428e38) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/5ee3be4727864bb08b991414e0428e38)</div>

## Control Properties and Associations in XML Views

***

### Properties

Property values for controls in XML views are specified as attributes of the XML element tag of the control. The name of the attribute corresponds to the name of the property in the API reference, for example, the property `text` of a the `sap.m.Button` control is specified as `text=”*value*”`.

> Note:
> Escape characters that have a special meaning in XML \(like `<`, or `&`\) when they occur in a property value. Use XML entities instead \(like `&lt;` instead of a `<`, or `&amp;` instead of `&`\).
> 
> 

Attributes in XML views use the same binding syntax as constructors of controls. For example, `“{customerName}”` is used to bind a property against the model property with name `“customerName”`.

***

### Associations

-   Associations of **cardinality `1`**: Define the ID of the associated element in an attribute that has the same name as the association in the XML view.

-   Associations of **cardinality `0..n`**: You can define multiple IDs separated by a blank.


