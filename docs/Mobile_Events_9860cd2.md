<!-- loio9860cd2b183540f48ee054bcef44a8b5 -->

| loio |
| -----|
| 9860cd2b183540f48ee054bcef44a8b5 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9860cd2b183540f48ee054bcef44a8b5) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9860cd2b183540f48ee054bcef44a8b5)</div>

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

### Windows 8

With Microsoft Windows 8, new devices are also introduced that allow user interaction with both mouse and touch. To be able to react to both kind of events, some new functionality was introduced.

For more information, see [Windows 8 Support](Windows_8_Support_1f9de72.md)

***

<a name="loio9860cd2b183540f48ee054bcef44a8b5__section_N1008E_N10011_N10001"/>

### Simulation of touch events on non-touch platforms

For testing or demonstration purposes, the events listed above can also be simulated on non-touch devices. When this simulation is enabled, the touch events will also be triggered by mouse interaction.

> Note:
> Due to technical constraints the simulation cannot be perfect, so it may not be used productively.
> 
> 

To enable the simulation mode, set the OpenUI5 configuration parameter `xx-test-mobile` to <true\>, for example by appending the URL parameter `sap-ui-xx-test-mobile=true`.

**Related information**  


[Event Handler Methods](Event_Handler_Methods_bdf3e98.md)

[Browser Events](Browser_Events_91f1b38.md)

