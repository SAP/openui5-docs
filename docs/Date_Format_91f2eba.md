<!-- loio91f2eba36f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f2eba36f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f2eba36f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f2eba36f4d1014b6dd926db0e91070)</div>

## Date Format

The `sap.ui.core.format.DateFormat` class can be used to parse a string representing a date, time, or the combination of date and time into a JavaScript date object and vice versa \(also known as format\). `DateFormat` formats and parses date and time values according to a set of format options. It can also be used to format intervals. A pattern base on Locale Data Markup Language \(LDML\) date format notation can be given and the date is formatted following the given pattern. `DateFormat` can also format the date and time into relative values on "day" level.

***

### Instantiation

You instantiate of `sap.ui.core.format.DateFormat` by calling the `getter` defined on the `DateFormat` \(and not by calling the constructor\):

``` js
var oDateFormat = sap.ui.core.format.DateFormat.getDateInstance();
// or
var oDateTimeFormat = sap.ui.core.format.DateFormat.getDateTimeInstance();
// or
var oTimeFormat = sap.ui.core.format.DateFormat.getTimeInstance();
```

***

### Parameters

There are several parameters which affect the final result of formatting and parsing a date. If no parameter is set, the default setting defined in the current locale is used to format and parse the date.

***

#### Date Pattern

`format` \(recommended\):

The format string does contain pattern symbols \(e.g. `yMMMd` or `Hms`\) and will be converted into the pattern in the used locale, which matches the wanted symbols best.

The symbols must be in canonical order, that is: Era \(`G`\), Year \(`y`/`Y`\), Quarter \(`q`/`Q`\), Month \(`M`/`L`\), Week \(`w`/`W`\), Day-Of-Week \(`E`/`c`\), Day \(`d`/`D`\), Hour \(`h`/`H`/`k`/`K`\), Minute \(`m`\), Second \(`s`\), Timezone \(`z`/`Z`/`v`/`V`/`O`/`X`/`x`\).

``` js
var oFormat = sap.ui.core.format.DateFormat.getInstance({
	format: "yMMMd"
});

oFormat.format(new Date()); //string in locale de "29. Jan. 2017"; string in locale en "Jan 29, 2017" 
```

`pattern`: A date pattern in LDML date format notation. The date is formatted based on the given pattern.

``` js
var oDateFormat = sap.ui.core.format.DateFormat.getDateInstance({
    pattern: "EEE, MMM d, yyyy"
});
 
var oNow = new Date();
oDateFormat.format(oNow); //string in the same format as "Thu, Jan 29, 2017"
```

> Note:
> If you define `format` and `pattern`, the `format` will be ignored!
> 
> 

The letters which can be included in this pattern are explained in the following table:Patterns<a name="loio91f2eba36f4d1014b6dd926db0e91070__table_i53_5gl_2y"/>

|Letter|Replaced By|
|------|-----------|
| `G` |era string for the current date|
| `y` |year|
| `Y` |Same as `y`, but uses the ISO year-week calendar|
| `M` |month|
| `L` |month in stand-alone format|
| `w` |week number in year|
|\(`W`\)|\(currently not supported\) week number in month|
|\(`D`\)|\(currently not supported\) day number in year|
| `d` |day number in month|
| `Q` |quarter number|
| `q` |quarter number in stand-alone format|
|\(`F`\)|\(currently not supported\) day of week in month|
| `E` |day of week|
| `c` |day of week in stand-alone format|
| `u` |day number of week|
| `a` |AM or PM|
| `j` |Can only be used in the `format` option, not in the `pattern`. It will be replaced by `h`, `H`, `K` or `k` depending on the locale preferred time cycle type \(12-hour or 24-hour\).|
| `J` |Can only be used in the `format` option, not in the `pattern`. It will be replaced by `h`, `H`, `K` or `k`. However unlike `j` it requests no `dayPeriod` marker such as "am" or "pm". It is typically used where there is enough context that the day period not necessary. For example, with `jmm`, "18:00" could appear as "6:00 PM", while with `Jmm`, it would appear as "6:00" \(no PM\).|
| `H` |hour \(0-23\)|
| `k` |hour \(1-24\)|
| `K` |hour \(0-11\)|
| `h` |hour \(1-12\)|
| `m` |minute|
| `s` |second|
| `S` |fractional second|
| `z` |time zone|
| `Z` |time zone in RFC 822 format|
| `X` |time zone in ISO 8601 format|

***

#### Style

This can be set with either `empty`, `short`, `medium` or `long`. If no pattern is given, a locale-dependent default date pattern of that style is used which is extracted from the current locale.

If in addition to `style` `pattern` or `format` is defined, the `style` is ignored.

If you use the `datetime` instance by calling `getDateTimeInstance`, you can define different styles for `date` and `time`. For example, `medium/short` defines medium style for the `date` and short style for the `time`.

***

#### Relative Format

Relative format on "day"' level is only supported by the date instance but not the date time or the time instance.

-   `relative`: if this is set to `true`, the date is formatted relatively to the actual date if it's within the given date range.

-   `relativeRange`: the day range used for relative formatting. The default is set to `6` which means only dates within the last six days, the acutal date, and the next six days are formatted relatively.

-   `relativeScale`: the relative scale is chosen depending on the difference between the given date and now, possible relative scales are: `year`, `month`, `week`, `day`, `hour`, `minute`, `second`, and `auto`

    If `auto` is set, the scale is chosen dependent on the actual difference.


***

#### Interval

`interval`: If this is set to `true`, the `DateFormat` is capable to format two dates as an interval. The `format` method expects an array with two dates as the first argument.

If the format option is set with necessary symbols, the `DateFormat` displays the fields which have the same value between the two dates only once in the result string. For example, the interval "Jan 10, 2008 - Jan 12, 2008" will be formatted as "Jan 10-12, 2008". Otherwise the two given dates are formatted separately and concatenated with locale-dependent pattern.

``` js
var oFormat = sap.ui.core.format.DateFormat.getInstance({
	format: "yMMMd",
	interval: true
});
var oDate1 = new Date(2017, 3, 11);
var oDate2 = new Date(2017, 4, 11);
oFormat.format([oDate1, oDate2]);  
// string in locale de "11. Apr. – 11. Mai 2017"; 
// string in locale en "Apr 11 – May 11, 2017"  
```

***

#### Parsing

`strictParsing`: If this is set to `true`, the `date` string is validated during parsing. If it doesn't pass the validation, `null` is returned.

``` js
var oDateFormat = sap.ui.core.format.DateFormat.getDateInstance({
    relative: true
});
 
var nMS = 1000 * 60 * 60 * 24; //milliseconds in a day
var oNow = new Date();
var oDate = new Date(oNow.getTime() - nMS);
oDateFormat.format(oDate); //returns yesterday
 
oDate = new Date(oNow.getTime() + 7 * nMS);
oDateFormat.format(oDate); //isn't returned in relative format because the default value of relativeRange is [6|-6,]
```

**Related information**  


[API Reference: `sap.ui.core.format.DateFormat`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.format.DateFormat.html)

