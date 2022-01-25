<!-- loioe1ddc69c01474faf830a522db8c9238a -->

| loio |
| -----|
| e1ddc69c01474faf830a522db8c9238a |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e1ddc69c01474faf830a522db8c9238a) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e1ddc69c01474faf830a522db8c9238a)</div>

## Date and Time Related Controls: Data Binding

Date and time related controls can be bound to an `OData` service.

***

<a name="loioe1ddc69c01474faf830a522db8c9238a__section_i2c_p4g_cdb"/>

### OData V4

The property binding automatically determines the appropriate type depending on the property's metadata, unless a type is specified explicitly. Check the information about automatic type determination in OData V4 under [Type Determination](Type_Determination_53cdd55.md).

***

### OData V2

***

#### Introduction

According to the `OData Version 2.0` specification, the following date and time related primitive data types exist:

1.  `Edm.Time` - represents the time as, for example, PT17H15M, which corresponds to 17:15:00.

2.  `Edm.DateTime` - represents the date and time as, for example, 2001-12-21T12:00, which corresponds to 12:00 PM on Dec 21, 2001.

3.  `Edm.DateTimeOffset` - represents the date and time as an offset in minutes from GMT, with values from 12:00:00 midnight, January 1, 1753 A.D. through to 11:59:59 P.M, December 9999 A.D. For example, 1999-01-01T23:01:00Z corresponds to 11:01:00 PM on January 1, 1999.


***

#### Binding of time values to `TimePicker`

1.  With a dedicated `Edm.Time`:

    ``` xml
    <TimePicker displayFormat="short"
                value="{ path: 'EntryTime', type: 'sap.ui.model.odata.type.Time'}"/>
    
    ```

    The sample shows how to bind time values at the backend \(for example PT11H33M55S for 11:33:55\). Note that there is a dedicated data binding type that recognizes the `Edm.Time` format and can handle time conversions in both directions - from and to the backend. When you are working with this data binding type and you choose a value using the `TimePicker` control, the same value will be sent to the backend, that is, no timezone conversions will be applied to the value.

2.  As a string:

    ``` xml
    <TimePicker value="{EntryTimeString}" valueFormat="HH:mm:ss"/>
    ```

    In the above example, the apps give the `TimePicker` information about the exact format with which the time values are stored in the backend. The whole coding is string-based \(the data field is a string, and the EDM type is an `Edm.String`\) and no conversion is done.

    With the introduction of the property `support2400` in version 1.54, this option may be used also if the apps need to differentiate between the beginning of a day \(00:00:00\) and the end of a day \(24:00:00\). For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.TimePicker) and the [Samples](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.TimePicker/preview). 


***

#### Binding of date values to `DatePicker`

``` xml
<DatePicker value="{
	path: 'EntryDate',
	type: 'sap.ui.model.odata.type.DateTime',
	constraints: {
		displayFormat: 'Date'
	}
}" />
```

If you have date values at the backend, you should bind them as shown in the sample above. When exposing its database field \(`EntryDate`\) via `OData`, date values can be exposed both as `Edm.DateTime` and `Edm.DateTimeOffset`. The syntax for binding the `DatePicker` value property is the same in both cases.

Above you can see an example of the `displayFormat` constraint. It specifies if the given value should be interpreted as Date or DateTime \(default\). If Date is specified, the binding type performs the UTC conversion, which is always on. In other words, any local date chosen by the end user will be considered as a UTC date and sent as a UTC date to the backend.

***

#### Binding of date and time values to `DateTimePicker`

``` xml
<DateTimePicker
        value="{ path: 'EntryDateTime', type: 'sap.ui.model.odata.type.DateTime' }"/>

```

In this example, the binding type specifies that the backend data will be interpreted as a date and time field.

> ### Note:  
> JavaScript provides only one object for working with dates and times – Date, which contains both date and time information. Currently, all dates that are API properties in the `DatePicker`, `TimePicker`, `DateTimePicker`, `PlanningCalendar` and `Calendar` controls use local time. For example, if a user chooses 19.02.2018 as a date from the `DatePicker`, the app developer calls the `getDateValue()` method. In this case they will get 19.02.2018 00:00:00 local time. The disadvantage here is that by default this value will be sent to the backend in UTC, which may change the date by +/- one day.

***

#### Binding of date ranges

1.  With a dedicated EDM type \(`Edm.DateTime`, `Edm.DateTimeOffset`\):

    ``` xml
    <DateRangeSelection value="{parts: [{path: 'EntryDate'}, {path: 'EntryDateTimeOffset'}], type: 'sap.ui.model.type.DateInterval',
    formatOptions: { UTC: true, format: 'yMd' }}" />
    ```

    If you have two dates in the backend represented as `Emd.DateTime` and/or `Edm.DateTimeOffset`, you can bind them to the `DateRangeSelection` control as shown above.

2.  As a string:

    If you have the date range provided with a single date formatted string field in the backend \(for example, July 29, 2015 - July 31, 2015\), use the value property in the following way:

    ``` xml
    <DateRangeSelection
            value="{path: 'EntryDateRange', valueFormat: 'MMM d, y’}"/>
    
    ```


Note that you need to tell the `DateRangeSelection` the format of the dates stored in the backend. The format should denote the format of a single date. If the delimiter is different than "-", you need to additionally specify it in the property delimiter.

**Related Information**  


[Primitive Data Types in the OData Documentation](http://www.odata.org/documentation/odata-version-2-0/overview/)

[Formatting, Parsing, and Validating Data](Formatting_Parsing_and_Validating_Data_07e4b92.md "Data that is presented on the UI often has to be converted so that is human readable and fits to the locale of the user. On the other hand, data entered by the user has to be parsed and validated to be understood by the data source. For this purpose, you use formatters and data types.")

[Step 10: Property Formatting Using Data Types](Step_10_Property_Formatting_Using_Data_Types_9252ee4.md "OpenUI5 provides a set of simple data types such as Boolean, Currency, Date and Float. These data types can then be applied to controls in order to ensure that the value presented on the screen is formatted correctly, and, if the field is open for input, that the value entered by the user adheres to the requirements of that data type. We will now add a new field called Sales Amount of type Currency.")

