<!-- loio8956f0a223284d729900ebad4ca88356 -->

| loio |
| -----|
| 8956f0a223284d729900ebad4ca88356 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8956f0a223284d729900ebad4ca88356) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8956f0a223284d729900ebad4ca88356)</div>

## Message Model

The message model contains all messages and is used to bind to the messages to display them.

The message model is retrieved from the message manager by calling the `getMessageModel()` method. You can use it directly in the application, or you can use it as a reference implementation.

***

### Using the Message Model

You use the message model like any other model to bind an aggregation to a root path \("/\), for example the items in a list, and add filters and sorters. The `MessagePopover` control is used to display the messages to the user:

```
// "Button" required from "sap/m/Button"
// "MessagePopover" required from "sap/m/MessagePopover"
// "MessagePopoverItem" required from "sap/m/MessagePopoverItem"

var oMessagePopoverButton = new Button({
    text: "Show MessagePopover",
    type: "Accept",
    press: function() {
        oMP.openBy(this);
    }
});

var oMP = new MessagePopover({
    items: {
        path:"message>/",
        template: new MessagePopoverItem({ description: "{message>description}", type: "{message>type}", title: "{message>message}"})
    }
});

oMP.setModel (sap.ui.getCore().getMessageManager().getMessageModel(),"message");

oMessagePopoverButton.placeAt("content");
```

> Note:
> For an example how to bind to the message model and show the messages to the user, see `sap.m.MessagePopover` in the API reference.
> 
> 

**Related information**  


[API Reference: `sap.ui.model.message.MessageModel`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.message.MessageModel.html)

[API Reference: `sap.ui.core.message.MessageManager`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.message.MessageManager.html)

[API Reference: `sap.ui.core.message.MessagePopover`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.message.MessagePopover.html)

