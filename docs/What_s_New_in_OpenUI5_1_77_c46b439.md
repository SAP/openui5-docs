<!-- loioc46b43916bd54813926e1027d723830e -->

| loio |
| -----|
| c46b43916bd54813926e1027d723830e |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/c46b43916bd54813926e1027d723830e) | [demo kit latest release](https://sdk.openui5.org/topic/c46b43916bd54813926e1027d723830e)</div>

## What's New in OpenUI5 1.77

With this release OpenUI5 is upgraded from version 1.76 to 1.77.

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

1.77 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Supported Locales and Fallback** 



</td>
<td valign="top">

**Supported Locales and Fallback**

A list of [supported locales](Supported_Locales_and_Fallback_Chain_ec753bc.md) can now be configured in the `manifest.json` file. This enables an application to only request particular resource bundles with language-specific texts. As requests, that were previously needed to check for the availability of language files, can now be avoided, this helps to improve the runtime performance of applications.

In addition, a new configuration allows you to explicitly set the fallback locale. English used to be the default locale, but now any fallback locale can be specified.

<sub>New•Feature•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



</td>
<td valign="top">

New 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Terminologies** 



</td>
<td valign="top">

**Terminologies**

By defining terminologies together with additional resource bundles, you can adapt an application for different scenarios or industries. [Terminologies](Terminologies_eba8d25.md) can be configured in the `manifest.json` file and can be activated in several ways, such as via API, URL parameter, or the bootstrap configuration.

<sub>New•Feature•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



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

-   You can now expand the first node of visually grouped aggregated data using `sap.ui.model.odata.v4.Context#expand`, as described in [Extension for Data Aggregation](Extension_for_Data_Aggregation_7d91431.md).

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataListBinding%23methods/setAggregation).

-   Binding parameters and format options can now be passed to `sap.ui.model.odata.v4.AnnotationHelper#format`, and binding parameters can be passed to `sap.ui.model.odata.v4.AnnotationHelper#value`.

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4.AnnotationHelper%23methods/).


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Samples](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

<sub>Changed•Feature•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Feature 



</td>
<td valign="top">

**Team Calendar** 



</td>
<td valign="top">

**Team Calendar**

This demo app is now enhanced with improvements in the navigation and available resolutions to provide better user experience. Switching between the different calendars now happens without loading the pages. Find the updated Team Calendar under [Demo Apps](https://sdk.openui5.orgdemoapps).

<sub>Changed•Feature•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



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

We’ve introduced the `restoreFocusOnBackNavigation` property. If the property is set to `true`, the focus is restored to the last known when navigating back to a previously opened column, for example, upon closing of the end column and being transferred back to the mid column.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.FlexibleColumnLayout) and the [Sample](https://sdk.openui5.org/entity/sap.f.FlexibleColumnLayout/sample/sap.f.sample.FlexibleColumnLayoutWithOneColumnStart).

<sub>Changed•Control•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Avatar`** 



</td>
<td valign="top">

**`sap.m.Avatar`**

You can now display visual affordance as a badge icon at the bottom-end corner of the `sap.m.Avatar` control. To set the icon that indicates the possible action that can be triggered, use the `badgeIcon` property. You can also set a tooltip for the badge icon by using the `badgeTooltip` property.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Avatar) and the [Sample](https://sdk.openui5.org/entity/sap.m.Avatar/sample/sap.m.sample.AvatarWithAffordance).

<sub>Changed•Control•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



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

We have added a new `Attention` button type to the `sap.m.ButtonType` enum. This button type indicates a critical situation. For more information about the `sap.m.Button`, see the [API Reference](https://sdk.openui5.org/api/sap.m.Button). 

<sub>Changed•Control•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



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

This control is now updated according to the latest SAP Fiori design guidelines. The horizontal scrolling behavior of the tab filters has been removed. Now, all tabs that can't fit on the tab strip, are moved over to an overflow tab. An `items` aggregation has been added to the `sap.m.IconTabFilter` control, which allows the nesting of tab filters in a hierarchical order. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IconTabBar) and the [Samples](https://sdk.openui5.org/entity/sap.m.IconTabBar). 

<sub>Changed•Control•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



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

We have introduced a new `change` event, fired when the user changes the value of the search field. Unlike the `liveChange` event, the `change` event is not fired for each key press. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SearchField).

<sub>Changed•Control•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.m.Table`** 



</td>
<td valign="top">

**`sap.m.Table`**

The automatic pop-in mode for the responsive table has been expanded: The new `hiddenInPopin` property now allows you to hide columns instead of moving them into the pop-in area based on the importance defined for each column \(`getImportance` in `sap.m.Column`\). For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Table%23methods/getHiddenInPopin) for the related method and the [Sample](https://sdk.openui5.org/entity/sap.m.Table/sample/sap.m.sample.TableAutoPopin).

<sub>Changed•Control•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



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

We have added a UI adaptation at runtime \(RTA\) `rename` action for the `sap.tnt.SideNavigation` items. Now it is possible to rename the text properties of the control at runtime directly in the SAP Fiori launchpad, without having to write new code. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.tnt.SideNavigation) and the [Samples](https://sdk.openui5.org/entity/sap.tnt.SideNavigation).

<sub>Changed•Control•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



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

-   We have introduced loading animation for UI Integration Cards. It displays a preview with an animated placeholder, which indicates the type and the attributes of the card while loading. For more information, see the loading of card samples in the [Card Explorer](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/index.html#/exploreOverview/types)..

-   We have introduced `label` and `description` properties in the Parameters and Destinations sections of the manifest. This is useful for user-friendly visualization when working with design-time configuration tools.
-   The markdown feature of Microsoft Adaptive Cards in `sap.ui.integration.widgets.Card` of type Adaptive is now enabled. The `TextBlock` element of the card supports a subset of Markdown syntax, that is defined in Microsoft's Adaptive Card. For more information, see the [Markdown Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/markdown) in the Card Explorer. 

-   We have enhanced the capabilities of the Adaptive Card by supporting the `data` property, provided on the `sap.card` level in the card's manifest. For more information, see the [Data and Templating Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/data) in the Card Explorer.

-   We have enabled manifest authors to define a destination with a basic configuration for the `Submit` action of the Adaptive Card type. Now you can control and define how the `Submit` action would be handled via the manifest. For more information, see the [Adaptive Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) section and the [Submit Action Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/adaptive/adaptive-action-submit) in the Card Explorer.


<sub>Changed•Control•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
<tr>
<td valign="top">

1.77 



</td>
<td valign="top">

Changed 



</td>
<td valign="top">

Control 



</td>
<td valign="top">

**`sap.uxap.ObjectPageLayout`** 



</td>
<td valign="top">

**`sap.uxap.ObjectPageLayout`**

-   We’ve introduced the `showTitle` property for `sap.uxap.ObjectPageSubSection` to enable you to determine whether the subsection title is displayed. If a subsection is the only one \(or the only one visible\) within a section, its title is displayed instead of the section title, even if this property is set to `false`. To hide the title of a subsection that is the only one \(or the only one visible\), you need to set the `showTitle` properties to `false` for both `ObjectPageSection` and its `ObjectPageSubSection`.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageSubSection).

-   We’ve introduced the `subSectionVisibilityChange` event. The event is fired when there’s a change in the visibility of the subsections of the page or the current tab \(when `ObjectPageLayout` is used in tabs-based mode\).For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageLayout) and the [Sample](https://sdk.openui5.org/entity/sap.uxap.ObjectPageLayout/sample/sap.uxap.sample.ObjectPageState).


<sub>Changed•Control•Info Only•1.77</sub>



</td>
<td valign="top">

Info Only 



</td>
<td valign="top">

2020-04-23



</td>
</tr>
</table>

**Parent topic:**[Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


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

