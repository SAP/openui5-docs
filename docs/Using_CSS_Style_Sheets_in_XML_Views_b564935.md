<!-- loiob564935324f449209354c7e2f9903f22 -->

| loio |
| -----|
| b564935324f449209354c7e2f9903f22 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b564935324f449209354c7e2f9903f22) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b564935324f449209354c7e2f9903f22)</div>

## Using CSS Style Sheets in XML Views

Style sheets are included in XML views in the same way as plain HTML. To add further CSS classes to OpenUI5 controls, use the `class` attribute.

***

The effect is the same as calling `myButton.addStyleClass(...)`.

> ### Tip:  
> We recommend to carefully choose the elements that you style as the CSS always affects the whole page and is **not** restricted to the view.

***

1.  To add a style sheet, add the style definition.

    To add a style class and define a button that uses it, add the following coding:

    ``` html
    
    <mvc:View controllerName="sap.hcm.Address" xmlns="sap.m" xmlns:mvc="sap.ui.core.mvc"
               xmlns:html="http://www.w3.org/1999/xhtml">
       <html:style>
          .mySuperRedButton {
             color: red;
          }
       </html:style>
       <Panel>
          <Button class="mySuperRedButton" text="Press Me"/>
       </Panel>
    </mvc:View>
    ```

    > ### Note:  
    > To allow your view to be used in an environment with a Content Security Policy denying inline styles \(i.e. without the `unsafe-inline` source for the `style-src` directive\), you need to refer to an external style sheet instead of embedding the style sheet into your XML view. For more information, see the Walkthrough tutorial, [Step 14: Custom CSS and Theme Colors](Step_14_Custom_CSS_and_Theme_Colors_723f4b2.md).


