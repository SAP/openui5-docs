<!-- loio9756f4745c0548ba9fea24ad2c0799c3 -->

| loio |
| -----|
| 9756f4745c0548ba9fea24ad2c0799c3 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9756f4745c0548ba9fea24ad2c0799c3) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9756f4745c0548ba9fea24ad2c0799c3)</div>

## HTML View

An HTML View is defined by declarative HTML. Like the declarative support, the HTML view supports embedded HTML. The view file ends with `view.html`, for example `myview.view.html`.

> Note:
> ``` html
>   <template data-controller-name="example.mvc.test">
>    Hello
>   <h1>Title</h1>
>   <div>Embedded HTML</div>
>   <div class="test test2 test3" data-sap-ui-type="sap.m.Panel" id="myPanel">
>   <div class="test test2 test3" data-sap-ui-type="sap.m.Button" id="Button1" data-text="Hello World" data-press="doIt"></div>
>   <div data-sap-ui-type="sap.m.Button" id="Button2" data-text="Hello"></div>
>   <div data-sap-ui-type="sap.ui.core.mvc.HTMLView" id="MyHTMLView" data-view-name="example.mvc.test2"></div>
>   <div data-sap-ui-type="sap.ui.core.mvc.JSView" id="MyJSView" data-view-name="example.mvc.test2"></div>
>   <div data-sap-ui-type="sap.ui.core.mvc.JSONView" id="MyJSONView" data-view-name="example.mvc.test2"></div>
>   <div data-sap-ui-type="sap.ui.core.mvc.XMLView" id="MyXMLView" data-view-name="example.mvc.test2"></div>
>   </div>
> </template>
> ```
> 
> 

All view-specific properties can be added to the `<template>` tag as `data-*` attributes.

**Related information**  


[Declarative Support](Declarative_Support_91f1301.md)

