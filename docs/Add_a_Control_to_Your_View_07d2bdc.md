<!-- loio07d2bdc3ad0e4c62b14123e6f80dca56 -->

| loio |
| -----|
| 07d2bdc3ad0e4c62b14123e6f80dca56 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/07d2bdc3ad0e4c62b14123e6f80dca56) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/07d2bdc3ad0e4c62b14123e6f80dca56)</div>

## Add a Control to Your View

In your SAPUI5 application project, the first step to build your application is to add a control to your view and implement a method to react on user interaction. In this case you create a button and implement a function to react when the user presses it.

1.  To add a control to your view, add the following coding depending on the type of your view:

    -   In a `JS view` add the following to the `createContent` function

        ``` js
        var aControls = [];
               var oButton = new sap.ui.commons.Button({
                 id : this.createId("MyButton"),
                 text : "Hello JS View"
               });
               aControls.push(oButton.attachPress(oController.doIt));
               return aControls;
        ```

    -   In an HTML view add the following to the `template` tag:

        ``` html
        <div data-sap-ui-type="sap.ui.commons.Button" id="MyButton"
          data-text="Hello HTML View" data-press="doIt">
        </div>   
          
        ```

    -   In an XML view add the following coding to the `core` tag

        ``` xml
        <Button id="MyButton" text="Hello XML View" press="doIt"/>
        
        ```

    -   In a JSON view add the following to the `content` function

        ``` js
        "Type":"sap.ui.commons.Button",
              "id":"MyButton",
              "text":"Hello JSON View",
              "press":"doIt"
        ```

    A button is added to your view with an event that is triggered when the user presses it.


***

The **doIt** method, which is called in each of these view types, is implemented in the controller:

[Implement a Method in the Controller](Implement_a_Method_in_the_Controller_10c6b87.md)

