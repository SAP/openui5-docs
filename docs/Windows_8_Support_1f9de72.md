<!-- loio1f9de72bea734beaafa86b80c2c4222c -->

| loio |
| -----|
| 1f9de72bea734beaafa86b80c2c4222c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/1f9de72bea734beaafa86b80c2c4222c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/1f9de72bea734beaafa86b80c2c4222c)</div>

## Windows 8 Support

Devices such as Windows 8 touch-enabled laptops now support both mouse and touch input methods together. As a control developer you have to take this into consideration.

> Note:
> OpenUI5 event delegation is adapted and the `ontouch` or `ontap` functions on the control prototype are called on both touch and mouse \(exclude the emulated mouse events on touch interfaces\) events. This enables the controls which only uses OpenUI5 event delegation for event handling to work seamlessly on Windows 8 touch-enabled devices without being changed. So for you as an OpenUI5 application developer there is no need to change or adapt your applications to support devices that allow input from both mouse and touch.
> 
> 

When you develop your own controls, then there are some things to consider:

***

### Background: How OpenUI5 handles events

With the introduction of touch-enabled Window 8 devices, touch is becoming part of the expected desktop experience. In the past, UI5 statically detected whether the running environment supports touch events. Then the assumption was made that only touch \(and not mouse\) events need to be supported. This assumption became faulty with the emerging of touch-enabled Windows 8 devices. The fact that touch events are supported doesn't mean that user can't use other input device than touch. Therefore, "support touch" is not equal to "doesn't need mouse support" anymore. For all these reasons, we don't switch between touch and mouse - we now just support both of them!

The following figure shows how this is implemented:

 ![](loio56d796e4026f463ab92c1ec10818f339_LowRes.png) 

A desktop control is defined as a control that listens to mouse events, whereas a mobile control listens to touch events. To ensure that all events can be received, for mouse events touch simulation events are created and for touch events mouse simulation events, respectively. So the UI Area, which acts as an event delegate, receives the correct events. In detail:

-   When a mouse event is triggered for a desktop control, it's handed over to the UI area directly.
-   When a mouse event is triggered for a mobile control, a touch event is simulated and handed over to the UI area.
-   When a touch event is triggered for a mobile control, it's handed over to the UI area directly.
-   When a touch event is triggered for a desktop control, a mouse event is simulated and handed over to the UI area.
-   Some browsers send a delayed mouse event after a touch event, this is just ignored.

So it is ensured that all events can be handled and no event is triggered twice.

***

### Support mouse and touch events together

Touch interfaces try to emulate mouse and click events obviously because touch interfaces need to work with applications that have only interacted with mouse events before. This means for a single tap on touch interfaces, the following events are fired in the written order:

1.  `touchstart`
2.  `touchend`
3.  `mousedown`
4.  `mouseup`
5.  `click`

If we support mouse and touch together, the event handler is called twice for a single tap because there are touchstart and mousedown fired by the browser. Fortunately, we have found a way to set a flag on the emulated mouse events from touch interfaces and suppress those events when they reach the event handler.

**Related information**  


[Adapting Event Handling to Support Windows 8 Devices](Adapting_Event_Handling_to_Support_Windows_8_Devices_b54d7d7.md)

[Device-specific Behavior of Controls](Device-specific_Behavior_of_Controls_a53ec81.md)

[Windows 8 Support - Known Issues](Windows_8_Support_-_Known_Issues_8168059.md)

