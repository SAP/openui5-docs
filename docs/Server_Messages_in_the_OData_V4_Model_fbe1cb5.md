<!-- loiofbe1cb5613cf4a40a841750bf813238e -->

| loio |
| -----|
| fbe1cb5613cf4a40a841750bf813238e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/fbe1cb5613cf4a40a841750bf813238e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/fbe1cb5613cf4a40a841750bf813238e)</div>

## Server Messages in the OData V4 Model

The OData V4 model supports server messages sent via an OData V4 service.

Messages transported via an OData V4 service response are parsed and reported to the message model `sap.ui.model.message.MessageModel`. An application can retrieve the messages \(`sap.ui.core.message.Message`\) and display them in a suitable control, for example in `sap.m.MessageView`. Server messages can be transported to the client over three different channels which are explained in detail in the following sections. The following table gives an overview how the OData message properties are mapped to the UI5 message:

|OData V4 Message

|UI5 Message

|Details

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>------------------</th>
			<th>-------------</th>
			<th>---------</th>
		</tr>
	</thead>
	<tbody>

			<td>`code`
			</td>
			<td>language-independent message code
			</td>
		</tr>
		<tr>
			<td>`message`
			</td>
			<td>`message`
			</td>
			<td>language-dependent message text
			</td>
		</tr>
		<tr>
			<td>`target`
			</td>
			<td>`target`
			</td>
			<td>-   path to the message target -   `target` and `additionalTargets` are both mapped to the `sap.ui.core.message.Message.target` collection
			</td>
		</tr>
		<tr>
			<td>`additionalTargets`\*
			</td>
		</tr>
		<tr>
			<td>`transition`
			</td>
			<td>`persistent`
			</td>
			<td>manages the message lifecycle
			</td>
		</tr>
		<tr>
			<td>`numericSeverity`\*
			</td>
			<td>`type`
			</td>
			<td>classification of end-user messages
			</td>
		</tr>
		<tr>
			<td>`longtextURL`\*
			</td>
			<td>`descriptionURL`
			</td>
			<td>a property of `Edm.String` type, which is nullable
			</td>
		</tr>
	</tbody>
</table>

\*\) In the error response this is represented by an instance annotation in the SAP Common vocabulary, [com.sap.vocabularies.Common.v1]()

End user messages contain the following information:

-   `code` - language-independent message code

-   `message`- language-dependent message text

-   `target` - path to the target of the message detail

-   `technicalDetails` - technical details of the message

-   `transition` - specifies a message as a state \(false\) or a transition message \(true\)

-   `numericSeverity` – classification of end user messages; allowed values: 1 \(success\), 2 \(info\), 3 \(warning\), 4 \(error\); `numericSeverity` is mapped to the specific `sap.ui.core.MessageType`

-   `longtextUrl` – optional; is omitted if there is no long text available for the corresponding message.


The use of the fields in specific cases is described in the sections below.

Messages can be either bound or unbound: Unbound messages are not related to OData entities and are therefore not part of the OData success response in the HTTP body. Bound messages are related to OData entities and are modeled as OData resources.

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

> Example:  
> Request URL: `http://<server>:<port>/serviceroot.svc/BusinessPartners(42)/to_Address; longtextUrl: "Messages(3)/LongText/$value"`
> 
> Result: `http://<server>:<port>/serviceroot.svc/BusinessPartners(42)/Messages(3)/LongText/$value`
> 
> Request URL: `http://<server>:<port>/serviceroot.svc/BusinessPartners(42); longtextUrl: "/Messages(3)/LongText/$value"`
> 
> Result: `http://<server>:<port>/Messages(3)/LongText/$value`

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_phx_wdz_5fb"/>

### Bound Messages

Bound messages are related to OData entities and are modeled as OData resources. An OData entity contains its bound messages as collection valued property of the complex type specified in the description of `com.sap.vocabularies.Common.v1.Messages`. Thus, bound messages are transported in the HTTP body. The target property specifies to which property the message is bound. The application needs to specify in the`$select` binding parameter whether messages should be returned by the server, or not.

``` js
  <ComplexType Name="<name of message type>">
      <Property Name="code" Type="Edm.String" Nullable="false" />
      <Property Name="message" Type="Edm.String" Nullable="false" />
      <Property Name="target" Type="Edm.String" Nullable="true" />
      <Property Name="additionalTargets" Type="Collection(Edm.String)" Nullable="false" />
      <Property Name="transition" Type="Edm.Boolean" Nullable="false" />
      <Property Name="numericSeverity" Type="Edm.Byte" Nullable="false" />
      <Property Name="longtextUrl" Type="Edm.String" Nullable="true" />
  </ComplexType>
```

The `target` property may contain a path relative to the entity which contains the message. The target can, for example, refer to a property within that entity. Further targets may be transported in the `additionalTargets` property. This information is used to highlight UI elements such as input fields if they are bound to properties referenced by a path contained in the `target` or `additionalTargets`properties. All responses are checked for bound messages. If there are messages, they are reported to the message model.

For bound messages, `longtextUrl` can be a relative or absolute path. Relative paths are treated as relative to the innermost context path \(`@odata.context`\) in the response, or to the request URL, if there is no context path. Absolute paths are treated as relative to the server.

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_fmj_dw2_nfb"/>

### Messages in Error Responses

Error messages are always reported in the error response in JSON format as described in the OData JSON Format Version 4.0 in section *19 Error Response* with the following additions:

-   The instance annotation `com.sap.vocabularies.Common.v1.longtextUrl` can be used to provide a long text URL, which can be a relative or an absolute path. Relative paths are treated as relative to the request URL. Absolute paths are treated as relative to the server.

-   `target` is relative to the requested resource.

-   `@com.sap.vocabularies.Common.v1.additionalTargets` is a list of additional targets relative to the requested resource.
-   The error message type is always `sap.ui.core.MessageType.Error`. The instance annotation `com.sap.vocabularies.Common.v1.numericSeverity` determines the message type of the detail messages.

-   The error message and all messages in details are transition messages.


A change set with multiple requests only has one error response. In this case, `target` alone is not sufficient to assign a message to a resource. The error must be assigned to one of the requests via the request's MIME header `Content-ID` first. The `Content-ID` has to be provided in the instance annotation `Org.OData.Core.V1.ContentID`.

> Example:  
> **Request**
> 
> ``` json
> --changeset_id-1612779902438-25
> Content-Type:application/http
> Content-ID:0.0
>  
> PATCH SalesOrderList('0500000005')/SO_2_SOITEM(SalesOrderID='0500000005',ItemPosition='0000000010')?custom-option=value HTTP/1.1
> Content-Type:application/json;charset=UTF-8;IEEE754Compatible=true
>  
> {"Quantity":"0","QuantityUnit":"EA"}
> --changeset_id-1612779902438-25
> Content-Type:application/http
> Content-ID:1.0
>  
> PATCH SalesOrderList('0500000005')/SO_2_SOITEM(SalesOrderID='0500000005',ItemPosition='0000000020')?custom-option=value HTTP/1.1
> Content-Type:application/json;charset=UTF-8;IEEE754Compatible=true
>  
> {"Quantity":"5","QuantityUnit":"EA"}
> --changeset_id-1612779902438-25--
> ```

> Example:  
> **Response**
> 
> ``` json
> {
>     "error": {
>         "message": "Value must be greater than 0",
>         "target": "Quantity",
>         "@com.sap.vocabularies.Common.v1.additionalTargets": ["ProductID"],
>         "@Org.OData.Core.V1.ContentID":"0.0"
>     }
> }
> ```

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

***

#### Combining State/Transition and Bound/Unbound Messages

| 

|State

|Transition

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>---</th>
			<th>-------</th>
			<th>------------</th>
		</tr>
	</thead>
	<tbody>

			<td>

![](loio38d78b4d740c43719a4eb8d80d4184e0_LowRes.png)
			</td>
			<td>

![](loio0d13ebb7aa8b4bf8b5c56acfa02653ef_LowRes.png)
			</td>
		</tr>
		<tr>
			<td>Bound
			</td>
			<td>

![](loio0d13ebb7aa8b4bf8b5c56acfa02653ef_LowRes.png)
			</td>
			<td>

![](loio0d13ebb7aa8b4bf8b5c56acfa02653ef_LowRes.png)
			</td>
		</tr>
	</tbody>
</table>

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_kxc_pp3_ffb"/>

### Message Severity

The table shows the supported severity values and their mapping to the specific `sap.ui.core.MessageType`.

|numericSeverity

|Type

|Comment

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>-----------------</th>
			<th>------</th>
			<th>---------</th>
		</tr>
	</thead>
	<tbody>

			<td>`sap.ui.core.MessageType.Success`
			</td>
			<td>Positive feedback - no action required
			</td>
		</tr>
		<tr>
			<td>2
			</td>
			<td>`sap.ui.core.MessageType.Information`
			</td>
			<td>Additional information - no action required
			</td>
		</tr>
		<tr>
			<td>3
			</td>
			<td>`sap.ui.core.MessageType.Warning`
			</td>
			<td>Warning - action may be required
			</td>
		</tr>
		<tr>
			<td>4
			</td>
			<td>`sap.ui.core.MessageType.Error`
			</td>
			<td>Error - action is required
			</td>
		</tr>
	</tbody>
</table>

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_jsd_vwk_33b"/>

### Accessing the Original Message

The attribute `technicalDetails.originalMessage` of the message in the message model allows you to access the original message from the back end.

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_httpStatus"/>

### Accessing the HTTP Status Code

The attribute `technicalDetails.httpStatus` of an error message in the message model provides the numerical HTTP status code of the corresponding back-end request that failed. In case of a 412 status code, additionally `technicalDetails.isConcurrentModification` is set to `true`, as in the case of  [sap.ui.model.odata.v4.Context\#delete](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/delete), which also uses this flag for the error instance that is used to reject its returned promise.

***

<a name="loiofbe1cb5613cf4a40a841750bf813238e__section_highlighting_table_rows"/>

### Highlighting Table Rows with Messages

To highlight table rows based on the criticality of the messages for that entity a formatter in controller code is needed. The `highlight` property of a table row is bound to the collection of messages in the message model and the entity displayed in the row. These binding parts are required to ensure that the formatter is called whenever a change occurs. The formatter itself calls the [`sap.ui.model.Context#getMessages`](https://openui5.hana.ondemand.com/#/api/sap.ui.model.Context/methods/getMessages) method, which returns the messages sorted by severity. The following code snippets demonstrate binding and formatter:

> Example:  
> Highlight a table row
> 
> ``` xml
> <!-- m.Table -->
> <Table items="{/SalesOrderList}">
>     <columns>
>         ...
>     </columns>
>     <ColumnListItem id="row">
>         ...
>     </ColumnListItem>
> </Table>
>  
> <!-- table.Table -->
> <table:Table rows="{/SalesOrderList}">
>     <table:rowSettingsTemplate>
>         <t:RowSettings id="row"/>
>     </t:rowSettingsTemplate>
> </table:Table>
> ```

Let `messageModel` be the named message model. A table row with messages can be highlighted with the following controller code:

> Example:  
> Formatter to highlight a table row
> 
> ``` js
> this.byId("row").bindProperty("highlight", {
>     formatter: function () {
>         var aMessages,
>             //formatter MUST be defined in a way that this is the control!
>             oRowContext = this.getBindingContext();
>  
>         if (oRowContext) { // formatter is called with oRowContext null initially
>             aMessages = oRowContext.getMessages();
>             return aMessages.length ? aMessages[0].type : sap.ui.core.MessageType.None;
>         }
>     },
>     parts: [
>         'messageModel>/',
>         { // ensure formatter is called on scrolling
>             mode: 'OneTime',
>             path: '',
>             targetType: 'any'
>         }
>     ]
> });
> ```

**Related Information**  


[https://github.com/SAP/odata-vocabularies/blob/master/vocabularies/Common.md]()

