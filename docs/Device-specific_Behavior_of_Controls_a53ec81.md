<!-- loioa53ec81aca59413cac86267b0fd5c787 -->

| loio |
| -----|
| a53ec81aca59413cac86267b0fd5c787 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a53ec81aca59413cac86267b0fd5c787) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a53ec81aca59413cac86267b0fd5c787)</div>

## Device-specific Behavior of Controls

Some controls have different behaviors between running on different device types \(mobile, desktop, tablet\).

For example, the `sap.m.Carousel` control shows the left and right navigation buttons in addition to gesture only when it runs on desktop. The distinction between desktop and mobile behaviors should be done by checking `sap.ui.Device.system.desktop` but NOT `sap.ui.Device.support.touch` because desktop browser can also support touch, for example Windows 8 touch-enabled device.

A property `combi` is provided in `sap.ui.Device.support` with which you can tell that the browser supports both touch and mouse interfaces.

Not all browser on Windows 8 touch-enabled device support touch events. Some browser fires mouse events when user operates with finger. Since those mouse events are not marked with `_sapui_delayedMouseEvents`, they can still be handled with OpenUI5 event delegation and the registered handler.

