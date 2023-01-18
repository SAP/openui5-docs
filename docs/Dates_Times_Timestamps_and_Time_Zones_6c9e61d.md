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
> If you use a configured time zone, **your application may break** if it uses JavaScript `Date` objects in combination with `oDate.getHours()` or `oDate.getDate()`. To avoid such issues, we recommend to use data binding with the corresponding OpenUI5 OData types wherever possible in your application.

This topic describes the different OData Edm types and the corresponding OpenUI5 data type, how to display timestamps in a specific time zone, a list of best practices for handling timestamps, dates, and times in OpenUI5, and a list of common pitfalls.

***

<a name="loio6c9e61dc157a40c19460660ece8368bc__section_nrw_4x3_dwb"/>

### Timestamps, Dates and Times in OData

OData provides different Edm types for handling timestamps, dates, and times. For these Edm types, OpenUI5 provides corresponding [OpenUI5 data types](Formatting_Parsing_and_Validating_Data_07e4b92.md) to be used with data binding for formatting and parsing timestamps, dates and times. The following table shows whichOpenUI5 data type belongs to which Edm type, and which meaning these types have:


<table>
<tr>
<th valign="top">

Edm Type



</th>
<th valign="top">

Transported as \(in JSON Format\)



</th>
<th valign="top">

Model Representation



</th>
<th valign="top">

OpenUI5 Type



</th>
<th valign="top">

Meaning



</th>
</tr>
<tr>
<td valign="top" colspan="5">

**OData V4 Edm Types**



</td>
</tr>
<tr>
<td valign="top">

`Edm.Date`



</td>
<td valign="top">

"Date" : "2014-03-25"



</td>
<td valign="top">

String



</td>
<td valign="top">

 [ `sap.ui.model.odata.type.Date`](https://sdk.openui5.org/api/sap.ui.model.odata.type.Date)



</td>
<td valign="top">

A **date** as defined above.



</td>
</tr>
<tr>
<td valign="top">

`Edm.DateTimeOffset`



</td>
<td valign="top">

"DateTimeOffset" : "2015-01-06T07:25:21Z"



</td>
<td valign="top">

String



</td>
<td valign="top">

 [ `sap.ui.model.odata.type.DateTimeOffset`](https://sdk.openui5.org/api/sap.ui.model.odata.type.DateTimeOffset)



</td>
<td valign="top">

A **timestamp** as defined above.



</td>
</tr>
<tr>
<td valign="top">

`Edm.TimeOfDay`



</td>
<td valign="top">

"TimeOfDay" : "07:25:21"



</td>
<td valign="top">

String



</td>
<td valign="top">

 [ `sap.ui.model.odata.type.TimeOfDay`](https://sdk.openui5.org/api/sap.ui.model.odata.type.TimeOfDay)



</td>
<td valign="top">

A **time** as defined above.



</td>
</tr>
<tr>
<td valign="top" colspan="5">

**OData V2 Edm Types**



</td>
</tr>
<tr>
<td valign="top">

`Edm.DateTime`



</td>
<td valign="top">

"DateTime" : "\\/Date\(1395752399000\)\\/"



</td>
<td valign="top">

JavaScript Date



</td>
<td valign="top">

 [ `sap.ui.model.odata.type.DateTime`](https://sdk.openui5.org/api/sap.ui.model.odata.type.DateTime) with constraint`displayFormat: "Date"`



</td>
<td valign="top">

A **date** as defined above if the property/parameter is annotated with `sap:display-format="Date"`. Using this type as a **timestamp** is not recommended; use `Edm.DateTimeOffset` instead.



</td>
</tr>
<tr>
<td valign="top">

`Edm.DateTimeOffset`



</td>
<td valign="top">

"DateTimeOffset" : "\\/Date\(1420529121547+0000\)\\/"



</td>
<td valign="top">

JavaScript Date



</td>
<td valign="top">

 [ `sap.ui.model.odata.type.DateTimeOffset`](https://sdk.openui5.org/api/sap.ui.model.odata.type.DateTimeOffset)



</td>
<td valign="top">

A **timestamp** as defined above.



</td>
</tr>
<tr>
<td valign="top">

`Edm.Time`



</td>
<td valign="top">

"Time" : "PT11H33M55S"



</td>
<td valign="top">

\{ ms : 41635000 , \_\_edmType : 'Edm.Time' \}



</td>
<td valign="top">

 [ `sap.ui.model.odata.type.Time`](https://sdk.openui5.org/api/sap.ui.model.odata.type.Time)



</td>
<td valign="top">

A **time** as defined above.



</td>
</tr>
</table>


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

Timestamps are always transported between client and server in UTC \(Coordinated Universal Time\), but on the UI they are displayed in the user's time zone, i.e. the time zone used by the browser which is configured in the operating system. The UTC offset \("Z" in OData V4, or "+0000" in OData V2 in the examples above\) is neither used to determine a time zone on the client nor to transport time zone information from the client to the back end.

Dates and times are time zone-independent, so OData V4 uses strings like "2014-03-25" or "07:25:21" for transporting dates and times between server and client, and for storing the values in the OData model. In OData V2, however, there is no specific data type for dates. There is an `sap:display-format="Date"` annotation at an OData property/parameter having the Edm type `DateTime`, which means that the given timestamp has to be interpreted as a date. The  [ `sap.ui.model.odata.type.DateTime`](https://sdk.openui5.org/api/sap.ui.model.odata.type.DateTime) with the constraint `sap:display-format="Date"` uses UTC to extract the date information from a timestamp.

***

<a name="loio6c9e61dc157a40c19460660ece8368bc__section_jrv_5wm_2fb"/>

### Displaying Timestamps in a Specific Time Zone

Displaying timestamps in a specific time zone provided by the back end is done using the composite type  [ `sap.ui.model.odata.type.DateTimeWithTimezone`](https://sdk.openui5.org/api/sap.ui.model.odata.type.DateTimeWithTimezone). The first part of the composite binding contains the timestamp and an `Edm.DateTimeOffset`, and the second part contains the IANA time zone ID.

***

<a name="loio6c9e61dc157a40c19460660ece8368bc__section_phx_wdz_5fb"/>

### Best Practices

**Use data binding with the corresponding OData types against the string-based property \(`value`\) of the control** used to display the date, time, timestamp, or a date range.

JSON models can also be used if the data is stored in the JSON model in the same way as in the corresponding OData model. If you already have the values in an OData model, you can transfer them to a JSON model. Dates, times and timestamps in the OData V2 model are stored as objects, so take care to clone these objects before transferring the values to a JSON model.

If an OData V4 model is used, cloning is not necessary, as the model representation of dates, times, and timestamps is a string.

When binding an OData V4 property via an OData V4 model, type information is automatically determined, and there is no need to specify a type in the binding information. If you bind an OData V4 property via a JSON model, however, you have to specify the types.

***

#### `sap.m.DatePicker` with `Edm.Date` or `Edm.DateTime`

Only transition messages are transported in the error response. The messages may be bound or unbound. Error messages are always reported in the error response in JSON format, as described in the OData JSON Format Version 4.0 in Section *19 Error Response*, with the following additions:

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

For bound messages, `longtextUrl` can be a relative or absolute path. Relative paths are treated as relative to the innermost context path \(`@odata.context`\) in the response, or to the request URL if there is no context path. Absolute paths are treated as relative to the server.

***

#### `sap.m.DateRangeSelection` with `Edm.Date` or `Edm.DateTime`

With a `DateRangeSelection` control, the user can select two dates, a start date and an end date. The control has the two properties `dateValue` and `secondDateValue` for these values, which expect a JS `Date` object, but there is only one property `value`, which expects a string property. For binding the `value` against a start date and an end date, the composite type `sap.ui.model.type.DateInterval` has to be used.

***

<a name="loio6c9e61dc157a40c19460660ece8368bc__section_CP"/>

### Common Pitfalls

***

#### Controls are used with JavaScript `Date` objects

**To display or modify dates, times or timestamps, we recommend to bind the `value` property of the control with the corresponding data type.** The OpenUI5 framework then takes care that the values are properly displayed and sent to the back end.

> ### Caution:  
> Applications calculating with or converting JavaScript `Date`s, e.g. by adding or subtracting time zone offsets \(`oDate.getTimeZoneOffset()`\) or by using `oDate.getHour()` or `oDate.getDate()`, will break if a user-configured time zone is used that is different from the browser's time zone. The time zone offset is relative to the browser's time zone, but the timestamp is displayed in the configured time zone.

Use data binding with the corresponding OData types, so that the framework takes care to properly display the dates, times and timestampss and sends them properly to the back end.

***

#### Unexpected type in `$metadata` document

Instead of using Edm types for dates/times, an Edm.String type is used, especially when using function import parameters. The application then has to take care that the date/time values are properly sent to the back end.

For date/time types we recommend to use the corresponding Edm type for properties and function import resp. action parameters, for example:

