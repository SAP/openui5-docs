<!-- loio1a010d3b92c34226a96f202ec27e9217 -->

| loio |
| -----|
| 1a010d3b92c34226a96f202ec27e9217 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/1a010d3b92c34226a96f202ec27e9217) | [demo kit latest release](https://sdk.openui5.org/topic/1a010d3b92c34226a96f202ec27e9217)</div>

## Binding Events

The OData V4 model supports certain events intended for applications, and others that are to be used for controls, as outlined in this section.

***

### Events for Applications

For applications, the OData V4 model supports the following events:

-   The `dataRequested` and `dataReceived` events are typically used by applications to display and hide a busy indicator or to process a back-end error which happened when requesting data. The events are fired by `ODataPropertyBinding`, `ODataContextBinding` and `ODataListBinding` when reading data:

    -   The `dataRequested` event is fired directly after data has been requested from a back end.

    -   The `dataReceived` event is fired after the back-end data has been processed. Note that the `dataReceived` event is also fired after a back-end request has failed. The error of the failed request is passed to the event handler as an `error` parameter.


    For more details, see the corresponding API documentation for the specific bindings [ODataPropertyBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataPropertyBinding), [ODataContextBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding) and [ODataListBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding) in the Demo Kit.

-   The `createSent` and `createCompleted` events at the `ODataListBinding` are typically used by applications to lock the UI for the created entity to avoid modifications while the data for the created entity is sent to the back end, but the response from the back end is not yet processed on the client. For each `createSent` event, a `createCompleted` event is fired.

    -   The `createSent` event is fired each time a POST request that is triggered for an `ODataListBinding#create` is sent to the backend.

    -   The `createCompleted` event is fired each time the backend has responded to a POST request triggered for an `ODataListBinding#create`.


    For more information, see [`ODataListBinding#create`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding/methods/create).

-   The `patchSent` and `patchCompleted` events are typically used by applications that are using update groups with submit mode [Auto](https://sdk.openui5.org/api/sap.ui.model.odata.v4.SubmitMode) \(which is the default\) and which need to be informed when PATCH requests are sent to the back end and when they are processed. For example, these events can be used to display a `DraftIndicator` to inform the user that his changes are being saved and when saving is finished.

    The `patchSent` and `patchCompleted` events are fired by `ODataContextBinding` and `ODataListBinding` if they send their own service request:

    -   The `patchSent` event is fired when the first PATCH request for this binding is sent to the backend.

    -   The `patchCompleted` event is fired when the backend has responded to the last PATCH request for this binding.


    If `ODataContextBinding` and `ODataListBinding` use the service request of a superordinate binding, the events are fired by the superordinate binding.

    For more details, see the corresponding API documentation for the specific bindings [ODataContextBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding) and [ODataListBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding) in the Demo Kit.


***

### Events for Controls

The events `change` and `refresh` are meant for controls only, and not available for app development. They indicate that the respective binding has new data which can be accessed by the control:

-   When the binding is initialized, it fires a `change` event with the parameter `reason` set to `sap.ui.model.ChangeReason.Change`.

-   When a relative binding gets a new context, it fires a `change` event with the parameter `reason` set to `sap.ui.model.ChangeReason.Context`.

-   When a binding is refreshed, the event fired depends on the binding type, as follows:

    a\) `ODataPropertyBinding` and `ODataContextBinding` fire a `change` event with the parameter `reason` set to `sap.ui.model.ChangeReason.Refresh`.

    b\) `ODataListBinding` fires a `refresh` event.


For more details, see the corresponding API documentation for the specific bindings [ODataPropertyBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataPropertyBinding), [ODataContextBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding) and [ODataListBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding), as well as [sap.ui.model.ChangeReason](https://sdk.openui5.org/api/sap.ui.model.ChangeReason) in the Demo Kit.

**Related Information**  


[ODataPropertyBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataPropertyBinding)

[ODataContextBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding)

[ODataListBinding](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding)

[sap.ui.model.ChangeReason](https://sdk.openui5.org/api/sap.ui.model.ChangeReason)

