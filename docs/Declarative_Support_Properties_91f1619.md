| loio |
| -----|
| 91f161996f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/91f161996f4d1014b6dd926db0e91070.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f161996f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f161996f4d1014b6dd926db0e91070)</div>
<!-- loio91f161996f4d1014b6dd926db0e91070 -->

## Declarative Support: Properties

For setting a property, define the property as a data attribute of the corresponding HTML tag.

To add text to the button, add the attribute `data-text` to its HTML tag:

```lang-html

<div data-sap-ui-type="sap.m.Button" data-text="HelloWorld"></div>
```

> Note:
> To define a property with upper case characters, you have to "escape" them with a dash character, similar to CSS attributes. The following code gives an example:
> 
> ```lang-html
> 
> <div data-sap-ui-type="sap.ui.commons.ApplicationHeader" data-display-logoff="false" data-display-welcome="false"></div>
> ```
> 
> As the name of the attributes of HTML tags are case-insensitive, the properties `displayLogoff` and `displayWelcome` of the `ApplicationHeader` control have to be "escaped" as `data-display-logoff` and `data-display-welcome` for the name of the attributes of the HTML tag. Keep this in mind when matching properties, associations, or events as an attribute of the HTML tag.
> 
> The ``id`` attribute defines the ID of a control:
> 
> ```lang-html
> 
> <div data-sap-ui-type="sap.m.Button" id="myButton"></div>
> ```
> 
> To add a CSS class to the control, use the class attribute:
> 
> ```lang-html
> 
> <div data-sap-ui-type="sap.m.Button" class="my-button"></div>
> ```
> 
> 

