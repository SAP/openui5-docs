<!-- loio8168059f21bb41bda96901eaf9c4302e -->

| loio |
| -----|
| 8168059f21bb41bda96901eaf9c4302e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8168059f21bb41bda96901eaf9c4302e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8168059f21bb41bda96901eaf9c4302e)</div>

## Windows 8 Support - Known Issues

Information regarding known issues with regard to Windows 8 support.

***

### Firefox doesn't simulate mouse events correctly for touch input method

Firefox currently only fires mouse events on Windows 8 for both touch and mouse input methods. When a touch input method is used to perform a single tap, all of the mouse events aren't fired until the touch input is released from the screen. This causes an issue that all UI updates between `mousedown` and `mouseup` events can't be reflected on the UI because UI Tray doesn't get the chance to update. For example, a blue color should be shown when button is tapped and set back to the normal color after tap. This blue color can't be seen on Firefox because the setting and resetting of blue color are executed in a row and UI Tray doesn't have the time to reflect the blue color.

A fix is only available in the beta version of Mozilla Firefox. Here you can start Firefox in Windows 8 metro mode in which touch events are fired instead of mouse events when touch input method is used.

In the desktop mode of Firefox, touch event support is off and can be turned on only by modifying the `dom.w3c_touch_events.enabled` parameter.

***

### More Information

-   [Mozilla Firefox Beta version](http://www.mozilla.org/en-US/firefox/beta/) 
-   [Mozilla Support: How do I launch Firefox for Windows 8 Touch?](https://support.mozilla.org/en-US/kb/how-do-i-launch-firefox-windows-8-touch)
-   [Mozilla Firefox - Touch events](https://developer.mozilla.org/en-US/docs/Web/Guide/Events/Touch_events)

