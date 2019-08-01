<!-- loioc75861e33942410d9ac77322763db203 -->

| loio |
| -----|
| c75861e33942410d9ac77322763db203 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/c75861e33942410d9ac77322763db203) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/c75861e33942410d9ac77322763db203)</div>

## Reacting on User Input Events

A handler can be used to validate, parse, and format issues.

You register the handler and can then use the following functions of `sap.ui.getCore()`:

-   `attachFormatError` 
-   `attachParseError`
-   `attachValidationError` 
-   `attachValidationSuccess` 

You can also register for these events directly on the control or any parent control where the event is fired. The corresponding event bubbles up to the Core if it is not canceled in the event handler.

**Related information**  


[Validation Messages](Validation_Messages_a90d93d.md)

