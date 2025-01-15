<!-- loioeded636b85584cd586b1fe231d2b5dac -->

| loio |
| -----|
| eded636b85584cd586b1fe231d2b5dac |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/eded636b85584cd586b1fe231d2b5dac) | [demo kit latest release](https://sdk.openui5.org/topic/eded636b85584cd586b1fe231d2b5dac)</div>

## JavaScript Coding Guidelines

Provides an overview of the guidelines for JavaScript coding for OpenUI5.

For JavaScript, the following **general** guidelines apply:

-   Do **not** use global JavaScript variables. For more information, see [Modules and Dependencies](Modules_and_Dependencies_91f23a7.md).

-   Do **not** access internal \(private\) members of other objects.

-   Do **not** use the browser-native `console` object to produce a console output. Use the [`sap/base/log`](https://sdk.openui5.org/api/module:sap/base/Log) module and its respective methods to create log entries.

-   Do **not** override OpenUI5 code \(JavaScript, CSS, etc.\). Such modifications may break parts of other OpenUI5 projects.


