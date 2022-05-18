<!-- loiobe54950cae1041f59d4aa97a6bade2d8 -->

| loio |
| -----|
| be54950cae1041f59d4aa97a6bade2d8 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/be54950cae1041f59d4aa97a6bade2d8) | [demo kit latest release](https://sdk.openui5.org/topic/be54950cae1041f59d4aa97a6bade2d8)</div>

## Using Native HTML in XML Views

The use of native HTML in XML views depends on the XHTML feature set.

***

When mixing XHTML and OpenUI5 controls, observe the following rules:

-   XHTML elements can be used instead of the OpenUI5 type control, for example, in the root of an XML view or in the content aggregation of a layout container.

-   When embedding XHTML in an aggregation of a OpenUI5 control, the XHTML must not consist of a single text node. The topmost node of an embedded XHTML tree must be an XHTML element. Embedding pure text into an aggregation is not supported.

-   The XHTML nodes are converted 1:1 to HTML, the XML view does not deal with any differences between XHTML and HTML \(for example rewriting and auto-closing tags\)

-   The created HTML DOM nodes are preserved during re-rendering of an XML view: Modifications to the DOM are not lost.


> ### Note:  
> As an alternative to embedding XHTML, you can use the `sap.ui.core.HTML` control. As this requires content encoding it is, however, less convenient.

> ### Note:  
> Native XHTML can't be used in the binding template for a bound aggregation \(e.g., the `content` aggregation\) of the XML view.

***

1.  To mix OpenUI5 controls with native XHTML, you only need the XHTML namespace to use \(X\)HTML:

    ```xml
    <mvc:View controllerName="sap.hcm.Address" xmlns="sap.m" xmlns:mvc="sap.ui.core.mvc"
               xmlns:html="http://www.w3.org/1999/xhtml">
       <Panel>
          <Button text="Press Me. I am an SAPUI5 Button"/>
          <html:button>No, press me. I am native HTML Button.</html:button>
       </Panel>
    </mvc:View>
    ```


