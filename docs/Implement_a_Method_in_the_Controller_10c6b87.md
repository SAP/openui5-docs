<!-- loio10c6b87c3728417f95a428cb7decb64c -->

| loio |
| -----|
| 10c6b87c3728417f95a428cb7decb64c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/10c6b87c3728417f95a428cb7decb64c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/10c6b87c3728417f95a428cb7decb64c)</div>

## Implement a Method in the Controller

All functions that are not directly related to the user interface should be handled in the controller to ensure clear separation between UI and data. In this case you add a method to handle the event, which is attached to a button.

***

You've created a button as described in: [Add a Control to Your View](Add_a_Control_to_Your_View_07d2bdc.md)

1.  To handle this event, add the following function to the controller:

    ``` java
    doIt : function(oEvent) { alert(oEvent.getSource().getId() + " does it!"); }
    ```


