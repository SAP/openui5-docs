<!-- loio9860cd2b183540f48ee054bcef44a8b5 -->

| loio |
| -----|
| 9860cd2b183540f48ee054bcef44a8b5 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/9860cd2b183540f48ee054bcef44a8b5) | [demo kit latest release](https://sdk.openui5.org/topic/9860cd2b183540f48ee054bcef44a8b5)</div>

## Mobile Events

In addition to the general browser and control events you can access specific events for touch-enabled devices.

When implementing OpenUI5 controls, some browser events can be handled very easily by implementing a method named `on<eventName>`, so all the bind/unbind effort is avoided. This is equally possible on mobile.

On touch-enabled platforms additional browser and pseudo events are available:

***

<a name="loio9860cd2b183540f48ee054bcef44a8b5__section_N1001C_N10011_N10001"/>

### Additional Mobile Browser Events

On touch-enabled platforms the following events are also provided within UI5 controls to be handled in `on<eventName>` methods:

-   `touchstart` 
-   `touchend` 
-   `touchmove` 
-   `touchcancel` 

***

<a name="loio9860cd2b183540f48ee054bcef44a8b5__section_N1004E_N10011_N10001"/>

### Additional Mobile Pseudo Events

jQuery mobile event handling is used in OpenUI5 when running on touch-enabled devices. From the basic browser events it creates semantically richer events. Some of them are also provided automatically in OpenUI5 controls:

-   `swipe` 
-   `tap` 
-   `swipeleft` 
-   `swiperight` 
-   `scrollstart` 
-   `scrollstop` 

For more information, see [jQuery mobile](http://api.jquerymobile.com/).

***

### Devices Supporting both Mouse and Touch Input

A number of devices allow user interaction by both mouse and touch input. To be able to react to both kind of events, some additional functionality has been introduced.

For more information, see [Devices Supporting both Mouse and Touch Input](Devices_Supporting_both_Mouse_and_Touch_Input_1f9de72.md)

**Related Information**  


[Event Handler Methods](Event_Handler_Methods_bdf3e98.md "Event handler methods are invoked when an event occurs. Method names starting with on are reserved for event handler methods.")

[Browser Events](Browser_Events_91f1b38.md "To react to browser events, a control needs to register for the event either explicitly, or by implementing the event handler.")

