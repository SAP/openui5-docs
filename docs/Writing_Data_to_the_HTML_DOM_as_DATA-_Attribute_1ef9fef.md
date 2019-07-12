| loio |
| -----|
| 1ef9fefa2a574735957dcf52502ab8d0 |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/1ef9fefa2a574735957dcf52502ab8d0.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/1ef9fefa2a574735957dcf52502ab8d0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/1ef9fefa2a574735957dcf52502ab8d0)</div>
<!-- loio1ef9fefa2a574735957dcf52502ab8d0 -->

## Writing Data to the HTML DOM as DATA-\* Attribute

OpenUI5 supports writing custom data to the HTML DOM.

These are two use cases, where this feature can be useful:

-   To generate markers in the HTML from data binding which then can then be used for data-dependent styling.

-   To create stable anchors in the HTML which can be used for automated tests.


A "data-" prefix is added to the key and the result is then written as an attribute into the root HTML element of the control. The `CustomData` value is written as an attribute value.

For this, the key has to be a valid HTML ID and the value has to be a string; otherwise an error is logged.

> Note:
> HTML attribute names are case-insensitive and browsers may convert the key to lowercase.
> 
> Do not write too much data into the DOM.
> 
> 

In JavaScript, you can set the flag as shown in the following code snippet:

```lang-js

myButton.data("mydata", "Hello", true); // attach some data to the Button and mark it as
          "write to HTML"
```

To set the `writeToDom` flag in XML views, the aggregation has to be written in expanded notation:

```lang-xml

<Button ... >
  <customData>
  <core:CustomData key="mydata" value="Hello" writeToDom="true" />
  </customData>
</Button>
```

This results in the following HTML:

```
<button ...  data-myData="Hello"  ... >
```

This is done similarly in HTML views:

```lang-html

<div data-sap-ui-type="sap.m.Button" data-text="This button has custom data written to the DOM">
   <div data-sap-ui-aggregation="customData">
      <div data-sap-ui-type="sap.ui.core.CustomData" data-key="mydata" data-value="Hello" data-write-to-dom="true"/>
   </div>
</div>

```

The CSS can now use attribute selectors to check the presence or the value of the custom data attribute:

```

button[data-mydata="Hello"] { border: 3px solid red !important; }
```

