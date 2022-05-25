<!-- loiode4d50b6c0f649fa859e4657ff8557a6 -->

| loio |
| -----|
| de4d50b6c0f649fa859e4657ff8557a6 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/de4d50b6c0f649fa859e4657ff8557a6) | [demo kit latest release](https://sdk.openui5.org/topic/de4d50b6c0f649fa859e4657ff8557a6)</div>

## What's New in OpenUI5 1.61

With this release OpenUI5 is upgraded from version 1.60 to 1.61.

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_yxw_pxt_zcb"/>

### New Features


<table>
<tr>
<td valign="top">

**Enabling Applications to Comply with the Content Security Policy \(CSP\)**

The OpenUI5 framework now allows you to run applications in an environment in which CSP has been enabled. Inline scripts are not required anymore, but you must still allow `eval()` for OpenUI5 to run. For details about the supported policies, and for recommendations on writing CSP-compliant applications, see [Content Security Policy](Content_Security_Policy_fe1a6db.md).

> ### Note:  
> An application needs to be prepared to the used policy to run in a CSP-enabled environment.



</td>
</tr>
</table>

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_bkm_s15_zcb"/>

### New Controls


<table>
<tr>
<td valign="top">

<code><b><code>sap.m.SinglePlanningCalendar</code></b></code>

The `sap.m.SinglePlanningCalendar` is a new control designed to display the schedule of a single resource. It can display three types of time intervals - a single day, a work week, or a full week. You can add custom actions to facilitate the interaction with the control.

   
  
<a name="loiode4d50b6c0f649fa859e4657ff8557a6__fig_pfj_mhs_5fb"/>SinglePlanningCalendar Header Area

 ![](images/loio9406ea72876f4b88982773c603b1886f_LowRes.png "SinglePlanningCalendar Header Area") 

   
  
<a name="loiode4d50b6c0f649fa859e4657ff8557a6__fig_pt5_d4r_1gb"/>SinglePlanningCalendar Meetings

 ![](images/loiob99c835dfb1246f2bb3a0befd34f65a9_LowRes.png "SinglePlanningCalendar Meetings") 

For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SinglePlanningCalendar) and the [Samples](https://sdk.openui5.org/entity/sap.m.SinglePlanningCalendar).



</td>
</tr>
</table>

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_qwl_pb5_zcb"/>

### Improved Features


<table>
<tr>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   `sap.ui.model.odata.v4.Context#refresh` is supported for the bound context and the return value context of `sap.ui.model.odata.v4.ODataContextBinding`.

-   You can now use `sap.ui.model.odata.v4.Context#requestSideEffects` to load side effects when implicit loading is switched off via the binding-specific parameter `$$patchWithoutSideEffects`. This method must only be called on the bound context of a context binding, or on the return value context of an operation binding. With OpenUI5 1.61, there is only basic support for :n navigations, that is, the complete context is refreshed.

-   For the calculation of the path for reading data, relative bindings use the path of the context instead of the canonical path. The creation of a new entity uses the deep path as well. Use the `$$canonicalPath` binding-specific parameter to switch to the old behavior.


Note that we have introduced this change to support message processing.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).



</td>
</tr>
</table>

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.f.DynamicPage`/`sap.f.semantic.SemanticPage`**

-   With the use of the new accessibility `landmarkInfo` aggregation, you can now set custom accessibility roles and labels for the different sections of the pages.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPageAccessibleLandmarkInfo).

-   We have enabled the controls to be a droppable area. For more information, see [Drag and Drop](Drag_and_Drop_3ddb6cd.md).



</td>
</tr>
<tr>
<td valign="top">

**`sap.f.GridList`**

We have implemented a regressive enhancement \(polyfill\) that enables the `sap.f.GridList` layout to work with Microsoft Internet Explorer 11. For more information, see the [Sample](https://sdk.openui5.org/sample/sap.f.sample.GridListBoxContainer/preview).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Input`**

Тhe **`sap.m.Input`** control now has autocomplete functionality which is enabled when the `showSuggestion` Boolean property is set to `true` \(default\). As the user types in the input field, the first matching item from the suggestions list gets highlighted. Matching text is based on the beginning of the first word entered in the input field. An autocompleted value can be accepted by pressing [Enter\]. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Input) and the [Samples](https://sdk.openui5.org/entity/sap.m.Input).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Label`**

We have changed the color for labels whose `displayOnly` property is set to `true`. The new color results in \#666 for the Belize theme and \#ddd for the Belize Deep theme. With this change, the color contrast ratio returns to the standard requirement, and the `displayOnly` label is visually indistinguishable from the normal label. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Label) and the [Samples](https://sdk.openui5.org/entity/sap.m.Label).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.ObjectHeader`**

Тhe `sap.m.ObjectHeader` control now supports circle-shaped images with the use of the new `imageShape` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ObjectHeader) and the [Samples](https://sdk.openui5.org/entity/sap.m.ObjectHeader).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Select`/`sap.m.SelectList`**

The `sap.m.Select` and `sap.m.SelectList` controls can now display icons before the text. You can set the icons through the `icon` property of each `sap.ui.core.ListItem` used in `sap.m.SelectList` or `sap.m.Select`.For more information, see [Sample: sap.m.Select](https://sdk.openui5.org/sample/sap.m.sample.SelectWithIcons/preview) and [Sample: sap.m.SelectList](https://sdk.openui5.org/sample/sap.m.sample.SelectListWithIcons/preview).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.semantic.DetailPage`/`sap.m.semantic.SemanticPage`**

We have enabled the controls to be a droppable area. For more information, see [Drag and Drop](Drag_and_Drop_3ddb6cd.md).



</td>
</tr>
<tr>
<td valign="top">

**`sap.m.Table`**

The `sortIndicator` property, which indicates that a column is sorted, is now available in `sap.m.Column`. The column displays the appropriate icon and also shows the sort order in the column. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Column/controlProperties) for the `SortIndicator` property.



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.layout.cssgrid.CSSGrid`**

We have added new samples to demonstrate different use cases. For more information, see the [Samples](https://sdk.openui5.org/entity/sap.ui.layout.cssgrid.CSSGrid).



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.unified.Calendar`**

The `sap.ui.unified.Calendar` control now has aligned keyboard navigation when used in a single interval selection mode. This means that if the user has selected the start date but has not yet selected the end date, all dates between the start date and the date the mouse is currently hovering over will be highlighted to indicate that they will be part of the selected interval.



</td>
</tr>
<tr>
<td valign="top">

**`sap.uxap.ObjectPageLayout`**

-   You can now enable the subsections of `sap.uxap.ObjectPageLayout` to expand to the full height of the sections container. To do this, add the `sapUxAPObjectPageSubSectionFitContainer` CSS class to the `sap.uxap.ObjectPageSubSection` to make it auto-expandable.

-   With the use of the new accessibility `landmarkInfo` aggregation, you can now set custom accessibility roles and labels for the different sections of the page.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageAccessibleLandmarkInfo).

-   We have enabled the control to be a droppable area. For more information, see [Drag and Drop](Drag_and_Drop_3ddb6cd.md).

-   We have changed the default layout of `Form`/`SimpleForm` in `ObjectPageSubSection` from `ResponsiveGridLayout` to `ColumnLayout`.For more information, see [API Reference](https://sdk.openui5.org/api/sap.ui.layout.form.ColumnLayout) and the [Sample](https://sdk.openui5.org/sample/sap.uxap.sample.ObjectPageFormLayout/preview).




</td>
</tr>
</table>

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_z2h_fh5_zcb"/>

### Documentation, Tutorials, and Demo Apps


<table>
<tr>
<td valign="top">

**Demo Apps/Tutorials**

We have adapted all demo apps and tutorials to the latest UI5 evolution recommendations and concepts, including:

-   Adapting to the modular core
-   Loading all resources asynchronously
-   Replacing deprecated APIs
-   Updating automated testing recommendations
-   Removing inline scripts in HTML pages

Some of these concepts use new APIs that have been available since OpenUI5 release 1.60.



</td>
</tr>
<tr>
<td valign="top">

**New Quick Start Tutorial**

We have replaced the Hello World! tutorial with a new Quick Start tutorial that showcases the key features of OpenUI5 in three simple steps. For more information, see [Quick Start](Quick_Start_592f36f.md).



</td>
</tr>
</table>

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_r5v_3h5_zcb"/>

### Demo Kit Improvements


<table>
<tr>
<td valign="top">

**Tools Page**

We have updated the *Tools* page and added two more blocks about the *Support Assistant* tool and resources for the alpha release of the *UI5 Build and Development Tooling*. For more information, visit the *Tools* section in Demo Kit.



</td>
</tr>
</table>

**Parent topic:** [Previous Versions](Previous_Versions_6660a59.md "")

**Related Information**  


[What's New in OpenUI5 1.101](What_s_New_in_OpenUI5_1_101_5a18410.md "With this release OpenUI5 is upgraded from version 1.100 to 1.101.")

[What's New in OpenUI5 1.100](What_s_New_in_OpenUI5_1_100_5deb78f.md "With this release OpenUI5 is upgraded from version 1.99 to 1.100.")

[What's New in OpenUI5 1.99](What_s_New_in_OpenUI5_1_99_5e35c25.md "With this release OpenUI5 is upgraded from version 1.98 to 1.99.")

[What's New in OpenUI5 1.98](What_s_New_in_OpenUI5_1_98_7aacb4e.md "With this release OpenUI5 is upgraded from version 1.97 to 1.98.")

[What's New in OpenUI5 1.97](What_s_New_in_OpenUI5_1_97_f21858f.md "With this release OpenUI5 is upgraded from version 1.96 to 1.97.")

[What's New in OpenUI5 1.96](What_s_New_in_OpenUI5_1_96_b39a11b.md "With this release OpenUI5 is upgraded from version 1.95 to 1.96.")

[What's New in OpenUI5 1.95](What_s_New_in_OpenUI5_1_95_1b09465.md "With this release OpenUI5 is upgraded from version 1.94 to 1.95.")

[What's New in OpenUI5 1.94](What_s_New_in_OpenUI5_1_94_2d6ffdd.md "With this release OpenUI5 is upgraded from version 1.93 to 1.94.")

[What's New in OpenUI5 1.93](What_s_New_in_OpenUI5_1_93_e9c8356.md "With this release OpenUI5 is upgraded from version 1.92 to 1.93.")

[What's New in OpenUI5 1.92](What_s_New_in_OpenUI5_1_92_1492551.md "With this release OpenUI5 is upgraded from version 1.91 to 1.92.")

[What's New in OpenUI5 1.91](What_s_New_in_OpenUI5_1_91_75777da.md "With this release OpenUI5 is upgraded from version 1.90 to 1.91.")

[What's New in OpenUI5 1.90](What_s_New_in_OpenUI5_1_90_b475202.md "With this release OpenUI5 is upgraded from version 1.89 to 1.90.")

[What's New in OpenUI5 1.89](What_s_New_in_OpenUI5_1_89_0805036.md "With this release OpenUI5 is upgraded from version 1.88 to 1.89.")

[What's New in OpenUI5 1.88](What_s_New_in_OpenUI5_1_88_bda141b.md "With this release OpenUI5 is upgraded from version 1.87 to 1.88.")

[What's New in OpenUI5 1.87](What_s_New_in_OpenUI5_1_87_e315108.md "With this release OpenUI5 is upgraded from version 1.86 to 1.87.")

[What's New in OpenUI5 1.86](What_s_New_in_OpenUI5_1_86_067e2fb.md "With this release OpenUI5 is upgraded from version 1.85 to 1.86.")

[What's New in OpenUI5 1.85](What_s_New_in_OpenUI5_1_85_eeb5bd9.md "With this release OpenUI5 is upgraded from version 1.84 to 1.85.")

[What's New in OpenUI5 1.84](What_s_New_in_OpenUI5_1_84_ccf76b7.md "With this release OpenUI5 is upgraded from version 1.82 to 1.84.")

[What's New in OpenUI5 1.82](What_s_New_in_OpenUI5_1_82_f081cf0.md "With this release OpenUI5 is upgraded from version 1.81 to 1.82.")

[What's New in OpenUI5 1.81](What_s_New_in_OpenUI5_1_81_f71563c.md "With this release OpenUI5 is upgraded from version 1.80 to 1.81.")

[What's New in OpenUI5 1.80](What_s_New_in_OpenUI5_1_80_3294c68.md "With this release OpenUI5 is upgraded from version 1.79 to 1.80.")

[What's New in OpenUI5 1.79](What_s_New_in_OpenUI5_1_79_edf8e35.md "With this release OpenUI5 is upgraded from version 1.78 to 1.79.")

[What's New in OpenUI5 1.78](What_s_New_in_OpenUI5_1_78_d176be3.md "With this release OpenUI5 is upgraded from version 1.77 to 1.78.")

[What's New in OpenUI5 1.77](What_s_New_in_OpenUI5_1_77_2ec6b6b.md "With this release OpenUI5 is upgraded from version 1.76 to 1.77.")

[What's New in OpenUI5 1.76](What_s_New_in_OpenUI5_1_76_b9b0a3f.md "With this release OpenUI5 is upgraded from version 1.75 to 1.76.")

[What's New in OpenUI5 1.75](What_s_New_in_OpenUI5_1_75_dc3d3ce.md "With this release OpenUI5 is upgraded from version 1.74 to 1.75.")

[What's New in OpenUI5 1.74](What_s_New_in_OpenUI5_1_74_21fc6cb.md "With this release OpenUI5 is upgraded from version 1.73 to 1.74.")

[What's New in OpenUI5 1.73](What_s_New_in_OpenUI5_1_73_7b82664.md "With this release OpenUI5 is upgraded from version 1.72 to 1.73.")

[What's New in OpenUI5 1.72](What_s_New_in_OpenUI5_1_72_25e5326.md "With this release OpenUI5 is upgraded from version 1.71 to 1.72.")

[What's New in OpenUI5 1.71](What_s_New_in_OpenUI5_1_71_609fd01.md "With this release OpenUI5 is upgraded from version 1.70 to 1.71.")

[What's New in OpenUI5 1.70](What_s_New_in_OpenUI5_1_70_4e89fee.md "With this release OpenUI5 is upgraded from version 1.69 to 1.70.")

[What's New in OpenUI5 1.69](What_s_New_in_OpenUI5_1_69_41203fd.md "With this release OpenUI5 is upgraded from version 1.68 to 1.69.")

[What's New in OpenUI5 1.68](What_s_New_in_OpenUI5_1_68_5531aef.md "With this release OpenUI5 is upgraded from version 1.67 to 1.68.")

[What's New in OpenUI5 1.67](What_s_New_in_OpenUI5_1_67_0968958.md "With this release OpenUI5 is upgraded from version 1.66 to 1.67.")

[What's New in OpenUI5 1.66](What_s_New_in_OpenUI5_1_66_ebe7fda.md "With this release OpenUI5 is upgraded from version 1.65 to 1.66.")

[What's New in OpenUI5 1.65](What_s_New_in_OpenUI5_1_65_9d2b189.md "With this release OpenUI5 is upgraded from version 1.64 to 1.65.")

[What's New in OpenUI5 1.64](What_s_New_in_OpenUI5_1_64_1975e30.md "With this release OpenUI5 is upgraded from version 1.63 to 1.64.")

[What's New in OpenUI5 1.63](What_s_New_in_OpenUI5_1_63_77e1dcc.md "With this release OpenUI5 is upgraded from version 1.62 to 1.63.")

[What's New in OpenUI5 1.62](What_s_New_in_OpenUI5_1_62_27eea38.md "With this release OpenUI5 is upgraded from version 1.61 to 1.62.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_2a70354.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_b28edde.md "With this release, OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_53b4b5e.md "With this release, OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_f29023e.md "With this release, OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_a09dd79.md "With this release, OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_a844984.md "With this release, OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_2818f80.md "With this release, OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_4cf0986.md "With this release, OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_4768f1a.md "With this release, OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

