| loio |
| -----|
| 020990b1210e47c89a58a4f4e790c476 |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/020990b1210e47c89a58a4f4e790c476.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/020990b1210e47c89a58a4f4e790c476) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/020990b1210e47c89a58a4f4e790c476)</div>
<!-- loio020990b1210e47c89a58a4f4e790c476 -->

## Declarative Support: Data Binding

Declarative support in OpenUI5 also enables data binding.

Just add the model path in curly brackets and bind the model to the control \(or parent control\):

```lang-html

<div data-sap-ui-type="sap.m.Button" data-text="{/stringValue}" data-enabled="{model2>/booleanValue}"></div>
```

0..n aggregations can define templates to use for the list binding:

```lang-html

<div data-sap-ui-type="sap.m.Carousel" data-content="{/buttons}">
    <div data-sap-ui-type="sap.m.Button" data-text="{title}"></div>
</div>
```

In the example above, the button template is used for the carousel content data binding.

**Related information**  


[Data Binding](Data_Binding_68b9644.md)

