<!-- loioc838330d188c4019826a0a50d7d32db1 -->

| loio |
| -----|
| c838330d188c4019826a0a50d7d32db1 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/c838330d188c4019826a0a50d7d32db1) | [demo kit latest release](https://sdk.openui5.org/topic/c838330d188c4019826a0a50d7d32db1)</div>

## What's New in OpenUI5 1.54

With this release OpenUI5 is upgraded from version 1.52 to 1.54.

****


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

1.54 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ColorPalette`** 

</td>
<td valign="top">

**`sap.m.ColorPalette`**

Provides the user with a palette containing up to 15 predefined web-standard colors, such as, Gold, Dark Magenta, and White. You can enable a *Default Color* button with a specified default color visible for the user. If the predefined set of colors is not sufficient, you can enable a *More Colors* button that opens `sap.ui.unified.ColorPicker`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ColorPalette) and the [Samples](https://sdk.openui5.org/entity/sap.m.ColorPalette).

![](images/loiob85d1e887e5b4cee961c71333ea71fe3_HiRes.png)

<sub>New•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.TimePickerSliders`** 

</td>
<td valign="top">

**`sap.m.TimePickerSliders`**

Enables the user to choose time, in different formats, from the available lists in the sliders. The control can be used inside any container. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.TimePickerSliders) and the [Samples](https://sdk.openui5.org/entity/sap.m.TimePickerSliders).

![](images/loio182377a46b7f44a5a36f7dff5f877638_HiRes.png)

<sub>New•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.tnt.InfoLabel`** 

</td>
<td valign="top">

**`sap.tnt.InfoLabel`**

Small non-interactive control whose purpose is to attract attention to a certain piece of information such as a state, quantity, condition. The control is vertically aligned with the OpenUI5 `Input` and `Button` control families.

`InfoLabel` has a `renderMode` property with the values `loose` and `narrow` that specify the side paddings. By default, the padding is loose, but for numeric text values, use narrow paddings.

![](images/loiod1abdba2289a4e569786d001b2cf17b4_HiRes.png)

![](images/loio3c064759038c4c6999c27ca0fbdac0da_HiRes.png)

The background and text color combinations are predefined. You can choose from 9 color schemes where the text content and choice of color depend on your preferences. The `colorScheme` property also accepts a digit as a value.

![](images/loio8cea6443944648fbad8860056af99f11_HiRes.png)

The size of the `InfoLabel` control adjusts to fit other controls, such as non-editable forms or tables, when the `displayOnly` property is set to `true`.

![](images/loio9023f007faa1416784779662a07a9b80_HiRes.png)

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.tnt.InfoLabel) and the [Samples](https://sdk.openui5.org/entity/sap.tnt.InfoLabel).

<sub>New•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Initialization Module for Bootstrap** 

</td>
<td valign="top">

**Initialization Module for Bootstrap**

You can now specify an initialization module that is loaded and executed after the initialization of the core with the configuration parameter `onInit` like this:.

```html
<script src="/sapui5/resources/sap-ui-core.js" 
	id="sap-ui-bootstrap"
	data-sap-ui-libs="sap.m" 
	data-sap-ui-oninit="module:sap/app/App"
	data-sap-ui-resourceroots='{"sap.app": "my/local/path"}'

	data-sap-ui-theme="sap_belize"></script>

```

For more information, see [Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md).

<sub>Changed•Feature•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**`manifest` Property for Component Containers** 

</td>
<td valign="top">

**`manifest` Property for Component Containers**

You can now also use the "Manifest First" mechanism for component containers. For more information, see [Using and Nesting Components](Using_and_Nesting_Components_346599f.md).

<sub>Changed•Feature•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V4 Model** 

</td>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model has the following features:

-   Enhancements to the adapter to use the V4 model with an OData V2 service:

    -   Handling of complex filters with `and`, `or`, `not`, brackets, and frequently used functions including `contains`.

    -   Support for bound operations by evaluating the V2 annotation `sap:action-for`.

    -   Additional annotation conversions and warnings \(in the console\) for V2 annotations that are not converted.


-   Suspend and resume absolute context and list bindings. A suspended binding will not send requests to the backend.

-   Possibility to refresh a single row in an absolute list binding.

-   Support of bound functions.

-   Newly created entities in an absolute list binding are refreshed/reread automatically after the successful post to the server.

-   It is now possible to request the `x-csrf` token and the root metadata document earlier. This is controlled by model parameter [`earlyRequests`](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/constructor).

    > ### Note:  
    > The default value of `earlyRequests` is **false** and this default may change in the future.

-   Action advertisements can be accessed in bindings by specifying `#<namespace>.<action>` 

    > ### Note:  
    > The previous method for metadata access is still available, but we recommend using a double hash \(\#\#\) syntax instead.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Sample](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

<sub>Changed•Feature•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Default Font** 

</td>
<td valign="top">

**Default Font**

A new default font, the 72 font family that offers some legibility and accessibility enhancements, has been implemented.

> ### Note:  
> Make sure the settings in your application are correct and comply with the new font, for example, texts are placed correctly and fonts are used consistently.

<sub>Changed•Feature•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Support Assistant Performance and Usability Improvements** 

</td>
<td valign="top">

**Support Assistant Performance and Usability Improvements**

There are several improvements in the Support Assistant tool:

-   Better initial loading performance - now each library should have a `.supportrc` file in its root folder. The purpose of this file is to serve as a metadata container to be used by the Support Assistant ruleset loader module.

    For more information, see [Create a Ruleset for a Library](Create_a_Ruleset_for_a_Library_b5a5135.md).

-   Improved perceived UI performance during initial tool loading – achieved by early and dynamic rendering of the most important UI elements and introducing a progress bar in the main screen of the Support Assistant.

-   Improved usability:

    -   The selection of rules to run an analysis has been improved. Now, selecting a library selects all the rules it contains.

    -   The *Issues* and *Rules* buttons are now highlighted to show the user which view is active at the moment.

    -   The issue details in the *Issues* view have been moved from the top to the bottom of the window for better usability.



![](images/loiof3258c9e029a4396a93eaf7127ab34b6_HiRes.png)

<sub>Changed•Feature•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**UI5 Inspector Updated** 

</td>
<td valign="top">

**UI5 Inspector Updated**

A new minor version 0.9.4 of the UI5 Inspector is available in the Chrome Web Store with some code adjustments and the new OpenUI5 logo.

<sub>Changed•Feature•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.DynamicPage`** 

</td>
<td valign="top">

**`sap.f.DynamicPage`**

-   A new `areaShrinkRatio` property is now available for the `sap.f.DynamicPageTitle` class. The property assigns shrinking ratios to the three areas in the `sap.f.DynamicPageTitle` \(Heading, Content, and Actions\). The greater value a section has the faster it shrinks when the screen size is reduced. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPageTitle/controlProperties).

-   A new `stateChange` event is introduced for the `sap.f.DynamicPageTitle` class. The event is fired when the state of the title \(expanded or collapsed\) is toggled by user interaction \(by clicking/tapping on the title, by using the expand/collapse button, or by scrolling down the `sap.f.DynamicPage` content\). For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPageTitle/events/stateChange).


<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayout`** 

</td>
<td valign="top">

**`sap.f.FlexibleColumnLayout`**

A new `backgroundDesign` property is added that specifies the background color of the content. The visualization of the different options depends on the used theme. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.FlexibleColumnLayout/controlProperties).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**Context Menu** 

</td>
<td valign="top">

**Context Menu**

`sap.m library` for `List`/`ListBase`, `Table`, `Tree` controls and tables in `sap.ui.table`: You can now use the context menu for these controls. For more information, see the [API Reference for the `contextMenu` aggregation](https://sdk.openui5.org/api/sap.ui.table.Table/aggregations), the [API Reference for the `beforeOpenContextMenu` event](https://sdk.openui5.org/api/sap.ui.table.Table/events/beforeOpenContextMenu) and the [Sample for `sap.ui.Table`](https://sdk.openui5.org/sample/sap.ui.table.sample.Menus/preview) \(and the same for `ListBase`\), the [Sample for `sap.m.Table`](https://sdk.openui5.org/sample/sap.m.sample.TableDnD/preview), and the [Sample for `List`](https://sdk.openui5.org/sample/sap.m.sample.ListGrouping/preview).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**Drag and Drop** 

</td>
<td valign="top">

**Drag and Drop**

`sap.m library` for `List`, `Table`, `Tree` controls: You can now use drag and drop for these controls with aggregation `dragDropConfig`. For more information, see the [API Reference for the `dragDropConfig` aggregation](https://sdk.openui5.org/api/sap.m.ListBase/aggregations.html), the [Sample for `Table`](https://sdk.openui5.org/sample/sap.m.sample.TableDnD/preview), and the [Sample for `Tree`](https://sdk.openui5.org/sample/sap.m.sample.TreeDnD/preview).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.CheckBox`** 

</td>
<td valign="top">

**`sap.m.CheckBox`**

-   A new `wrapping` property is now available that determines whether the text in the control's label is wrapped. When set to `false` \(default\), the label's text is truncated with an ellipsis at the end.

-   A new `displayOnly` property is added that enables visually distinguishable rendering of the control in gray. When set to `true`, the control becomes non-focusable and is not part of the tab chain. The `displayOnly` state is intended to be used in form controls only, and it is different from the read-only state.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.CheckBox/controlProperties) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.CheckBox/preview).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.DateTimeField`** 

</td>
<td valign="top">

**`sap.m.DateTimeField`**

With the new `initialFocusedDateValue` property, you can now set a JavaScript `Date` object to define the initially focused date/time when a picker popup is opened. This can be used in the context of `sap.m.TimePicker`, `sap.m.DatePicker`, or `sap.m.DateTimePicker` and it only takes into account the time part, the date part, or both parts of the JavaScript `Date` object, respectively. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DateTimeField).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.IconTabBar`** 

</td>
<td valign="top">

**`sap.m.IconTabBar`**

-   Updated drag and drop feature for visible tab areas - the drag and drop feature has a new visual indication, including a drop area indicator and a ghost element. The keyboard handling is also updated.

-   Implemented drag and drop in the overflow area of `IconTabBar` – the drag and drop feature is added in the overflow list of `sap.m.IconTabBar`. Rearranging tabs using the keyboard is also enabled in the overflow.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IconTabHeader) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.IconTabBarDragDrop/preview).


<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Label`** 

</td>
<td valign="top">

**`sap.m.Label`**

A new `vAlign` property has been added. It specifies the vertical alignment of `sap.m.Label`. To preserve the current behavior of the control, the default value of the property is `inherit`. From now on, app developers can set vertical alignment of `sap.m.Label` with the `vAlign` property using its get/set method, which accepts values from the `sap.ui.core.VerticalAlign` interface. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Label).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Link`** 

</td>
<td valign="top">

**`sap.m.Link`**

A new `validateUrl` property has been added that defines whether the link target URI should be validated. If validation fails, the value of the `href` property will still be set, but it will not be applied to the DOM tree. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Link/controlProperties).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.MessagePage`** 

</td>
<td valign="top">

**`sap.m.MessagePage`**

-   With the new `enableFormattedText` Boolean property, you can now enable the text that is set in the `description` property to be rendered as HTML. The new property takes effect only when the `customDescription` aggregation is not set.For a list of supported HTML tags, see the [API Reference](https://sdk.openui5.org/api/sap.m.FormattedText) for `sap.m.FormattedText`.

-   A new `buttons` aggregation is implemented that allows you to add buttons \(of type `sap.m.Button`\) to the `sap.m.MessagePage`. The buttons are centered under the description of the `MessagePage`. If more buttons are added, and enough space is available , they will be rendered on two or more lines.


For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MessagePage) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.MessagePageWithButtons/preview).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ObjectStatus`** 

</td>
<td valign="top">

**`sap.m.ObjectStatus`**

The control now has the option to have an active icon and text so the user can click/tap on them. To do this, set the new `active` property to `true`. There is also a new `press` event that fires when the user clicks/taps on active text/icon. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ObjectStatus) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.ObjectStatus/preview).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.OverflowToolbar`** 

</td>
<td valign="top">

**`sap.m.OverflowToolbar`**

The `sap.m.Label` control is now added to the list of controls that can be moved to the overflow area of `sap.m.OverflowToolbar`.

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.PlanningCalendar`**:

</td>
<td valign="top">

**`sap.m.PlanningCalendar`**

-   A new `getSelectedAppointments` method is implemented which holds the IDs of the selected appointments. If no appointments are selected, an empty array is returned. This is an addition to the `appointmentSelect` event and its `appointment` parameter where you can listen for the value of the `selected` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar/methods/getSelectedAppointments) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.PlanningCalendar/preview).

-   The control now provides the possibility for the user to drag and drop appointments in one `PlanningCalendarRow`. You can enable this behavior with the `enableAppointmentDragAndDrop` Boolean property. When an appointment is dropped over a drop target area, an `appointmentDrop` event is fired. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendarRow) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.PlanningCalendarDnD/preview).

-   For large screens, the date navigation arrows are now displayed closer to the date picker button to improve the experience of date navigation in the `sap.m.PlanningCalendar`.

-   With the use of the new `stickyHeader` property, you can now enable the header area to remain visible \(fixed on top\) when the rest of the content is scrolled out of view. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.PlanningCalendarWithStickyHeader/preview).

    > ### Restriction:  
    > There is limited browser support, hence the `stickyHeader` API is in experimental state. This API should not be used in a production environment.

-   Until now, the appointments in `sap.m.PlanningCalendar` were sorted vertically according to their duration with the longer ones being on top. With the introduction of the new API method `setCustomAppointmentsSorterCallback`, you can now sort the appointments in a custom way. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.PlanningCalendarOneLine/preview).


<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.StepInput`** 

</td>
<td valign="top">

**`sap.m.StepInput`**

-   You can now add a description and align the text with the use of the new properties: `description`, `fieldWidth`, and `textAlign`. With the `description` property, you can display text after the input field. The `fieldWidth` property specifies how much of the available space is taken from the field and how much from the description \(equal by default\). The `textAlign` property enables you to choose how the numbers in the input field are aligned. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.StepInput/controlProperties).

-   The control now increases the speed in which the value changes when the user presses and holds the increase or decrease buttons.

-   With the new `stepMode` property, you can now decide which calculation method to use for the `value` when the user chooses the increase/decrease buttons. The `AdditionAndSubtraction` type simply adds/subtracts the current `step` to/from the `value`, while the `Multiple` type increases/decreases the `value` to the closest number that is divisible by the `step`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.StepInput) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.StepInput/preview).


<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.TimePicker`** 

</td>
<td valign="top">

**`sap.m.TimePicker`**

-   You can now set not only a `00:00` time value but also `24:00` if you need the time to represent the end of the day. To enable this option, set the new `support2400` Boolean property to `true`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.TimePicker) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.TimePicker/preview).

-   With the use of the new `maskMode` property, you can now disable the assistance that is provided for the `sap.m.TimePicker` input. This enables variable length time formats, for example AM/PM formats in different languages. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.TimePicker).


<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Toolbar`** 

</td>
<td valign="top">

**`sap.m.Toolbar`**

A new `style` property has been added that defines the visual style of the `sap.m.Toolbar`. The available styles are theme-dependent and can differ based on the currently used theme. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Toolbar/controlProperties) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.ToolbarDesign/preview).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.WizardStep`** 

</td>
<td valign="top">

**`sap.m.WizardStep`**

A new Boolean property called `optional` has been added. When set to `true`, it marks a step with the text “Optional” under the step’s title. The new property only affects the visual appearance of the step and does not provide any behavioral changes to the control. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.WizardStep).

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.layout.form.Form`** 

</td>
<td valign="top">

**`sap.ui.layout.form.Form`**

Labels in form controls are now wrapped automatically using the `wrapping` property of `sap.m.label`. This prevents long labels from being cut off. For more information, see the [Sample](https://sdk.openui5.org/sample/sap.ui.layout.sample.Form354wide/preview).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.table.TreeTable`** 

</td>
<td valign="top">

**`sap.ui.table.TreeTable`**

You can now expand and collapse multiple rows at once. For more information, see the [API Reference for `expand`](https://sdk.openui5.org/api/sap.ui.table.TreeTable/methods/expand) and the [API Reference for `collapse`](https://sdk.openui5.org/api/sap.ui.table.TreeTable/methods/collapse) and the [Sample](https://sdk.openui5.org/sample/sap.ui.table.sample.TreeTable.JSONTreeBinding/preview).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.unified.CalendarLegend`** 

</td>
<td valign="top">

**`sap.ui.unified.CalendarLegend`**

With the use of the new `standardItems` property, you now have the option to configure which of the standard items related to the calendar days \(`today`, `selected`, `working`, and `non-working`\) to display. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.CalendarLegend) and the [Sample](https://sdk.openui5.org/sample/sap.ui.unified.sample.CalendarSpecialDaysLegend/preview).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.unified.Currency`** 

</td>
<td valign="top">

**`sap.ui.unified.Currency`**

The new `stringValue` property enables you to display very large numbers \(16+ characters\) without losing precision. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.Currency) and the [Sample](https://sdk.openui5.org/sample/sap.ui.unified.sample.Currency/preview).

<sub>Changed•Control•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

User Documentation 

</td>
<td valign="top">

**Documentation Updates** 

</td>
<td valign="top">

**Documentation Updates**

-   We have a new tutorial: [OData V4 Tutorial](OData_V4_Tutorial_bcdbde6.md).

-   We have reworked the [Data Binding](Data_Binding_68b9644.md) section under *Essentials*.

-   We received feedback that many examples throughout the documentation were outdated and still used the old OData model, the deprecated `sap.ui.commons` library, or used the deprecated `jQuery.sap.require` syntax. We are currently working on updating all the occurrences, and you may already notice that we have made a big step forward in this version. Nevertheless, there will still be topics we could not yet update - please be patient and allow us some more time to finish this task.


<sub>Changed•User Documentation•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
<tr>
<td valign="top">

1.54 

</td>
<td valign="top">

New 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Demo Kit Improvements** 

</td>
<td valign="top">

**Demo Kit Improvements**

-   Information about downloading OpenUI5 can now be accessed easily through the new *Download* button on the home page:

    ![](images/loio8a1b47aecf404f7183e266dad1d1afb3_HiRes.png)

-   A new *API Reference* button is now available when a sample page is loaded. It links directly to the control's API information:

    ![](images/loio2f112d6e3749461ca2c319d58343ecf5_HiRes.png)

-   In the *API Reference*, information is now available if an aggregation is used by default:

    ![](images/loio0b98785cd7404a82b7dd940616349fca_HiRes.png)

-   Browser back button functionality is available for the *API Reference* as the navigation steps are now persisted in the browser history.

-   Performance improvements: We have enabled lazy loading for the methods in the *API Reference* and implemented other various optimizations. The performance of the app has improved as a result.


<sub>Changed•Feature•Info Only•1.54</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2018-04-26

</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.133](What_s_New_in_OpenUI5_1_133_86d7605.md "With this release OpenUI5 is upgraded from version 1.132 to 1.133.")

[What's New in OpenUI5 1.132](What_s_New_in_OpenUI5_1_132_bd2e61f.md "With this release OpenUI5 is upgraded from version 1.131 to 1.132.")

[What's New in OpenUI5 1.131](What_s_New_in_OpenUI5_1_131_7d24d94.md "With this release OpenUI5 is upgraded from version 1.130 to 1.131.")

[What's New in OpenUI5 1.130](What_s_New_in_OpenUI5_1_130_85609d4.md "With this release OpenUI5 is upgraded from version 1.129 to 1.130.")

[What's New in OpenUI5 1.129](What_s_New_in_OpenUI5_1_129_d22b8af.md "With this release OpenUI5 is upgraded from version 1.128 to 1.129.")

[What's New in OpenUI5 1.128](What_s_New_in_OpenUI5_1_128_1f76220.md "With this release OpenUI5 is upgraded from version 1.127 to 1.128.")

[What's New in OpenUI5 1.127](What_s_New_in_OpenUI5_1_127_e5e1317.md "With this release OpenUI5 is upgraded from version 1.126 to 1.127.")

[What's New in OpenUI5 1.126](What_s_New_in_OpenUI5_1_126_1d98116.md "With this release OpenUI5 is upgraded from version 1.125 to 1.126.")

[What's New in OpenUI5 1.125](What_s_New_in_OpenUI5_1_125_9d87044.md "With this release OpenUI5 is upgraded from version 1.124 to 1.125.")

[What's New in OpenUI5 1.124](What_s_New_in_OpenUI5_1_124_7f77c3f.md "With this release OpenUI5 is upgraded from version 1.123 to 1.124.")

[What's New in OpenUI5 1.123](What_s_New_in_OpenUI5_1_123_9d00ac7.md "With this release OpenUI5 is upgraded from version 1.122 to 1.123.")

[What's New in OpenUI5 1.122](What_s_New_in_OpenUI5_1_122_5d078da.md "With this release OpenUI5 is upgraded from version 1.121 to 1.122.")

[What's New in OpenUI5 1.121](What_s_New_in_OpenUI5_1_121_91a4a2f.md "With this release OpenUI5 is upgraded from version 1.120 to 1.121.")

[What's New in OpenUI5 1.120](What_s_New_in_OpenUI5_1_120_2359b63.md "With this release OpenUI5 is upgraded from version 1.119 to 1.120.")

[What's New in OpenUI5 1.119](What_s_New_in_OpenUI5_1_119_0b1903a.md "With this release OpenUI5 is upgraded from version 1.118 to 1.119.")

[What's New in OpenUI5 1.118](What_s_New_in_OpenUI5_1_118_3eecbde.md "With this release OpenUI5 is upgraded from version 1.117 to 1.118.")

[What's New in OpenUI5 1.117](What_s_New_in_OpenUI5_1_117_029d3b4.md "With this release OpenUI5 is upgraded from version 1.116 to 1.117.")

[What's New in OpenUI5 1.116](What_s_New_in_OpenUI5_1_116_ebd6f34.md "With this release OpenUI5 is upgraded from version 1.115 to 1.116.")

[What's New in OpenUI5 1.115](What_s_New_in_OpenUI5_1_115_409fde8.md "With this release OpenUI5 is upgraded from version 1.114 to 1.115.")

[What's New in OpenUI5 1.114](What_s_New_in_OpenUI5_1_114_890fce1.md "With this release OpenUI5 is upgraded from version 1.113 to 1.114.")

[What's New in OpenUI5 1.113](What_s_New_in_OpenUI5_1_113_a9553fe.md "With this release OpenUI5 is upgraded from version 1.112 to 1.113.")

[What's New in OpenUI5 1.112](What_s_New_in_OpenUI5_1_112_34afc69.md "With this release OpenUI5 is upgraded from version 1.111 to 1.112.")

[What's New in OpenUI5 1.111](What_s_New_in_OpenUI5_1_111_7a67837.md "With this release OpenUI5 is upgraded from version 1.110 to 1.111.")

[What's New in OpenUI5 1.110](What_s_New_in_OpenUI5_1_110_71a855c.md "With this release OpenUI5 is upgraded from version 1.109 to 1.110.")

[What's New in OpenUI5 1.109](What_s_New_in_OpenUI5_1_109_3264bd2.md "With this release OpenUI5 is upgraded from version 1.108 to 1.109.")

[What's New in OpenUI5 1.108](What_s_New_in_OpenUI5_1_108_66e33f0.md "With this release OpenUI5 is upgraded from version 1.107 to 1.108.")

[What's New in OpenUI5 1.107](What_s_New_in_OpenUI5_1_107_d4ff916.md "With this release OpenUI5 is upgraded from version 1.106 to 1.107.")

[What's New in OpenUI5 1.106](What_s_New_in_OpenUI5_1_106_5b497b0.md "With this release OpenUI5 is upgraded from version 1.105 to 1.106.")

[What's New in OpenUI5 1.105](What_s_New_in_OpenUI5_1_105_4d6c00e.md "With this release OpenUI5 is upgraded from version 1.104 to 1.105.")

[What's New in OpenUI5 1.104](What_s_New_in_OpenUI5_1_104_69e567c.md "With this release OpenUI5 is upgraded from version 1.103 to 1.104.")

[What's New in OpenUI5 1.103](What_s_New_in_OpenUI5_1_103_0e98c76.md "With this release OpenUI5 is upgraded from version 1.102 to 1.103.")

[What's New in OpenUI5 1.102](What_s_New_in_OpenUI5_1_102_f038c99.md "With this release OpenUI5 is upgraded from version 1.101 to 1.102.")

[What's New in OpenUI5 1.101](What_s_New_in_OpenUI5_1_101_7733b00.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](What_s_New_in_OpenUI5_1_100_27dec1d.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](What_s_New_in_OpenUI5_1_99_4f35848.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](What_s_New_in_OpenUI5_1_98_d9f16f2.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](What_s_New_in_OpenUI5_1_97_fa0e282.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](What_s_New_in_OpenUI5_1_96_7a9269f.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](What_s_New_in_OpenUI5_1_95_a1aea67.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What_s_New_in_OpenUI5_1_94_c40f1e6.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What_s_New_in_OpenUI5_1_93_f273340.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What_s_New_in_OpenUI5_1_92_1ef345d.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What_s_New_in_OpenUI5_1_91_0a2bd79.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What_s_New_in_OpenUI5_1_90_91c10c2.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What_s_New_in_OpenUI5_1_89_e56cddc.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What_s_New_in_OpenUI5_1_88_e15a206.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_b506da7.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What_s_New_in_OpenUI5_1_86_4c1c959.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What_s_New_in_OpenUI5_1_85_1d18eb5.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What_s_New_in_OpenUI5_1_84_dc76640.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What_s_New_in_OpenUI5_1_82_3a8dd13.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f5e2a21.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_8cee506.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_99c4cdc.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_f09b63e.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_c46b439.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_aad03b5.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_5cbb62d.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_c22208a.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_231dd13.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_521cad9.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_a93a6a3.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_f073d69.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_89a18bd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_f94bf93.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_a6b1472.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_c9896e9.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_0f5acfd.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What_s_New_in_OpenUI5_1_64_0e30822.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_e8d9da7.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What_s_New_in_OpenUI5_1_62_771f4d5.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What_s_New_in_OpenUI5_1_61_d991552.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_5a0e1f7.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_7c927aa.md "With this release OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_108b7fd.md "With this release OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_849e1b6.md "With this release OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_759e9f3.md "With this release OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_fa1efac.md "With this release OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_6307539.md "With this release OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

