<!-- loio890fce16801640459e67ec64da4daa00 -->

| loio |
| -----|
| 890fce16801640459e67ec64da4daa00 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/890fce16801640459e67ec64da4daa00) | [demo kit latest release](https://sdk.openui5.org/topic/890fce16801640459e67ec64da4daa00)</div>

## What's New in OpenUI5 1.114

With this release OpenUI5 is upgraded from version 1.113 to 1.114.

** **


<table>
<tr>
<th valign="top">

Version



</th>
<th valign="top">

Type



</th>
<th valign="top">

Category



</th>
<th valign="top">

Title



</th>
<th valign="top">

Description



</th>
<th valign="top">

Action



</th>
<th valign="top">

Available as of



</th>
</tr>
<tr>
<td valign="top">

 1.114 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.ui.integration.widgets.Card`** 



</td>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

We have \(experimentally\) introduced a new type of message – card-blocking messages. The three available types `NoData`, `Error`, and `Information` are listed in the `sap.ui.integration.CardBlockingMessageType` enumeration.

List, Table, Object, and the other declarative card types automatically show a card-blocking message when there is no data or an error has occurred. Additionally, the developers of Component cards, or those using extensions, can use the `showBlockingMessage` and `hideBlockingMessage` methods to programmatically control the message. For more information, see the [CardBlockingMessageType](https://sdk.openui5.org/api/sap.ui.integration.CardBlockingMessageType) enumeration, the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.widgets.Card), and the [Blocking Message](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/blockingMessage) and [No Data Message](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/component/noDataMessage) samples in the Card Explorer.

<sub>Changed•Control•Info Only•1.114</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-05-18



</td>
</tr>
<tr>
<td valign="top">

 1.114 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **FLP Time Zone Support in OpenUI5** 



</td>
<td valign="top">

**FLP Time Zone Support in OpenUI5**

We now enable the configuration of a time zone in OpenUI5. The configured time zone affects all applications. Using a time zone that is different from the time zone of a user's computer can break existing applications. Changing the time zone while using an application can cause unexpected side effects.

**Action:** Check and, if necessary, adapt your application code if you plan to use a configured time zone that is different from your browser's time zone.

For more information, see [Dates, Times, Timestamps, and Time Zones](Dates_Times_Timestamps_and_Time_Zones_6c9e61d.md) and [Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md).

<sub>Changed•Feature•Required•1.114</sub>



</td>
<td valign="top">

 Required 



</td>
<td valign="top">

2023-05-18



</td>
</tr>
<tr>
<td valign="top">

 1.114 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Control 



</td>
<td valign="top">

 **`sap.m.SearchField`** 



</td>
<td valign="top">

**`sap.m.SearchField`**

When the user clicks the search button \(the magnifier icon\), the `search` event is triggered with a new `searchButtonPressed` parameter. This behavior enables developers to differentiate between the actual click on the search button and keystrokes, such as [Enter\] and [Esc\], which also trigger the `search` event.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SearchField%23events/search) and the [Sample](https://sdk.openui5.org/entity/sap.m.SearchField/sample/sap.m.sample.SearchField).

<sub>Changed•Control•Info Only•1.114</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-05-18



</td>
</tr>
<tr>
<td valign="top">

 1.114 



</td>
<td valign="top">

 Changed 



</td>
<td valign="top">

 Feature 



</td>
<td valign="top">

 **Demo Kit: New Tile for UI5 Test Recorder** 



</td>
<td valign="top">

**Demo Kit: New Tile for UI5 Test Recorder**

We have added a tile for the UI5 Test Recorder to the Demo Kit Tools section for better visibility. For more information, visit the Tools section in the Demo Kit.

<sub>Changed•Feature•Info Only•1.114</sub>



</td>
<td valign="top">

 Info Only 



</td>
<td valign="top">

2023-05-18



</td>
</tr>
</table>

