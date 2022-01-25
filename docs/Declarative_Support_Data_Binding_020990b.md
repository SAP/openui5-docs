<!-- loio020990b1210e47c89a58a4f4e790c476 -->

| loio |
| -----|
| 020990b1210e47c89a58a4f4e790c476 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/020990b1210e47c89a58a4f4e790c476) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/020990b1210e47c89a58a4f4e790c476)</div>

## Declarative Support: Data Binding

Declarative support in OpenUI5 also enables data binding.

Just add the model path in curly brackets and bind the model to the control \(or parent control\):

``` html

<div data-sap-ui-type="sap.m.Button" data-text="{/stringValue}" data-enabled="{model2>/booleanValue}"></div>
```

0..n aggregations can define templates to use for the list binding:

``` html

<div data-sap-ui-type="sap.m.Carousel" data-content="{/buttons}">
    <div data-sap-ui-type="sap.m.Button" data-text="{title}"></div>
</div>
```

In the example above, the button template is used for the carousel content data binding.

**Related Information**  


[Data Binding](Data_Binding_68b9644.md "You use data binding to bind UI elements to data sources to keep the data in sync and allow data editing on the UI.")

