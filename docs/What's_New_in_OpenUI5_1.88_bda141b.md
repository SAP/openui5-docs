<!-- loiobda141b86c464e5bad7c0a0cc9dee753 -->

| loio |
| -----|
| bda141b86c464e5bad7c0a0cc9dee753 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/bda141b86c464e5bad7c0a0cc9dee753) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/bda141b86c464e5bad7c0a0cc9dee753)</div>

## What's New in OpenUI5 1.88

With this release OpenUI5 is upgraded from version 1.87 to 1.88.

***

<a name="loiobda141b86c464e5bad7c0a0cc9dee753__section_yxw_pxt_zcb"/>

### Announcements


<table>
<tr>
<td>

**End of Support for Microsoft Internet Explorer 11**

Starting with version 1.88, OpenUI5 no longer supports Microsoft Internet Explorer 11. For more information, see [OpenUI5 Support Status for Microsoft Internet Explorer 11](Browser_and_Platform_Support_74b59ef.md#loio74b59efa0eef48988d3b716bd0ecc933__MS_IE).



</td>
</tr>
</table>

***

<a name="loiobda141b86c464e5bad7c0a0cc9dee753__section_r5v_3h5_zcb"/>

### Demo Kit Feedback


<table>
<tr>
<td>

**Demo Kit Improvements**

Thank you all for using the Demo Kit feedback function! We have received many comments and suggestions about the different Demo Kit functionalities and we are considering all of them. Please continue providing your valuable feedback, and we will continue to implement it.

We have improved the following Demo Kit areas:

-   You can now choose to view the whole Demo Kit app in dark or light mode. We have added an *Appearance* setting in the *More Information* menu. If you choose Auto, the mode is based on your OS settings.

-   We have improved the readability of the *Known direct subclasses* popover in the *API Reference*. The subclasses are displayed in a list with only one item per row. It is now easier to browse through the numerous subclasses of base controls, such as `sap.ui.core.Control`.Check it out in the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Control).

-   You can now use the new  [Ctrl\] + [Shift\] + [F\]  shortcut combination to directly enable the global search functionality and start typing without the need to select the search field.

-   We have improved the appearance of long API names, such as methods and aggregations, in the *API Reference* so that they are no longer truncated.




</td>
</tr>
</table>

***

<a name="loiobda141b86c464e5bad7c0a0cc9dee753__section_bkm_s15_zcb"/>

### New Controls


<table>
<tr>
<td>

**`sap.f.IllustratedMessage` \(Experimental\)**

Empty states are moments in the user experience where there’s no data to display. Success states are occasions to celebrate and reward a user’s special accomplishment or the completion of an important task. The new `IllustratedMessage` control is the recommended combination of a solution-oriented message, an engaging illustration, and conversational tone to better communicate empty or success states.

![](loio46b68bf7ca8244abba196f9f15eb7c6c_HiRes.png)

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.IllustratedMessage) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.f.IllustratedMessage).



</td>
</tr>
</table>

***

<a name="loiobda141b86c464e5bad7c0a0cc9dee753__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td>

**OpenUI5 Models**

The new version of OpenUI5 introduces a new `sap.ui.model.Binding#getResolvedPath` method, which provides the resolved path for a binding's path and context. The method can be used with all bindings. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.Binding/methods/getResolvedPath).



</td>
</tr>
<tr>
<td>

**OpenUI5 OData V4 Model**

If you use a list binding for an OData V4 model and have specified a list of groupable properties in the `groupLevels` array of the `$$aggregation` list binding parameter, you can now use the `sap.ui.model.odata.v4.ODataListBinding#getDownloadUrl` method to obtain the URL for the leaf level data.

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).



</td>
</tr>
<tr>
<td>

**Test Recorder**

We've introduced the option to generate code snippets with assertions. Assertions verify that the selected property will have exactly the same value during the test as it does at the moment of recording. For more information, see [Test Recorder](Test_Recorder_2535ef9.md).



</td>
</tr>
</table>

***

<a name="loiobda141b86c464e5bad7c0a0cc9dee753__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td>

**`sap.f.GridContainer`**

We have added a new `columnsChange` event, fired when the count of grid columns changes. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.f.GridContainer/sample/sap.f.sample.GridContainer).



</td>
</tr>
<tr>
<td>

**`sap.gantt`**

We have improved the usability of the Gantt chart with the large interval/label always visible on the time axis.

 For more information, see the [API Reference](https://openui5.hana.ondemand.com/sdk/#/api/sap.gantt.misc.AxisTime) and the [Sample](https://openui5.hana.ondemand.com/sdk/#/entity/sap.gantt.simple.GanttChartWithTable). 



</td>
</tr>
<tr>
<td>

**`sap.m.UploadCollection`**

As of the SAPUI5 1.88 release, the Upload Collection control is deprecated. You can use the Upload Set \(`sap.m.upload.UploadSet`\) control that has better handling of headers and requests, unified behavior of instant and deferred uploads, as well as improved progress indication.

 For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.upload.UploadSet). 



</td>
</tr>
<tr>
<td>

**`sap.ui.integration.widgets.Card`**

-   To improve the loading performance of Integration cards, we have added a new `Auto` value to the `dataMode` \(experimental\) property. It sets the card to start the manifest processing only when the card is in the viewport. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.integration.widgets.Card/sample/sap.ui.integration.sample.LazyLoading) and the [Integrate](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/api) section in the Card Explorer.
-   In Calendar card, using the new `actions` \(experimental\) property, you can now define an action for each calendar item. A possible use case is when you want to provide a link for an online event or application. For more information, see the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/calendar/calendar) and the [Calendar Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar) section in the Card Explorer.

-   Actions can now also be used as column entries in the Table card and as group entries in the Object card. For more information, see the [Table Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/table) and the [Object Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/object) sections in the Card Explorer




</td>
</tr>
<tr>
<td>

**`sap.ui.unified.Currency`**

As an app developer you can now define custom currency names with a length of up to 5 symbols and values with a larger number of digits after the decimal point. If not explicitly set, the default maximal precision is decided based on the number of digits after the decimal point. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.unified.Currency/sample/sap.ui.unified.sample.Currency).



</td>
</tr>
</table>

