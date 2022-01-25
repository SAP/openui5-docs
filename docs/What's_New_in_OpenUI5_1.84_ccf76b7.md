<!-- loioccf76b76327c421e9d87ff7fc3d7ba41 -->

| loio |
| -----|
| ccf76b76327c421e9d87ff7fc3d7ba41 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ccf76b76327c421e9d87ff7fc3d7ba41) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ccf76b76327c421e9d87ff7fc3d7ba41)</div>

## What's New in OpenUI5 1.84

With this release OpenUI5 is upgraded from version 1.82 to 1.84.

***

<a name="loioccf76b76327c421e9d87ff7fc3d7ba41__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**Asynchronous Loading of XML Content in Fragments**

The `sap.ui.core.Fragment.load()` generic function to instantiate fragments is now fully asynchronic. Many scenarios, such as the declarative use of fragments in XML views, automatically benefit from the new asynchronous behavior. If your own code [instantiates fragments programmatically](Programmatically_Instantiating_XML_Fragments_d6af195.md) and accesses dependent entities such as controls by ID, make sure you're correctly chaining to the Promise returned by `Fragment.load()`. We have adjusted samples, tutorials, and documentation to reflect the typical asynchronous usage of fragments.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Fragment/methods/sap.ui.core.Fragment.load) in the Demo Kit.



</td>
</tr>
<tr>
<td valign="top">

**Card Explorer**

-   A new Troubleshooting page has been added to the Integrate section of the Card Explorer. It contains additional tips and solutions to the most common issues with Integration cards. For more information, see [Card Explorer](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar).

-   We have added detailed documentation about sizing and layouts in Integration cards. For more information, see the [Sizing](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/sizing) and the  [Layouts](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/layouts) pages in the Card Explorer.




</td>
</tr>
<tr>
<td valign="top">

**Navigation with Dynamic Targets**

In addition to the usual static definition of navigation targets in the [Routing Configuration](Routing_Configuration_9023130.md) of the manifest, we also provide APIs to allow the declaration and display of targets at runtime. This accounts for scenarios in which the necessary information is only available at runtime, for example depending on the specific user configuration.

Note that the static definition remains the preferred solution as it allows for performance optimization. Only use dynamic targets when a static declaration is not possible. For more information, see [Navigate with Dynamic Targets](Navigate_with_Dynamic_Targets_856d6c6.md).



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V2 Model**

The new version of the OpenUI5 OData V2 model introduces the following features:

-   We have introduced a `persistTechnicalMessages` model parameter. If set to `true`, messages returned with failed requests are treated as persistent and aren't removed by the OData model.
-   An `expand` parameter can be provided to the `sap.ui.model.odata.v2.ODataModel#callFunction` method in `mParameters`. The expand is performed in a separate GET request within the same batch request as the POST request of the function import. The GET request references the result of the function import.



</td>
</tr>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   We now recommend using the [Manifest Model Preload](Manifest_Model_Preload_26ba6a5.md). For an earlier request of the root `$metadata` and the security token you need to also set the `earlyRequests` model parameter.
-   The `sap.ui.model.odata.v4.Context#refresh` method is now supported for kept-alive contexts. A list binding context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.
-   The `com.sap.vocabularies.Common.v1.ValueListRelevantQualifiers` annotation is now automatically taken into account by `sap.ui.model.odata.v4.ODataPropertyBinding#requestValueListInfo`.
-   When using `groupLevels` with the `$$aggregation` list binding parameter, we now support the collapsing and re-expanding of previously expanded nodes.
-   The `DataStateIndicator` table plugin now also works with the OData V4 model.
-   Messages resulting from failed requests contain the HTTP status code in `technicalDetails.httpStatus`.
-   Query options starting with `sap-valid-` are allowed.
-   Dynamic "[14.5.5 Expression `edm:Collection`](http://docs.oasis-open.org/odata/odata/v4.0/csprd02/part3-csdl/odata-v4.0-csprd02-part3-csdl.html#_Toc360208903)" is supported by `sap.ui.model.odata.v4.AnnotationHelper#format` and `sap.ui.model.odata.v4.AnnotationHelper#value`.

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.



</td>
</tr>
</table>

***

<a name="loioccf76b76327c421e9d87ff7fc3d7ba41__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.f.GridContainer`**

You can now drag and drop items using the keyboard into an empty container. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridContainer). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Button`**

The new `ariaHasPopup` property allows the `aria-haspopup` attribute to be set from another control that uses `sap.m.Button`. It indicates the availability and type of an interactive popup element that can be triggered by another control. This property is of type `sap.ui.core.aria.HasPopup`, which can have the following values: `None`\(default\), `Menu, ListBox, Tree, Grid`, and `Dialog`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Button).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.ComboBox`**

We have updated the behavior of the control regarding the `selectedKey` and `value` properties, to be aligned with `sap.m.Input`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ComboBox).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.IconTabBar`**

The control now supports the badge feature. You can use it to indicate that something new has been added in a tab. This visual eye catcher, in the shape of a circle inherits the semantic colors of the tab filters. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.BadgeCustomData) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarBadges).



</td>
</tr>
<tr>
<td valign="top">

`**sap.m.Input**`

We have introduced a new `valueHelpIconSrc` property. It allows you to set a custom value help icon, instead of the default one, by setting `sap.ui.core.URI` as value of the `valueHelpIconSrc` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Input) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Input/sample/sap.m.sample.InputCustomValueHelpIcon).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.List`**

The new `accDescription` property allows applications to define their own application-specific text for screen readers to replace the default text of `CustomListItem`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.CustomListItem%23methods/getAccDescription).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.ObjectStatus`**

We have made several visual improvements:

-   Samples have been updated to use the latest message and status icons.
-   Icons now have same width, which allows the text to be aligned when there are more than one items one below the other.
-   The control now supports light font in large state.

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ObjectStatus) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ObjectStatus/sample/sap.m.sample.ObjectStatus).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.ProgressIndicator`**

We have improved the control behavior when the available width is not enough and the text displayed inside `sap.m.ProgressIndicator` is truncated. Now, if the text value set in the `displayValue` property is truncated, the cursor becomes a pointer \(hand\). In such a scenario, the `ProgressIndicator` can be clicked/tapped to open an information popover that displays the full text value.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ProgressIndicator) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ProgressIndicator/sample/sap.m.sample.ProgressIndicator).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.SearchField`**

The icon of the Refresh button in the `sap.m.SearchField` is now changed from sap-icon://synchronize to sap-icon://refresh.



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Wizard` \(Experimental\)**

We have enhanced the `sap.m.Wizard` to support rendering of the steps as separate pages, instead of being appended to the previous one. Enable this by setting the new `renderMode` property to `sap.m.WizardRenderMode.Page`. The default behavior is not changed. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Wizard) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Wizard/sample/sap.m.sample.WizardSingleStep) .



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   The Calendar card is no longer in experimental state. This card shows an overview of tasks for a single entity \(such as a person or resource\). It consists of an interactive calendar and a chronological list of appointments for a single date. For more information, see [Calendar Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar) in the Card Explorer.
-   You can now dynamically fetch data to populate filters \(experimental\). For more information, see the `data` property in the [Filters](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/filters) section and the  [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/filters) in the Card Explorer.
-   We have introduced `size` and `backgroundColor` icon properties \(experimental\). They are both available for the List, Object, and Table cards, while the default card header has only the `backgroundColor` \(experimental\) property. For more information, see the [List Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/list), [Object Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/object) and [Table Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/table) sections in the Card Explorer.
-   You can now use the `oCard.triggerAction` \(experimental\) method to programmatically trigger an action from a Component card or from an extension. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.integration.widgets.CardFacade%23methods/sap.ui.integration.widgets.CardFacade.triggerAction), [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/component/triggerAction) and the [Card Actions](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/cardActions) section in the Card Explorer. 
-   You can now make HTTP POST requests with body encoding of type JSON. For more information, see the [Sample](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/data/graphql) and the [Data](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/data) section in the Card Explorer.



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.95](What's_New_in_OpenUI5_1.95_1b09465.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What's_New_in_OpenUI5_1.94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What's_New_in_OpenUI5_1.93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What's_New_in_OpenUI5_1.92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What's_New_in_OpenUI5_1.91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What's_New_in_OpenUI5_1.90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What's_New_in_OpenUI5_1.89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What's_New_in_OpenUI5_1.88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What's_New_in_OpenUI5_1.87_e315108.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What's_New_in_OpenUI5_1.86_067e2fb.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What's_New_in_OpenUI5_1.85_eeb5bd9.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.82](What's_New_in_OpenUI5_1.82_f081cf0.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What's_New_in_OpenUI5_1.81_f71563c.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What's_New_in_OpenUI5_1.80_3294c68.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What's_New_in_OpenUI5_1.79_edf8e35.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What's_New_in_OpenUI5_1.78_d176be3.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What's_New_in_OpenUI5_1.77_2ec6b6b.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What's_New_in_OpenUI5_1.76_b9b0a3f.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What's_New_in_OpenUI5_1.75_dc3d3ce.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What's_New_in_OpenUI5_1.74_21fc6cb.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What's_New_in_OpenUI5_1.73_7b82664.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What's_New_in_OpenUI5_1.72_25e5326.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What's_New_in_OpenUI5_1.71_609fd01.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What's_New_in_OpenUI5_1.70_4e89fee.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What's_New_in_OpenUI5_1.69_41203fd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What's_New_in_OpenUI5_1.68_5531aef.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What's_New_in_OpenUI5_1.67_0968958.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What's_New_in_OpenUI5_1.66_ebe7fda.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What's_New_in_OpenUI5_1.65_9d2b189.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What's_New_in_OpenUI5_1.64_1975e30.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What's_New_in_OpenUI5_1.63_77e1dcc.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What's_New_in_OpenUI5_1.62_27eea38.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.61](What's_New_in_OpenUI5_1.61_de4d50b.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What's_New_in_OpenUI5_1.60_2a70354.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What's_New_in_OpenUI5_1.58_b28edde.md "With this release, OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What's_New_in_OpenUI5_1.56_53b4b5e.md "With this release, OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What's_New_in_OpenUI5_1.54_f29023e.md "With this release, OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What's_New_in_OpenUI5_1.52_a09dd79.md "With this release, OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What's_New_in_OpenUI5_1.50_a844984.md "With this release, OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What's_New_in_OpenUI5_1.48_2818f80.md "With this release, OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What's_New_in_OpenUI5_1.46_4cf0986.md "With this release, OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What's_New_in_OpenUI5_1.44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What's_New_in_OpenUI5_1.42_4768f1a.md "With this release, OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What's_New_in_OpenUI5_1.40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What's_New_in_OpenUI5_1.38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

