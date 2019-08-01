<!-- loio91f1b3856f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f1b3856f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f1b3856f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f1b3856f4d1014b6dd926db0e91070)</div>

## Browser Events

To react to browser events, a control needs to register for the event either explicitly, or by implementing the event handler.

OpenUI5 applications can have the following two event types:

-   Browser events: These events are fired by the browser; examples for browser events are `click` and `blur`.

-   Control events: These events are fired by OpenUI5 controls. They contain more semantic information than browser events and relate to the control functionality. An example for a control event is when a browser's a `click` event on an icon in a panel header that triggers a `maximize` or `minimize` event of the control.


To register browser events explicitly for certain DOM elements, use either `jQuery.bind()` or the respective browser methods, such as `addEventListener` and register the event in the `onAfterRendering` method of the control. This ensures that the event binding is repeated after the control is rerendered, meaning that new DOM elements are created and old DOM elements are discarded. The event binding must be removed in the `onBeforeRendering` and `exit` methods by using `jQuery.unbind()` to prevent memory leaks. The `exit` method is called before the control is destroyed.

The explicit registering for browser events enables you to handle any type of browser event and works exactly the same way as in web pages or jQuery-based web applications. On the other hand side, it requires some coding to do the binding and unbinding of the event handler and registering many event handlers can affect the performance.

Example for explicit registration of browser events:

``` js
MyControl.prototype.onAfterRendering = function() {
        this.$().bind("click", this.handleClick.bind(this));
}

MyControl.prototype.onBeforeRendering = function() {
        this.$().unbind("click", this.handleClick);
}


MyControl.prototype.exit = function() {
        this.$().unbind("click", this.handleClick);
}


MyControl.prototype.handleClick = function(oEvent) {
        // do something...
}
```

Instead of explicitly registering for browser events, you can implement the event handler directly for certain common event types by using a naming convention for the handler method. OpenUI5 automatically registers event handlers for a list of commonly used event types on the root element of a complete tree of OpenUI5 controls. For more information about these event types, see the [API Reference](https://openui5.hana.ondemand.com/#/api/module:sap/ui/events/ControlEvents). If the respective event occurs at any position in the tree and the respective control implements the `on<eventName>` method, this method is invoked as if it had been registered with `jQuery.bind()`.

The event handler implementation requires less code, reduces the number of event handler registrations in the DOM and also reduces the number of event handler registrations and deregistrations that are executed on every rerendering action. On the other hand, this option is only available for specific events.

Example for registering the event handler directly:

``` js

MyControl.prototype.onclick = function(oEvent) {
   // do something...
}
```

OpenUI5 also provides so-called pseudo events. Pseudo events are semantically enriched and can be handled by just implementing an `on<eventName>` method. They **cannot** be used with `jQuery.bind()`. By using pseudo events, you avoid additional checks for modifier keys in the event handler or for certain keycodes. For a list of Pseudo Events, see [jQuery.sap.PseudoEvents](https://openui5.hana.ondemand.com/#docs/api/symbols/jQuery.sap.PseudoEvents.html).

