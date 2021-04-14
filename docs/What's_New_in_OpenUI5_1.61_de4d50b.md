<!-- loiode4d50b6c0f649fa859e4657ff8557a6 -->

| loio |
| -----|
| de4d50b6c0f649fa859e4657ff8557a6 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/de4d50b6c0f649fa859e4657ff8557a6) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/de4d50b6c0f649fa859e4657ff8557a6)</div>

## What's New in OpenUI5 1.61

With this release OpenUI5 is upgraded from version 1.60 to 1.61.

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_yxw_pxt_zcb"/>

### New Features

|**Enabling Applications to Comply with the Content Security Policy \(CSP\)**

The OpenUI5 framework now allows you to run applications in an environment in which CSP has been enabled. Inline scripts are not required anymore, but you must still allow `eval()` for OpenUI5 to run. For details about the supported policies, and for recommendations on writing CSP-compliant applications, see [Content Security Policy](Content_Security_Policy_fe1a6db.md).

> Note:  
> An application needs to be prepared to the used policy to run in a CSP-enabled environment.

|

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_bkm_s15_zcb"/>

### New Controls

|`**`sap.m.SinglePlanningCalendar`**`

The `sap.m.SinglePlanningCalendar` is a new control designed to display the schedule of a single resource. It can display three types of time intervals - a single day, a work week, or a full week. You can add custom actions to facilitate the interaction with the control.

   
  
<a name="loiode4d50b6c0f649fa859e4657ff8557a6__fig_pfj_mhs_5fb"/>SinglePlanningCalendar Header Area

 ![](loio9406ea72876f4b88982773c603b1886f_LowRes.png "SinglePlanningCalendar Header Area") 

   
  
<a name="loiode4d50b6c0f649fa859e4657ff8557a6__fig_pt5_d4r_1gb"/>SinglePlanningCalendar Meetings

 ![](loiob99c835dfb1246f2bb3a0befd34f65a9_LowRes.png "SinglePlanningCalendar Meetings") 

For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.SinglePlanningCalendar) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.SinglePlanningCalendar).

|

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_qwl_pb5_zcb"/>

### Improved Features

|**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   `sap.ui.model.odata.v4.Context#refresh` is supported for the bound context and the return value context of `sap.ui.model.odata.v4.ODataContextBinding`.

-   You can now use `sap.ui.model.odata.v4.Context#requestSideEffects` to load side effects when implicit loading is switched off via the binding-specific parameter `$$patchWithoutSideEffects`. This method must only be called on the bound context of a context binding, or on the return value context of an operation binding. With OpenUI5 1.61, there is only basic support for :n navigations, that is, the complete context is refreshed.

-   For the calculation of the path for reading data, relative bindings use the path of the context instead of the canonical path. The creation of a new entity uses the deep path as well. Use the `$$canonicalPath` binding-specific parameter to switch to the old behavior.


Note that we have introduced this change to support message processing.

> Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

|

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_rqn_wd5_zcb"/>

### Improved Controls

|**`sap.f.DynamicPage`/`sap.f.semantic.SemanticPage`**

-   With the use of the new accessibility `landmarkInfo` aggregation, you can now set custom accessibility roles and labels for the different sections of the pages.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPageAccessibleLandmarkInfo).

-   We have enabled the controls to be a droppable area. For more information, see [Drag and Drop](Drag_and_Drop_3ddb6cd.md).

|
|**`sap.f.GridList`**

We have implemented a regressive enhancement \(polyfill\) that enables the `sap.f.GridList` layout to work with Microsoft Internet Explorer 11. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.f.sample.GridListBoxContainer/preview).

|
|**`sap.m.Input`**

Тhe **`sap.m.Input`** control now has autocomplete functionality which is enabled when the `showSuggestion` Boolean property is set to `true` \(default\). As the user types in the input field, the first matching item from the suggestions list gets highlighted. Matching text is based on the beginning of the first word entered in the input field. An autocompleted value can be accepted by pressing [Enter\]. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Input) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.Input).

|
|**`sap.m.Label`**

We have changed the color for labels whose `displayOnly` property is set to `true`. The new color results in \#666 for the Belize theme and \#ddd for the Belize Deep theme. With this change, the color contrast ratio returns to the standard requirement, and the `displayOnly` label is visually indistinguishable from the normal label. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Label) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.Label).

|
|**`sap.m.ObjectHeader`**

Тhe `sap.m.ObjectHeader` control now supports circle-shaped images with the use of the new `imageShape` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ObjectHeader) and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.ObjectHeader).

|
|**`sap.m.Select`/`sap.m.SelectList`**

The `sap.m.Select` and `sap.m.SelectList` controls can now display icons before the text. You can set the icons through the `icon` property of each `sap.ui.core.ListItem` used in `sap.m.SelectList` or `sap.m.Select`.For more information, see [Sample: sap.m.Select](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.SelectWithIcons/preview) and [Sample: sap.m.SelectList](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.SelectListWithIcons/preview).

|
|**`sap.m.semantic.DetailPage`/`sap.m.semantic.SemanticPage`**

We have enabled the controls to be a droppable area. For more information, see [Drag and Drop](Drag_and_Drop_3ddb6cd.md).

|
|**`sap.m.Table`**

The `sortIndicator` property, which indicates that a column is sorted, is now available in `sap.m.Column`. The column displays the appropriate icon and also shows the sort order in the column. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Column/controlProperties) for the `SortIndicator` property.

|
|**`sap.ui.layout.cssgrid.CSSGrid`**

We have added new samples to demonstrate different use cases. For more information, see the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.cssgrid.CSSGrid).

|
|**`sap.ui.unified.Calendar`**

The `sap.ui.unified.Calendar` control now has aligned keyboard navigation when used in a single interval selection mode. This means that if the user has selected the start date but has not yet selected the end date, all dates between the start date and the date the mouse is currently hovering over will be highlighted to indicate that they will be part of the selected interval.

|
|**`sap.uxap.ObjectPageLayout`**

-   You can now enable the subsections of `sap.uxap.ObjectPageLayout` to expand to the full height of the sections container. To do this, add the `sapUxAPObjectPageSubSectionFitContainer` CSS class to the `sap.uxap.ObjectPageSubSection` to make it auto-expandable.

-   With the use of the new accessibility `landmarkInfo` aggregation, you can now set custom accessibility roles and labels for the different sections of the page.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.uxap.ObjectPageAccessibleLandmarkInfo).

-   We have enabled the control to be a droppable area. For more information, see [Drag and Drop](Drag_and_Drop_3ddb6cd.md).

-   We have changed the default layout of `Form`/`SimpleForm` in `ObjectPageSubSection` from `ResponsiveGridLayout` to `ColumnLayout`.For more information, see [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.form.ColumnLayout) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.uxap.sample.ObjectPageFormLayout/preview).


|

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_z2h_fh5_zcb"/>

### Documentation, Tutorials, and Demo Apps

|**Demo Apps/Tutorials**

-   Adapting to the modular core
-   Loading all resources asynchronously
-   Replacing deprecated APIs
-   Updating automated testing recommendations
-   Removing inline scripts in HTML pages

Some of these concepts use new APIs that have been available since OpenUI5 release 1.60.

|
|**New Quick Start Tutorial**

We have replaced the Hello World! tutorial with a new Quick Start tutorial that showcases the key features of OpenUI5 in three simple steps. For more information, see [Quick Start](Quick_Start_592f36f.md).

|

***

<a name="loiode4d50b6c0f649fa859e4657ff8557a6__section_r5v_3h5_zcb"/>

### Demo Kit Improvements

|**Tools Page**

We have updated the *Tools* page and added two more blocks about the *Support Assistant* tool and resources for the alpha release of the *UI5 Build and Development Tooling*. For more information, visit the *Tools* section in Demo Kit.

|

