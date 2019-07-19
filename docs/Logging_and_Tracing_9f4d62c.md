<!-- loio9f4d62c6648a423d85aaf2bfc2c7ddfe -->

| loio |
| -----|
| 9f4d62c6648a423d85aaf2bfc2c7ddfe |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9f4d62c6648a423d85aaf2bfc2c7ddfe) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9f4d62c6648a423d85aaf2bfc2c7ddfe)</div>

## Logging and Tracing

Use the built-in OpenUI5 logging mechanisms to debug and analyze applications or framework errors.

You can view the log in the console in the developer tools of your browser. A log entry contains a timestamp, a log level, a message with optional details, and component information.

Log messages can be written by the framework or the application code. Which log messages are contained in the log is defined according to their severity and the log level that is currently set.

Specific log messages only appear in the console when the severity of the issue is equal to or higher than the currently set log level. For example, when opening an OpenUI5 app without any additional configuration, the default log level \(1 = `ERROR`\) is applied. Only messages with severity `FATAL` and `ERROR` will be written to the console; other messages are not logged for performance reasons.

> Note:
> In productive applications, you should keep the system defaults for log levels for performance reasons.
> 
> 

Severities and Log Levels<a name="loio9f4d62c6648a423d85aaf2bfc2c7ddfe__table_ihz_4ld_xz"/>

|Severity|Log Level|Description|Example|
|--------|---------|-----------|-------|
| `NONE` |-1|No messages are written to the console| |
| `FATAL` |0|Unrecoverable situations|A parse error occurred while processing a JavaScript file or an XML view|
| `ERROR` |1 \(Default\)|Erroneous but recoverable situations|Loading a requested module failed|
| `WARNING` |2|Unwanted but foreseen situations|Wrong property format was passed to a control|
| `INFO` |3|Purely informative|A configuration parameter was set|
| `DEBUG` |4 \(Debug Mode\)|Information necessary for debugging|A framework event was fired|
| `TRACE` |5|Tracing the program flow|A certain position in the code was reached|
| `ALL` |6|Messages of all severity categories are written to the console| |

***

<a name="loio9f4d62c6648a423d85aaf2bfc2c7ddfe__section_wmr_fnd_xz"/>

### Tracing Errors

During development, or when you're troubleshooting application errors, you can increase the log level for debugging . When you enable debug mode, for example in the *Technical Information* dialog, the log level is automatically increased to 4 \(`DEBUG`\) and you will see messages in the console that might be helpful for finding bugs.

You can also set the log level manually, either by calling `in the application code or by setting the framework parameter <level>) setting the framework parameter <level>)```sap-ui-loglevel= \(see<level sap-ui-loglevel=<level\>[Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md)\). Depending on the log level, you might get a large amount of log messages in the console. The error might not be clearly visible from a single log message and might need further analysis.

Log entries are written to the console in chronological order. When you identify a message in the console that is connected to the error you are tracing, there might be other related log messages written shortly before or after the current message.

A dash separates the log message and the component \(or feature\) that logged it.

To find out which messages are related to a specific error, you can filter the messages in the console. Narrow down the log messages by selecting a severity or doing a full-text search, for example for a specific keyword or an OpenUI5 component.

***

<a name="loio9f4d62c6648a423d85aaf2bfc2c7ddfe__section_g5r_gnd_xz"/>

### Adding Your Own Log Messages

You can define your own log messages in your code to help tracing errors and understanding the application flow. You can use the `Log` API to create and manage log entries \(see the [API Reference: `sap/base/log`](https://openui5.hana.ondemand.com/#/api/module%3Asap%2Fbase%2FLog)\).

***

#### Generic Log Entries

To log a message, simply call `Log.*` with the specific method that corresponds to the log levels described above. The following code line issues a log statement with severity *Error*. The browser highlights the statement in red to indicate an application error:

```
// "Log" required from module "sap/base/Log"
Log.error("This should never have happened!");
```

The next code line issues a log statement with severity *Information*. The browser does not display this statement if your log console is set to filter for errors only:

```
// "Log" required from module "sap/base/Log"
Log.info("Something has happened");
```

***

#### Component Logging

The log statements above do not contain the component. A log component can be used to semantically group log entries that belong to the same software component \(or feature\).

It can be specified as an additional argument to the log function or as a default for all log entries written by a certain component. With `Log.getLogger("<component>")`, you can retrieve a logger that automatically adds the given component as component parameter to each log entry.

```
// "Log" required from module "sap/base/Log"
this._oLogger = Log.getLogger("sap.ui.demo.MyComponent");
this._oLogger.info("Something has happened");
```

> Note:
> The log entries can also be accessed programmatically. You can also register a listener to the log that will be notified whenever a new entry is added to the log.
> 
> 

***

#### Assertions

For logical checks in your application flow, you can use assertions. With `sap/base/assert` an error message is logged when a given condition is not met.

```
// "assert" required from module "sap/base/assert"
assert(aValues.length === 10, "There are 10 values stored in the array")
```

> Note:
> Assertions might be removed when the JavaScript code is optimized during a build. Therefore, callers should not rely on any side effects of this method.
> 
> 

**Related information**  


[Debugging](Debugging_.md#loioc9b0f8cca852443f9b8d3bf8ba5626ab)

[Troubleshooting Tutorial Step 1: Browser Developer Tools](Step_1_Browser_Developer_Tools_eadd60a.md)

