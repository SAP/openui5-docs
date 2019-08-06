<!-- loiofbe1cb5613cf4a40a841750bf813238e -->

| loio |
| -----|
| fbe1cb5613cf4a40a841750bf813238e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/fbe1cb5613cf4a40a841750bf813238e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/fbe1cb5613cf4a40a841750bf813238e)</div>

## Server Messages in OData V4 Model

The OData V4 model supports server messages sent via an OData V4 service.

> Note:
> This feature is experimental. For more information, see [Compatibility Rules](Compatibility_Rules_91f0873.md).
> 
> 

Messages transported via an OData V4 service response are parsed and reported to the message model `sap.ui.model.message.MessageModel`. An application can retrieve the messages and display them in a suitable control, for example in `sap.m.MessageView`.

End user messages contain the following information:

-   `code` - language-independent message code

-   `message`- language-dependent message text

-   `target` - path to the target of the message detail

-   `technicalDetails` - technical details of the message

-   `transition` - specifies a message as a state \(false\) or a transition message \(true\)

-   `numericSeverity` – classification of end user messages; allowed values: 1 \(success\), 2 \(info\), 3 \(warning\), 4 \(error\); `numericSeverity` is mapped to the specific `sap.ui.core.MessageType`

-   `longtextUrl` – optional; is omitted, if there is no long text available for the corresponding message.


The use of the fields in specific cases is described in the sections below.

Messages can be either bound or unbound: Unbound messages are not related to OData entities and are, therefore, also not part of the OData success response in the HTTP body. Bound messages are related to OData entities and are modeled as OData resources.

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_jrv_5wm_2fb"/>

### Unbound Messages

Unbound messages are transported in the header field `sap-messages`, which is an array of messages. Unbound messages cannot be suppressed. They are always returned by the server and they always refer to the current request as described in the section about transition messages below. In case of successful requests, unbound messages are transported as an array in the HTTP header field `sap-messages`:

```
sap-messages:[
     {
          "code" : "SYS/42",
          "message" : "System will be down for maintenance next weekend.",
          "numericSeverity" : 2,
          "longtextUrl" : "Messages(3)/LongText/$value"
     }
]
```

> Note:
> `longtextUrl` can be a relative or absolute path. Relative paths are treated as relative to the request URL. Absolute paths are treated as relative to the server.
> 
> 

> Note:
> Request URL: `http://<server>:<port>/serviceroot.svc/BusinessPartners(42)/to_Address; longtextUrl: "Messages(3)/LongText/$value"`
> 
> Result: `http://<server>:<port>/serviceroot.svc/BusinessPartners(42)/Messages(3)/LongText/$value`
> 
> Request URL: `http://<server>:<port>/serviceroot.svc/BusinessPartners(42); longtextUrl: "/Messages(3)/LongText/$value"`
> 
> Result: `http://<server>:<port>/Messages(3)/LongText/$value`
> 
> 

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_phx_wdz_5fb"/>

### Bound Messages

Bound messages are related to OData entities and are modeled as OData resources. An OData entity contains its bound messages as collection valued property of the complex type specified in the description of `com.sap.vocabularies.Common.v1.Messages`. Thus, bound messages are transported in the HTTP body. The target property specifies to which property the message is bound. The application needs to specify in the`$select` binding parameter whether messages should be returned by the server, or not.

``` js
1  <ComplexType Name="<name of message type>">
2      <Property Name="code" Type="Edm.String" Nullable="false" />
3      <Property Name="message" Type="Edm.String" Nullable="false" />
4      <Property Name="target" Type="Edm.String" Nullable="true" />
5      <Property Name="transition" Type="Edm.Boolean" Nullable="false" />
6      <Property Name="numericSeverity" Type="Edm.Byte" Nullable="false" />
7      <Property Name="longtextUrl" Type="Edm.String" Nullable="true" />
8  </ComplexType>
```

The `target` property may contain a path relative to the entity which contains the message. The target can, for example, refer to a property within that entity. This information is used to highlight UI elements such as input fields, if they are bound to properties referenced by the path contained in the `target` property. All responses are checked for bound messages. If there are messages, they are reported to the message model.

For bound messages, `longtextUrl` can be a relative or absolute path. Relative paths are treated as relative to the innermost context path \(`@odata.context`\) in the response, or to the request URL, if there is no context path. Absolute paths are treated as relative to the server.

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_fmj_dw2_nfb"/>

### Messages in Error Responses

Error messages are always reported in the error response in JSON format as described in the OData JSON Format Version 4.0 in section *19 Error Response* with the following additions:

-   The instance annotation `com.sap.vocabularies.Common.v1.longtextUrl` can be used to provide a long text URL, which can be a relative or an absolute path. Relative paths are treated as relative to the request URL. Absolute paths are treated as relative to the server.

-   `target` is relative to the requested resource.

-   The error message type is always `sap.ui.core.MessageType.Error`. The instance annotation `com.sap.vocabularies.Common.v1.numericSeverity` determines the message type of the detail messages.

-   The error message and all messages in details are transition messages.


***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_lnt_hym_2fb"/>

### State Messages and Transition Messages

Messages can be either state or transition messages:

-   State messages refer to the state of the corresponding resource \(OData entity instance\). State messages are valid as long as the related business object is not changed. The OData V4 Model is responsible for the lifecycle of state messages and will remove state messages from the message model, if they are no longer sent by the server when the corresponding resource is requested.

-   Transition messages refer to the current request and are not related to the state of a resource. They are only relevant for the request that was triggered, for example *System not available, business object could not be updated*. Optionally, transition messages can reference a business object, for example *Shipping address could not be changed due to missing authorization*. Transition messages are translated into persistent messages in the message model. The application is responsible for the lifecycle of such persistent messages. The OData V4 Model will not remove persistent messages from the message model.


***

#### Lifecycle Management for State Messages

The lifecycle management for state messages is optimized for a specific orchestration with the server. When bound messages are requested, the OData V4 server returns all bound messages for the respective entity and its subentities within the same business object. The business object is defined by the first path segment.

The following example uses a sales order with items and related products:

-   A `GET` request for `/SalesOrder(´0815´)` returns all bound messages for the sales order and the items, even if the items themselves are not contained in the response. Messages to assigned products, business partners, and so on, that are not part of the `SalesOrder` business object will **not** be sent if the path starts within the `SalesOrder` business object.

-   A `GET` request for a specific item with path `/SalesOrder(´0815´)/_Items(´010´)` returns all bound messages for this item.

-   A `GET` request for the product related to an item using the deep path `/SalesOrder(´0815´)/_Items(´010´)/_Product` will not return any bound messages.


The OData V4 model checks whether the response contains the message property and removes all previous bound state messages from the message model, if their target path starts with the path of the entity.

This concept has the following consequences:

-   When you display the information for the business object itself, you can also display the messages for all subentities of this business object.

-   For displaying the entities within a business object, an application has to use deep paths, instead of canonical paths. Otherwise, messages will appear twice. In the object page of item `´010´`, for example, the binding needs to use the path `/SalesOrder(´0815´)/_Items(´010´)`. You can achieve this also with a relative binding using the context of the sales order.

-   Binding entities outside the business object with the deep path means that no messages will be retrieved for this entity. Using the binding `/SalesOrder(´0815´)/_Items(´010´)/_Product` to display product information of item `010`, for example, will not return any product-specific bound message.

-   As a consequence, it must also **not** be possible to change the entity that is bound with a path that starts with a different business object. If, for example, product information needs to be changed, we recommended to use the canonical path to bind the product assigned to item `010` to achieve that the server sends the bound messages of the product.


> Note:
> The OpenUI5 V4 ODataModel is agnostic to business objects. The application needs to take care of the proper setup.
> 
> 

***

#### Combining State/Transition and Bound/Unbound Messages

| |State|Transition|
|--|-----|----------|
|Unbound|![](loio38d78b4d740c43719a4eb8d80d4184e0_LowRes.png)|![](loio0d13ebb7aa8b4bf8b5c56acfa02653ef_LowRes.png)|
|Bound|![](loio0d13ebb7aa8b4bf8b5c56acfa02653ef_LowRes.png)|![](loio0d13ebb7aa8b4bf8b5c56acfa02653ef_LowRes.png)|

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_kxc_pp3_ffb"/>

### Message Severity

The table shows the supported severity values and their mapping to the specific `sap.ui.core.MessageType`.

|numericSeverity|Type|Comment|
|---------------|----|-------|
|1|`sap.ui.core.MessageType.Success`|Positive feedback - no action required|
|2|`sap.ui.core.MessageType.Information`|Additional information - no action required|
|3|`sap.ui.core.MessageType.Warning`|Warning - action may be required|
|4|`sap.ui.core.MessageType.Error`|Error - action is required|

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_jsd_vwk_33b"/>

### Accessing the Original Message

The attribute `technicalDetails.originalMessage` of the message in the message model allows you to access the original message from the back-end.

**Related information**  


[https://wiki.scn.sap.com/wiki/display/EmTech/OData+4.0+Vocabularies+-+SAP+Common](https://wiki.scn.sap.com/wiki/display/EmTech/OData+4.0+Vocabularies+-+SAP+Common)

