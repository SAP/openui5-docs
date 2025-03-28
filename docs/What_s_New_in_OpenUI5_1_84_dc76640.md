<!-- loiodc76640051524e35a4de9a366c43c405 -->

| loio |
| -----|
| dc76640051524e35a4de9a366c43c405 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/dc76640051524e35a4de9a366c43c405) | [demo kit latest release](https://sdk.openui5.org/topic/dc76640051524e35a4de9a366c43c405)</div>

## What's New in OpenUI5 1.84

With this release OpenUI5 is upgraded from version 1.82 to 1.84.

***

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

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Asynchronous Loading of XML Content in Fragments** 

</td>
<td valign="top">

**Asynchronous Loading of XML Content in Fragments**

The `sap.ui.core.Fragment.load()` generic function to instantiate fragments is now fully asynchronic. Many scenarios, such as the declarative use of fragments in XML views, automatically benefit from the new asynchronous behavior. If your own code [instantiates fragments programmatically](Programmatically_Instantiating_XML_Fragments_d6af195.md) and accesses dependent entities such as controls by ID, make sure you're correctly chaining to the Promise returned by `Fragment.load()`. We have adjusted samples, tutorials, and documentation to reflect the typical asynchronous usage of fragments.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.Fragment/methods/sap.ui.core.Fragment.load) in the Demo Kit.

<sub>Changed•Feature•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Card Explorer** 

</td>
<td valign="top">

**Card Explorer**

-   A new Troubleshooting page has been added to the Integrate section of the Card Explorer. It contains additional tips and solutions to the most common issues with Integration cards. For more information, see [Card Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar).

-   We have added detailed documentation about sizing and layouts in Integration cards. For more information, see the [Sizing](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/sizing) and the [Layouts](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/layouts) pages in the Card Explorer.


<sub>Changed•Feature•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Navigation with Dynamic Targets** 

</td>
<td valign="top">

**Navigation with Dynamic Targets**

In addition to the usual static definition of navigation targets in the [Routing Configuration](Routing_Configuration_9023130.md) of the manifest, we also provide APIs to allow the declaration and display of targets at runtime. This accounts for scenarios in which the necessary information is only available at runtime, for example depending on the specific user configuration.

Note that the static definition remains the preferred solution as it allows for performance optimization. Only use dynamic targets when a static declaration is not possible. For more information, see [Navigate with Dynamic Targets](Navigate_with_Dynamic_Targets_856d6c6.md).

<sub>Changed•Feature•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V2 Model** 

</td>
<td valign="top">

**OpenUI5 OData V2 Model**

The new version of the OpenUI5 OData V2 model introduces the following features:

-   We have introduced a `persistTechnicalMessages` model parameter. If set to `true`, messages returned with failed requests are treated as persistent and aren't removed by the OData model.
-   An `expand` parameter can be provided to the `sap.ui.model.odata.v2.ODataModel#callFunction` method in `mParameters`. The expand is performed in a separate GET request within the same batch request as the POST request of the function import. The GET request references the result of the function import.

<sub>Changed•Feature•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

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

The new version of the OpenUI5 OData V4 model introduces the following features:

-   We now recommend using the [Manifest Model Preload](Manifest_Model_Preload_26ba6a5.md). For an earlier request of the root `$metadata` and the security token you need to also set the `earlyRequests` model parameter.
-   The `sap.ui.model.odata.v4.Context#refresh` method is now supported for kept-alive contexts. A list binding context can be kept alive with the `sap.ui.model.odata.v4.Context#setKeepAlive` method introduced with OpenUI5 1.81.
-   The `com.sap.vocabularies.Common.v1.ValueListRelevantQualifiers` annotation is now automatically taken into account by `sap.ui.model.odata.v4.ODataPropertyBinding#requestValueListInfo`.
-   When using `groupLevels` with the `$$aggregation` list binding parameter, we now support the collapsing and re-expanding of previously expanded nodes.
-   The `DataStateIndicator` table plugin now also works with the OData V4 model.
-   Messages resulting from failed requests contain the HTTP status code in `technicalDetails.httpStatus`.
-   Query options starting with `sap-valid-` are allowed.
-   Dynamic "[14.5.5 Expression `edm:Collection`](http://docs.oasis-open.org/odata/odata/v4.0/csprd02/part3-csdl/odata-v4.0-csprd02-part3-csdl.html#_Toc360208903)" is supported by `sap.ui.model.odata.v4.AnnotationHelper#format` and `sap.ui.model.odata.v4.AnnotationHelper#value`.

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

<sub>Changed•Feature•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.f.GridContainer`** 

</td>
<td valign="top">

**`sap.f.GridContainer`**

You can now drag and drop items using the keyboard into an empty container. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.GridContainer).

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Button`** 

</td>
<td valign="top">

**`sap.m.Button`**

The new `ariaHasPopup` property allows the `aria-haspopup` attribute to be set from another control that uses `sap.m.Button`. It indicates the availability and type of an interactive popup element that can be triggered by another control. This property is of type `sap.ui.core.aria.HasPopup`, which can have the following values: `None`\(default\), `Menu, ListBox, Tree, Grid`, and `Dialog`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Button).

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ComboBox`** 

</td>
<td valign="top">

**`sap.m.ComboBox`**

We have updated the behavior of the control regarding the `selectedKey` and `value` properties, to be aligned with `sap.m.Input`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ComboBox).

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

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

The control now supports the badge feature. You can use it to indicate that something new has been added in a tab. This visual eye catcher, in the shape of a circle inherits the semantic colors of the tab filters. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.BadgeCustomData) and the [Sample](https://sdk.openui5.org/entity/sap.m.IconTabBar/sample/sap.m.sample.IconTabBarBadges).

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Input`** 

</td>
<td valign="top">

**`sap.m.Input`**

We have introduced a new `valueHelpIconSrc` property. It allows you to set a custom value help icon, instead of the default one, by setting `sap.ui.core.URI` as value of the `valueHelpIconSrc` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Input) and the [Sample](https://sdk.openui5.org/entity/sap.m.Input/sample/sap.m.sample.InputCustomValueHelpIcon).

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.List`** 

</td>
<td valign="top">

**`sap.m.List`**

The new `accDescription` property allows applications to define their own application-specific text for screen readers to replace the default text of `CustomListItem`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.CustomListItem%23methods/getAccDescription).

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

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

We have made several visual improvements:

-   Samples have been updated to use the latest message and status icons.
-   Icons now have same width, which allows the text to be aligned when there are more than one items one below the other.
-   The control now supports light font in large state.

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ObjectStatus) and the [Sample](https://sdk.openui5.org/entity/sap.m.ObjectStatus/sample/sap.m.sample.ObjectStatus). 

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.ProgressIndicator`** 

</td>
<td valign="top">

**`sap.m.ProgressIndicator`**

We have improved the control behavior when the available width is not enough and the text displayed inside `sap.m.ProgressIndicator` is truncated. Now, if the text value set in the `displayValue` property is truncated, the cursor becomes a pointer \(hand\). In such a scenario, the `ProgressIndicator` can be clicked/tapped to open an information popover that displays the full text value.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ProgressIndicator) and the [Sample](https://sdk.openui5.org/entity/sap.m.ProgressIndicator/sample/sap.m.sample.ProgressIndicator).

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

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

The icon of the Refresh button in the `sap.m.SearchField` is now changed from sap-icon://synchronize to sap-icon://refresh.

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Wizard` \(Experimental\)** 

</td>
<td valign="top">

**`sap.m.Wizard` \(Experimental\)**

We have enhanced the `sap.m.Wizard` to support rendering of the steps as separate pages, instead of being appended to the previous one. Enable this by setting the new `renderMode` property to `sap.m.WizardRenderMode.Page`. The default behavior is not changed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Wizard) and the [Sample](https://sdk.openui5.org/entity/sap.m.Wizard/sample/sap.m.sample.WizardSingleStep) .

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

</td>
</tr>
<tr>
<td valign="top">

1.84 

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

-   The Calendar card is no longer in experimental state. This card shows an overview of tasks for a single entity \(such as a person or resource\). It consists of an interactive calendar and a chronological list of appointments for a single date. For more information, see [Calendar Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar) in the Card Explorer.
-   You can now dynamically fetch data to populate filters \(experimental\). For more information, see the `data` property in the [Filters](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/filters) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/filters) in the Card Explorer.
-   We have introduced `size` and `backgroundColor` icon properties \(experimental\). They are both available for the List, Object, and Table cards, while the default card header has only the `backgroundColor` \(experimental\) property. For more information, see the [List Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/list), [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/object) and [Table Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/table) sections in the Card Explorer.
-   You can now use the `oCard.triggerAction` \(experimental\) method to programmatically trigger an action from a Component card or from an extension. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.integration.widgets.CardFacade%23methods/sap.ui.integration.widgets.CardFacade.triggerAction), [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/component/triggerAction) and the [Card Actions](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/cardActions) section in the Card Explorer. 
-   You can now make HTTP POST requests with body encoding of type JSON. For more information, see the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/data/graphql) and the [Data](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/data) section in the Card Explorer.

<sub>Changed•Control•Info Only•1.84</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2020-11-20

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

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_c838330.md "With this release OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_849e1b6.md "With this release OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_759e9f3.md "With this release OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_fa1efac.md "With this release OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_6307539.md "With this release OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_a0cb7a0.md "With this release OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_468b05d.md "With this release OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_fbab50e.md "With this release OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_f218918.md "With this release OpenUI5 is upgraded from version 1.36 to 1.38.")

