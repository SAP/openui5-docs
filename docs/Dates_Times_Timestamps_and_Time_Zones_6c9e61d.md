<!-- loio6c9e61dc157a40c19460660ece8368bc -->

| loio |
| -----|
| 6c9e61dc157a40c19460660ece8368bc |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/6c9e61dc157a40c19460660ece8368bc) | [demo kit latest release](https://sdk.openui5.org/topic/6c9e61dc157a40c19460660ece8368bc)</div>

## Dates, Times, Timestamps and Time Zones

OpenUI5 applications often deal with timestamps, dates and times. Typically, these timestamps, dates and times are stored in a back-end system and communicated to the client via OData services. OpenUI5 offers a variety of UI5 data types and formatters for handling these timestamps, dates and times.

When talking about dates, times, or timestamps, we'll use the following definitions:

-   A **date** is a representation of a specific day within a year that is independent of any time zone. For example, Sylvester 2022 is on 2022/12/31, regardless of the time zone in which the user is in. The time zone is irrelevant for dates.
-   A **time** is a representation of a specific hour/minute/second within a day that is independent of any time zone. For example, if all shops of a brand open at 9:00 AM, they will open at 9:00 AM in whichever time zone the customer is in. The time zone is irrelevant for times.
-   A **timestamp** represents a point in time that can be displayed or edited in specific time zones. For example, if a meeting starts at a specific date and a specific time in a specific time zone, its timestamp may be displayed as `27.11.2022, 14:00:00 Honolulu` or as `28.11.2022, 11:00:00 Australia/Canberra`, depending on the user's time zone.

The intermediate processing of these entities on the client side typically uses the JavaScript `Date` object, which represents a timestamp. This may cause issues if dates are used and time zone handling comes into play. Typically, timestamps are displayed in the time zone of the browser. It is also possible to display a timestamp in a different time zone, for example in the `America/New_York` time zone, by using  [ `sap.ui.model.odata.type.DateTimeWithTimezone`](https://sdk.openui5.org/api/sap.ui.model.odata.type.DateTimeWithTimezone) or [ `sap.ui.core.format.DateFormat.getDateTimeWithTimezoneInstance`](https://sdk.openui5.org/api/sap.ui.core.format.DateFormat.getDateTimeWithTimezoneInstance).

For testing purposes, you can use the `sap-timezone` URL parameter to switch from the browser time zone to any provided time zone. For example, with `?sap-timezone= Pacific/Honolulu` the Honolulu time zone \(GMT-10:00\), or with `?sap-timezone= Pacific/Fiji` the Fiji time zone \(GMT+12:00\) is used for formatting and parsing timestamps, except for the timestamps that are formatted or parsed with  [ `sap.ui.model.odata.type.DateTimeWithTimezone`](https://sdk.openui5.org/api/sap.ui.model.odata.type.DateTimeWithTimezone) or [ `sap.ui.core.format.DateFormat.getDateTimeWithTimezoneInstance`](https://sdk.openui5.org/api/sap.ui.core.format.DateFormat.getDateTimeWithTimezoneInstance).

> ### Restriction:  
> If you use a configured time zone, **your application may break** if it uses JavaScript `Date` objects in combination with `oDate.getHours()` or `oDate.getDate()`. To avoid such issues, we urge you to use data binding with the corresponding OpenUI5 OData data types wherever possible in your application.

This topic describes the different OData Edm types and the corresponding OpenUI5 data type, how to display timestamps in a specific time zone, a list of best practices for handling timestamps, dates, and times in OpenUI5, and a list of common pitfalls.

***

<a name="loio6c9e61dc157a40c19460660ece8368bc__section_nrw_4x3_dwb"/>

### Timestamps, Dates and Times in OData

OData provides different Edm types for handling timestamps, dates, and times. For these Edm types, OpenUI5 provides corresponding OpenUI5 data types to be used with data binding for formatting and parsing timestamps, dates and times. The following table shows whichOpenUI5 data type belongs to which Edm type, and which meaning these types have:


<table>
<tr>
<th valign="top" align="center">

OData V4 Message



</th>
<th valign="top" align="center">

UI5 Message



</th>
<th valign="top" align="center">

Details



</th>
</tr>
<tr>
<td valign="top">

`code`



</td>
<td valign="top">

`code`



</td>
<td valign="top">

language-independent message code



</td>
</tr>
<tr>
<td valign="top">

`message`



</td>
<td valign="top">

`message`



</td>
<td valign="top">

language-dependent message text



</td>
</tr>
<tr>
<td valign="top">

`target`



</td>
<td valign="top" rowspan="2">

`target`



</td>
<td valign="top" rowspan="2">

-   path to the message target
-   `target` and `additionalTargets` are both mapped to the transition message \(true\)`sap.ui.core.message.Message.target` collection



</td>
</tr>
<tr>
<td valign="top">

`additionalTargets`\*



</td>
</tr>
<tr>
<td valign="top">

`transition`



</td>
<td valign="top">

`persistent`



</td>
<td valign="top">

manages the message lifecycle



</td>
</tr>
<tr>
<td valign="top">

`numericSeverity`\*



</td>
<td valign="top">

`type`



</td>
<td valign="top">

classification of end-user messages



</td>
</tr>
<tr>
<td valign="top">

`longtextURL`\*



</td>
<td valign="top">

`descriptionURL`



</td>
<td valign="top">

a property of `Edm.String` type, which is nullable



</td>
</tr>
</table>

\*\) In the error response this is represented by an instance annotation in the SAP Common vocabulary, [com.sap.vocabularies.Common.v1](https://github.com/SAP/odata-vocabularies/blob/master/vocabularies/Common.md)

End user messages contain the following information:

-   `code` - language-independent message code

-   `message`- language-dependent message text

-   `target` - path to the target of the message detail

-   `technicalDetails` - technical details of the message

-   `transition`

-   `numericSeverity` - specifies a m – classification of end user messages; allowed values: 1 \(success\), 2 \(info\), 3 \(warning\), 4 \(error\); `numericSeverity` is mapped to the specific `sap.ui.core.MessageType`

-   `longtextUrl` – optional; is omitted if there is no long text available for the corresponding message.


The use of the fields in specific cases is described in the sections below.

***

<a name="loio6c9e61dc157a40c19460660ece8368bc__section_jrv_5wm_2fb"/>

### Displaying Timestamps in a Specific Time Zone

Messages are classified by two different categories: bound/unbound and state/transition.

***

#### Bound and unbound messages

Messages are either bound or unbound: Bound messages are related to OData entities, whereas unbound messages are not related to OData entities. Unbound messages are identified by a missing, i.e. undefined, target in the OData V4 message. This is translated into an empty string in the UI5 message.

***

#### State and transition messages

Messages are either state or transition messages:

-   State messages refer to the state of the corresponding resource \(OData entity instance\). State messages are valid as long as the related business object is not changed. The OData V4 model handles the lifecycle of state messages and will remove state messages from the message model once they are no longer sent by the server when the corresponding resource is requested. For more information, see [Lifecycle Management for State Messages](Server_Messages_in_the_OData_V4_Model_fbe1cb5.md#loiofbe1cb5613cf4a40a841750bf813238e__section_LMFSM).

-   Transition messages refer to the current request and are not related to the state of a resource. They are only relevant for the request that was triggered, for example *System not available, business object could not be updated*. Optionally, transition messages can reference a business object, for example *Shipping address could not be changed due to missing authorization*. Transition messages are translated into persistent messages in the message model. The application is responsible for the handling of the lifecycle of such persistent messages. The OData V4 model will not remove persistent messages from the message model.


***

#### Combining state/transition and bound/unbound messages

Three different types of messages result from the possible combinations of the state/transition and bound/unbound categories. There cannot be unbound messages referring to the state of an OData entity.


<table>
<tr>
<th valign="top">

 



</th>
<th valign="top">

State



</th>
<th valign="top">

Transition



</th>
</tr>
<tr>
<td valign="top">

Unbound



</td>
<td valign="top">

![](images/loio38d78b4d740c43719a4eb8d80d4184e0_LowRes.png)



</td>
<td valign="top">

![](images/loio0d13ebb7aa8b4bf8b5c56acfa02653ef_LowRes.png)



</td>
</tr>
<tr>
<td valign="top">

Bound



</td>
<td valign="top">

![](images/loio0d13ebb7aa8b4bf8b5c56acfa02653ef_LowRes.png)



</td>
<td valign="top">

![](images/loio0d13ebb7aa8b4bf8b5c56acfa02653ef_LowRes.png)



</td>
</tr>
</table>

***

<a name="loio6c9e61dc157a40c19460660ece8368bc__section_phx_wdz_5fb"/>

### Best Practices

There are three different channels for transporting messages to the client:

1.  The error response for transporting unbound and bound transition messages in the error case.

2.  The `sap-messages` header for transporting unbound and bound transition messages in the success case.

3.  The `message` property as part of the entity for transporting bound state and transition messages in the success case.


> ### Note:  
> In the success case, a bound transition message can either be transported in the `sap-messages` header or in the `message` property. A message sent in the `sap-messages` header must not be repeated in the `message` property, and vice versa.

***

#### `sap.m.DatePicker` with `Edm.Date` or `Edm.DateTime`

Only transition messages are transported in the error response. The messages may be bound or unbound. Error messages are always reported in the error response in JSON format, as described in the OData JSON Format Version 4.0 in Section *19 Error Response*, with the following additions:

-   The instance annotation `com.sap.vocabularies.Common.v1.longtextUrl` can be used to provide a long text URL, which can be a relative or an absolute path. Relative paths are treated as relative to the request URL. Absolute paths are treated as relative to the server.

-   `target` is relative to the requested resource.

-   `@com.sap.vocabularies.Common.v1.additionalTargets` is a list of additional targets relative to the requested resource.
-   The error message type is always `sap.ui.core.MessageType.Error`. The instance annotation `com.sap.vocabularies.Common.v1.numericSeverity` determines the message type of the detail messages.


A change set with multiple requests only has one error response. In this case, `target` alone is not sufficient to assign a message to a resource. The error must be assigned to one of the requests via the request's MIME header `Content-ID` first. The `Content-ID` has to be provided in the instance annotation `Org.OData.Core.V1.ContentID`.

> ### Example:  
> **Request**
> 
> ```json
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

> ### Example:  
> **Response**
> 
> ```json
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

#### `sap.m.TimePicker` with `Edm.TimeOfDay` or `Edm.Time`

The response of a successful request may contain messages in the `sap-messages` header. Only transition messages are transported in the `sap-messages` header. These messages may be bound or unbound. The `sap-messages` header contains an array of objects that can include:

-   A machine-readable `code`,
-   a human-readable, language-dependent `message`,
-   a `numericSeverity`,
-   an optional `longtextUrl`,
-   an optional `target`,
-   an optional array of `additionalTargets` if the message applies to two or more fields. Each item in this array is a string with the same syntax as `target`.

```
sap-messages:[
     {
          "code" : "0815",
          "message" : "Delivery date is in the past",
          "numericSeverity" : 3
          "longtextUrl" : "Messages(3)/LongText/$value",
          "target" : "DeliveryDate"
     }
]
```

> ### Note:  
> `longtextUrl` can be a relative or absolute path. Relative paths are treated as relative to the request URL. Absolute paths are treated as relative to the server.

> ### Example:  
> Request URL: `http://<server>:<port>/serviceroot.svc/BusinessPartners(42)/to_Address; longtextUrl: "Messages(3)/LongText/$value"`
> 
> Result: `http://<server>:<port>/serviceroot.svc/BusinessPartners(42)/Messages(3)/LongText/$value`
> 
> Request URL: `http://<server>:<port>/serviceroot.svc/BusinessPartners(42); longtextUrl: "/Messages(3)/LongText/$value"`
> 
> Result: `http://<server>:<port>/Messages(3)/LongText/$value`

***

#### `sap.m.DateTimePicker` with `Edm.DateTimeOffset`

Bound messages may also be transported as a part of the OData entity to which they belong. These messages may be transition or state messages. The OData entity contains its bound messages as collection-valued property of the complex type specified in the description of `com.sap.vocabularies.Common.v1.Messages`. The `target` property specifies to which property the message is bound. The application needs to specify in the`$select` binding parameter whether messages should be returned by the server.

```js
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

The `target` property may contain a path relative to the entity which contains the message. The target can, for example, refer to a property within that entity. Further targets may be transported in the `additionalTargets` property. This information is used to highlight UI elements such as input fields if they are bound to properties referenced by a path contained in the `target` or `additionalTargets` properties. All responses are checked for bound messages. If there are messages, they are reported to the message model.

> ### Note:  
> Highlighting of an input field only works if the resolved message target and the binding path of the control are identical. In addition to the OData 4.0 specification, the model normalizes the message targets following these rules:
> 
> -   Key properties are ordered just as in the metadata,
> -   for single key properties, the name of the key is omitted,
> -   for collection-valued navigation properties, all keys are present,
> -   the values are encoded via `encodeURIComponent`.

For bound messages, `longtextUrl` can be a relative or absolute path. Relative paths are treated as relative to the innermost context path \(`@odata.context`\) in the response, or to the request URL if there is no context path. Absolute paths are treated as relative to the server.

***

#### `sap.m.DateRangeSelection` with `Edm.Date` or `Edm.DateTime`

***

<a name="loio6c9e61dc157a40c19460660ece8368bc__section_CP"/>

### Common Pitfalls

***

#### Controls are used with JavaScript `Date` objects

***

#### Unexpected type in `$metadata` document

The lifecycle management for state messages is optimized for a specific orchestration with the server. When a message is requested, the OData V4 server returns all bound messages for the respective entity and its subentities within the same business object. The business object is defined by the first path segment.

The following example uses a sales order with items and related products:

-   A `GET` request for `/SalesOrder(´0815´)` returns all bound messages for the sales order and its items, even if the items themselves are not contained in the response. Messages to assigned products, business partners, and so on, that are not part of the `SalesOrder` business object will **not** be sent if the path starts within the `SalesOrder` business object.

-   A `GET` request for a specific item with path `/SalesOrder(´0815´)/_Items(´010´)` returns all bound messages for this item.

-   A `GET` request for the product related to an item using the deep path `/SalesOrder(´0815´)/_Items(´010´)/_Product` will not return any bound messages.


The OData V4 model checks whether the response contains the message property and removes all previous bound state messages from the message model if their target paths start with the path of the entity.

This concept has the following consequences:

-   When you display the information for the business object itself, you can also display the messages for all subentities of this business object.

-   For displaying the entities within a business object, an application has to use deep paths instead of canonical paths; otherwise, messages will appear twice. In the object page of item `´010´`, for example, the binding needs to use the path `/SalesOrder(´0815´)/_Items(´010´)`. You can also achieve this with a relative binding using the context of the sales order.

-   Binding entities outside the business object with the deep path means that no messages will be retrieved for this entity. Using the binding `/SalesOrder(´0815´)/_Items(´010´)/_Product` to display product information of item `010`, for example, will not return any product-specific bound message.

-   As a consequence, it must also **not** be possible to change the entity that is bound with a path that starts with a different business object. If, for example, product information needs to be changed, we recommended to use the canonical path to bind the product assigned to item `010` to achieve that the server sends the bound messages of the product.


> ### Note:  
> The OpenUI5 V4 ODataModel is agnostic to business objects. The application needs to take care of the proper setup.

