<!-- loiob54d7d73eff245d3ab91b96e21177ebf -->

| loio |
| -----|
| b54d7d73eff245d3ab91b96e21177ebf |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b54d7d73eff245d3ab91b96e21177ebf) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b54d7d73eff245d3ab91b96e21177ebf)</div>

## Adapting Event Handling to Support Windows 8 Devices

OpenUI5 event delegation automatically handles both mouse and touch events simultaneously. If you are using jQuery or native browser API \(`domElement.addEventListener`\) to handle events, you have to adapt your coding to support both.

***

In addition, emulated mouse events shouldn't be handled otherwise the event handler is called twice for the touch. This can be achieved by checking the flag \(`_sapui_delayedMouseEvent`\) we set to the emulated mouse events. We have extended the `jQuery.Event` object with `isMarked` function for checking UI5 specific flags on the real event object. The `sapui` prefix is already considered within the `isMarked`function so only the semantic part needs to be passed into the function \(for example, for checking if the flag `_sapui_delayedMouseEvent` is marked, simply call `isMark` \(`delayedMouseEvent`\)\). But when event handler is bound using browser API like `addEventListener`, flag needs to be checked by using the full flag name since there's no `isMarked` function on the browser event object.

In most of the cases, the event handler was bound by checking if touch is supported, like the code below:

``` js
// "Device" required from module "sap/ui/Device"
jQuery(document).on(Device.support.touch ? "touchmove" : "mousemove", function(oEvent) {
    ......
});
```

1.  Since both mouse and touch should be supported, the code needs to be changed as follows.

    -   When using jQuery:

        ``` js
        
        jQuery(document).on("touchmove mousemove", function(oEvent) {
            if (oEvent.isMarked("delayedMouseEvent")) {
        
                // Suppress the emulated mouse event from touch interface
                return;
            }
            ......
        });
        ```

    -   When using native browser event listeners:

        ``` js
        
        var fnHandler = function (oEvent ) { if (oEvent . _sapui_delayedMouseEvent ) { // Suppress the emulated mouse event from touch interface
         return ; } ...... };
        
        document . addEventListener ( "touchmove" , fnHandler );
        document . addEventListener ( "mousemove" , fnHandler );
        ```

2.  Same should be applied for the all touch and mouse event pairs when the events are needed:

    -   `touchstart` and `mousedown`
    -   `touchmove` and `mousemove`
    -   `touchend`, `touchcancel` and `mouseup`

***

We have also adapted some controls within `sap.m` for Windows 8 support. Let's take `sap/m/RatingIndicator` as an example. User can drag the rating indicator to change the rating value. This is implemented by registering to `touchmove` or `mousemove` event in `ontouchstart` function and `deregister` from `touchmove` or `mousemove`by listening to `touchend`, `touchcancel` or `mouseup`.

**Before the adaptation, code was:**

``` js
// "RatingIndicator" defined in module "sap/m/RatingIndicator"
// "Device" required from module "sap/ui/Device"
RatingIndicator.prototype.ontouchstart = function(oEvent) {
    if (this.getEnabled()) {
        ......

        if (!this._touchEndProxy) {
            this._touchEndProxy = jQuery.proxy(this._ontouchend, this);
        }

        if (!this._touchMoveProxy) {
            this._touchMoveProxy = jQuery.proxy(this._ontouchmove, this);
        }

        // here also bound to the mouseup mousemove event to enable it working in
        // desktop browsers
        if (Device.support.touch) {
            jQuery(window.document).on("touchend touchcancel", this._touchEndProxy);
            jQuery(window.document).on("touchmove", this._touchMoveProxy);
        } else {
            jQuery(window.document).on("mouseup", this._touchEndProxy);
            jQuery(window.document).on("mousemove", this._touchMoveProxy);
        }

        ......
    }
};

RatingIndicator.prototype._ontouchmove = function(oEvent) {
    ......
};

RatingIndicator.prototype._ontouchend = function(oEvent) {
    if (this.getEnabled()) {
        ......
        if (Device.support.touch) {
            jQuery(window.document).off("touchend touchcancel", this._touchEndProxy);
            jQuery(window.document).off("touchmove", this._touchMoveProxy);
        } else {
            jQuery(window.document).off("mouseup", this._touchEndProxy);
            jQuery(window.document).off("mousemove", this._touchMoveProxy);
        }
        ......
    }
};
```

**After the code adaptation:**

``` js
// "RatingIndicator" defined in module "sap/m/RatingIndicator"
// "Device" required from module "sap/ui/Device"
RatingIndicator.prototype.ontouchstart = function (oEvent) {
    if (this.getEnabled()) {
        ......

        if (!this._touchEndProxy) {
            this._touchEndProxy = jQuery.proxy(this._ontouchend, this);
        }
        if (!this._touchMoveProxy) {
            this._touchMoveProxy = jQuery.proxy(this._ontouchmove, this);
        }

        // The if (Device.support.touch) is removed and both mouse and touch events are supported always
        jQuery(window.document).on("touchend touchcancel mouseup", this._touchEndProxy);
        jQuery(window.document).on("touchmove mousemove", this._touchMoveProxy);

        ......
    }
};

RatingIndicator.prototype._ontouchmove = function (oEvent) {
    // Check the _sapui_delayedMouseEvent flag for the emulated mouse event from touch interface
    if (oEvent.isMarked("delayedMouseEvent")) {
        return;
    }
    ......
};

RatingIndicator.prototype._ontouchend = function (oEvent) {
    // Check the _sapui_delayedMouseEvent flag for the emulated mouse event from touch interface
    if (oEvent.isMarked("delayedMouseEvent")) {
        return;
    }
    
    if (this.getEnabled()) {
        ......

        // The if (Device.support.touch) is removed, just deregister from every event
        jQuery(window.document).off("touchend touchcancel mouseup", this._touchEndProxy);
        jQuery(window.document).off("touchmove mousemove", this._touchMoveProxy);

        ......
    }
};
```

