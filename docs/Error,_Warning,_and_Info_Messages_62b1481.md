<!-- loio62b1481d3e084cb49dd30956d183c6a0 -->

| loio |
| -----|
| 62b1481d3e084cb49dd30956d183c6a0 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/62b1481d3e084cb49dd30956d183c6a0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/62b1481d3e084cb49dd30956d183c6a0)</div>

## Error, Warning, and Info Messages

 OpenUI5 provides a central place for storing and managing info, warning, and error messages.

Messages can be used to notify the user about specific states of the application and can help the user to correct their incorrect inputs. The central `MessageManager` for storing messages is available globally by calling `sap.ui.getCore().getMessageManager()` and the central `MessageModel` for managing messages is available by calling `sap.ui.getCore().getMessageManager().getMessageModel()`.

***

<a name="loio62b1481d3e084cb49dd30956d183c6a0__section_xkx_xr3_rhb"/>

### Message Object Properties

The following properties of `sap.ui.core.message.Message` instances are important:

-   Target: Describes the part of the application to which the message applies. If the target is empty, the message applies to the entire application. The target format depends on the used message processor. Currently,OpenUI5 supports two types of targets:

    -   Control IDs with control properties: The `sap.ui.core.message.ControlMessageProcessor` propagates these messages to the affected control.

    -   Binding path: The `sap.ui.model.Model` propagates these messages to affected bindings.

-   Message processor: The object that handles the message in the application and propagates the message to correct controls, bindings, or other objects, see `sap.ui.core.message.ControlMessageProcessor` in the API reference.

-   Type: Defines the severity of the message; possible types are: error, warning, info, and success, see `sap.ui.core.MessageType` in the API reference.

-   Message text: The actual message text describing the issue. This text is shown to the user.

-   Persistent: This property influences the lifecycle of the message. Non-persistent messages are cleaned up by the framework messaging lifecycle, persistent messages have to be removed manually by the application.


***

<a name="loio62b1481d3e084cb49dd30956d183c6a0__section_fjj_1s3_rhb"/>

### Message Creation

There are several ways to create messages automatically and push them into the central message model:

-   Validation messages refer to a control. They are created by the OpenUI5 framework when data is parsed, formatted, and validated according to defined data types, see [Formatting, Parsing, and Validating Data](Formatting,_Parsing,_and_Validating_Data_07e4b92.md). Such messages are propagated to one specific control. For more information, see [Validation Messages](Validation_Messages_a90d93d.md).

-   OData V2 messages refer to a binding path. They are typically managed by the server and are changed every time the back end responds to a request. Such messages are propagated to all bindings with the specific binding path. For more information, see [OData V2 Messages](OData_V2_Messages_81c735e.md).


You can also create messages manually or extend the messaging features provided by the framework:

-   You can create custom messages manually via the central `sap.ui.core.message.MessageManager` APIs. For these manually created messages, the application has to ensure a proper message lifecycle.

-   For custom target formats, you can use the custom message processor. The own message processor has to inherit from the class `sap.ui.core.message.MessageProcessor`.

-   If the used back end serves messages in a special way, you can use your own implementation of `sap.ui.core.message.MessageParser`. For more information, see [Implementing Your Own OData V2 Message Parser](Implementing_Your_Own_OData_V2_Message_Parser_2e532e6.md).


**Related information**  


[API Reference: `sap.ui.core.message.Message`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.message.Message.html)

[API Reference: `sap.ui.core.MessageType`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.MessageType.html)

[API Reference: `sap.ui.core.message.MessageManager`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.message.MessageManager.html)

[API Reference: `sap.ui.model.message.MessageModel`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.message.MessageModel.html)

[API Reference: `sap.ui.core.message.MessageParser`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.message.MessageParser.html)

[API Reference: `sap.ui.core.message.MessageProcessor`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.message.MessageProcessor.html)

[API Reference: `sap.ui.core.message.ControlMessageProcessor`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.message.ControlMessageProcessor.html)

[API Reference: `sap.ui.model.Model`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.Model.html)

