<!-- loio86d76053ea2e40f190773732781824e9 -->

| loio |
| -----|
| 86d76053ea2e40f190773732781824e9 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/86d76053ea2e40f190773732781824e9) | [demo kit latest release](https://sdk.openui5.org/topic/86d76053ea2e40f190773732781824e9)</div>

## What's New in OpenUI5 1.133

With this release OpenUI5 is upgraded from version 1.132 to 1.133.

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

1.133 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Deprecations** 

</td>
<td valign="top">

**Deprecations**

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated).

<sub>Deprecated•Feature•Info Only•1.133</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-02-20

</td>
</tr>
<tr>
<td valign="top">

1.133 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.table.columnmenu*`** 

</td>
<td valign="top">

**`sap.m.table.columnmenu.Menu`**

We have improved the design and interaction of the column menu for all tables. The redesigned *Column settings* menu is now implemented in `sap.ui.mdc.Table` by default. We have adapted the menu to make it more accessible and provided a leaner design by using icons for the quick actions instead of buttons. In addition, there is now a *Table Settings* button taking the user to the *View Settings* dialog with the personalization settings. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.table.columnmenu), the [Sample](https://sdk.openui5.org/entity/sap.m.Table/sample/sap.m.sample.p13n.Engine) for `sap.m.Table`, and the [Sample](https://sdk.openui5.org/entity/sap.ui.table.Table/sample/sap.m.sample.p13n.EngineGridTable) for `sap.ui.table.Table`.

<sub>Changed•Control•Info Only•1.133</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-02-20

</td>
</tr>
<tr>
<td valign="top">

1.133 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Link, sap.m.ObjectStatus, sap.m.ObjectNumber, sap.m.ObjectIdentifier, sap.m.ObjectMarker, sap.m.ObjectAttribute`** 

</td>
<td valign="top">

**`sap.m.Link, sap.m.ObjectStatus, sap.m.ObjectNumber, sap.m.ObjectIdentifier, sap.m.ObjectMarker, sap.m.ObjectAttribute`**

We have introduced a new enumeration property called `reactiveAreaMode`. The property helps meet the WCAG 2.2 Target Size requirement. It is designed to make links easier to activate and sufficiently large to help users avoid accidentally selecting unintended UI elements. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Link).

<sub>Changed•Control•Info Only•1.133</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-02-20

</td>
</tr>
<tr>
<td valign="top">

1.133 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`** 

</td>
<td valign="top">

**`sap.m.SinglePlanningCalendar`**

-   We have introduced a new method `getFirstAndLastVisibleDates` that returns the first and last visible dates within the calendar view. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar).
-   You can now select a range of days by selecting a start date, holding the [Shift\] key, and then selecting an end date. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar/sample/sap.m.sample.SinglePlanningCalendarDateSelection).

<sub>Changed•Control•Info Only•1.133</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-02-20

</td>
</tr>
<tr>
<td valign="top">

1.133 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.tnt.SideNavigation`** 

</td>
<td valign="top">

**`sap.tnt.SideNavigation`**

We have introduced a new `design` property for navigation items, enabling application developers to add an individually styled action button. This button appears on top of the other fixed items in the static footer area and can be used for quick access to frequently used actions. Moreover, parent-side navigation items now can either be dual or single click areas; non-selectable items behave as single click areas and can expand to list any child items. Lastly, a new `press` event is added for action item types. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.tnt.NavigationListItem%23controlProperties).

<sub>Changed•Control•Info Only•1.133</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-02-20

</td>
</tr>
<tr>
<td valign="top">

1.133 

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

-   In cards that have been opened from another card because of Card Actions, we have moved the **Close** button from the header to the footer. The button is now always positioned at the right end of the footer, with precedence over any other preexisting buttons. We have provided an optional setting to hide the button if it is not needed. This new feature is backward compatible but generates a footer if none exists. For more information, see the [Documentation](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/footer).
-   We have introduced a new `overflow` property for cards with a fixed height. If set to `ShowMore`, a shading gradient overlay marks the borderline over which any content is cut due to overflowing the card's fixed height. Additionally, a *Show More* button automatically appears and enables the user to open the entire card in a new window and read its full content. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.widgets.Card%23controlProperties).

<sub>Changed•Control•Info Only•1.133</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-02-20

</td>
</tr>
<tr>
<td valign="top">

1.133 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Localization** 

</td>
<td valign="top">

**Localization**

The new version of OpenUI5 introduces the following features:

-   We now use the localization content of the Unicode Common Locale Data Repository \(CLDR\) version 46.1.0. Note that we haven't taken over the changed default calendar of the `ar_SA` locale for now. Locale-specific texts for deprecated IANA time zones have been removed from the CLDR data.

-   We have introduced a mapping of deprecated IANA time zones to current IANA time zones in`sap.ui.core.format.DateFormat`. Deprecated time zones supplied to the `format` function are mapped and a locale-specific text for the current time zone is provided instead. When parsing time zones, deprecated time zone keys are mapped accordingly. For more information, see *Mapping of Deprecated Time Zones* in [Parameters](Date_Format_91f2eba.md#loio91f2eba36f4d1014b6dd926db0e91070__section_params).


<sub>Changed•Feature•Info Only•1.133</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-02-20

</td>
</tr>
<tr>
<td valign="top">

1.133 

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

We now support the creation of entities for single-valued navigation properties. For more information, see [Creating a Single Entity](Creating_a_Single_Entity_ba0e73c.md).

<sub>Changed•Feature•Info Only•1.133</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-02-20

</td>
</tr>
<tr>
<td valign="top">

1.133 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Tokenizer`** 

</td>
<td valign="top">

**`sap.m.Tokenizer`**

We've now made the `Tokenizer` available for standalone usage. This allows for a more flexible and independent use of the control. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Tokenizer%23controlProperties).

<sub>Changed•Control•Info Only•1.133</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-02-20

</td>
</tr>
</table>

