<!-- loio53b4b5ec2c83408a8da2cb6b9154c246 -->

| loio |
| -----|
| 53b4b5ec2c83408a8da2cb6b9154c246 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/53b4b5ec2c83408a8da2cb6b9154c246) | [demo kit latest release](https://sdk.openui5.org/topic/53b4b5ec2c83408a8da2cb6b9154c246)</div>

## What's New in OpenUI5 1.56

With this release, OpenUI5 is upgraded from version 1.54 to 1.56.

***

<a name="loio53b4b5ec2c83408a8da2cb6b9154c246__section_yxw_pxt_zcb"/>

### New Features

***

#### New Event Handler Parameter Syntax

When event handlers are assigned to control events in XML views, you can now also specify parameters which can be passed to the event handler. The parameters can be static values as well as bindings and even expressions. This feature helps to reduce controller code and avoid unnecessary controller methods, and separates the controller logic from the retrieval of the required input values.

```xml
<Button text="Add Product" press=".modifyList('add ', ${products>unitPrice})"/>
```

For more information, see [Handling Events in XML Views](Handling_Events_in_XML_Views_b0fb4de.md).

***

#### Support Assistant

The Support Assistant now allows you to import and export your rule selection. This helps you when you want to perform more than one analysis with the same subset of selected rules. The selection is exported as a `.json` file with a title and description of your choice. You can then import this file and load it whenever you want to execute the same rules in another analysis.

 ![](images/loio916079a1321e478498c896d0ce325591_HiRes.png) 

For more information, see [Rules Management](Rules_Management_3fc864a.md).

***

#### XML Composite Control

A new type of composite control, the XML composite control, is now available. It let's you build more flexible controls that contain separate XML and JavaScript parts. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.XMLComposite) and the [Samples](https://sdk.openui5.org/entity/sap.ui.core.XMLComposite). 

***

<a name="loio53b4b5ec2c83408a8da2cb6b9154c246__section_bkm_s15_zcb"/>

### New Controls


***

<a name="loio53b4b5ec2c83408a8da2cb6b9154c246__section_qwl_pb5_zcb"/>

### Improved Features

***

#### OpenUI5 OData V4 Model

The new version of the OpenUI5 OData V4 model has the following features:

-   Binding parameter `$$ownRequest` to enforce that a binding sends its own requests.

-   Binding parameter `$$aggregation` to display aggregated data.

    > ### Note:  
    > This feature is still a work in progress. So far it supports displaying a flat list of aggregated data or grouping by one groupable property without being able to expand.

-   The refresh of a single row in an absolute list binding can now also take filters into account .

-   When executing a deferred bound operation, the result of the promise returned by `v4.ODataContextBinding#execute` is the context representing the data of the bound operation response if certain conditions are fulfilled. For more information check the API for <code><a href="https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataContextBinding/methods/execute"><code>ODataContextBinding#execute</code></a></code>.


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [Sample](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

***

#### Support Assistant

-   `sap.ui.support.ExecutionScope.getElements` has a new parameter `cloned`. It allows users of the Support Assistant to filter out elements that are clones of list bindings. Now the results will include only the representative clone. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.support.ExecutionScope/methods/Summary).

-   A *Filter* view showing the currently applied filter has been added to the *Issues* view of the Support Assistant. The *Clear Filtering* button \(![](images/loio4a0cf3bc3f7244549cf95901077aa6ae_HiRes.png)\) has moved to the *Filter* view. It is active only when there is a filter selected.

-   An explanatory note has been added to the *Additional Rulesets* view under the header to give more clarity about the function of these rulesets and why they are in a separate tab.

-   The *Report* button is now fixed to the panel to be always visible and not to get into the overflow.

-   The font sizes are aligned across all three views for consistency.

-   In the *Issues* view the number of issues is only highlighted when there are issues of medium and high severity. This improvement helps to easily see the distribution of the issues by severity.


![](images/loio88301172a39245bbb35f0d5abbc26646_HiRes.png)

***

#### Drag and Drop

Configuration for dragging has been separated from the one for dropping. This allows you to also perform drag-and-drop operations, for example, from one view to another. For more information, see the [API Reference for `DragInfo`](https://sdk.openui5.org/api/sap.ui.core.dnd.DragInfo), the [API Reference for `DropInfo`](https://sdk.openui5.org/api/sap.ui.core.dnd.DropInfo), and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.TableDnD/preview).

***

#### Drag and Drop: General Support \(experimental\)

Drag and drop has been enabled for **all** controls \(with the new `dragDropConfig` aggregation\) in `sap.ui.core.Element`.

> ### Restriction:  
> This function is not intended for production use except for the controls for which drag and drop has already been enabled in previous versions \(for example, for tables and lists\).

 For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.Element/aggregations) \(`dragDropConfig` aggregation\). 

***

<a name="loio53b4b5ec2c83408a8da2cb6b9154c246__section_rqn_wd5_zcb"/>

### Improved Controls

-   `sap.f.DynamicPageHeader`: The expand/collapse arrow and the pin/unpin buttons now have a new visual design. They are centered at the bottom header border next to each other. The interaction behavior is improved and you can now collapse a pinned header with a title tap or click or by choosing the expand/collapse arrow. This means that the pinned state now prevents the header from collapsing only when the user is scrolling the page.For more information, see the [Sample](https://sdk.openui5.org/sample/sap.f.sample.DynamicPageFreeStyle/preview).

    > ### Note:  
    > The above functionality and visual appearance is also maintained when using the dynamic header of the `sap.uxap.ObjectPage` control.

-   `sap.m.DateTimePicker`: Two new properties are added to the control - `minutesStep` and `secondsStep`. They allow configuring the value step for the minutes and seconds sliders. For example, if you need the values for the minutes inside the slider to be multiples of 5, you can use the option - `minutesStep:5`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DateTimePicker) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.DateTimePicker/preview). 

-   `sap.m.IconTabBar`:

    -   Drag and drop between the header and the overflow list is now possible. When you hover over the overflow button with a dragged element, an overflow list opens and you can drag an item from the header to the list. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IconTabHeader) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.IconTabBarDragDrop/preview).

    -   A new `TabDensityMode` property is introduced in both `sap.m.IconTabBar` and `sap.m.IconTabHeader`. The property allows both the Tab Bar and the Header to change their density within different controls. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.IconTabBar) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.IconTabBarTabDensityMode/preview).


-   `sap.m.List`: The `columns` aggregation was deprecated in version 1.16 and has now been removed. Use the `sap.m.Table` control instead.

-   `sap.m.MenuButton`: The control now has a new `menuPosition` property. It specifies the position of the popup menu with enlisted options. By default, the menu opens at the bottom left side of the control but if there is not enough space in the current window, it tries to open on the opposite side. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MenuButton) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.MenuButton/preview).

-   `sap.m.PlanningCalendar:`

    -   The new `appointmentDragEnter` event allows appointments to be dragged and dropped between calendar rows. By default, when the `enableAppointmentDragAndDrop` property is enabled, appointments can be dragged only within their original `PlanningCalendarRow`. When `enableAppointmentsDragAndDrop` is set to true, attaching the event handler to the `appointmentDragEnter` event can change the default behavior and allow appointments to be dragged on the same row and between calendar rows.

    -   Appointments can now be created in one `PlanningCalendarRow` by dragging with the mouse on an empty cell. This behavior is enabled with the `enableAppointmentCreate` boolean property. When creating is finished, an `appointmentCreate` event is fired.

    -   The new `enableAppointmentResize` boolean property provides the possibility to resize appointments in one `PlanningCalendarRow`. When resizing is finished, an `appointmentResize` event is fired.

    -   A new functionality to copy appointments by dragging them is added on the `PlanningCalendarRow` level. When you press [Ctrl\]/[Cmd\] while dragging an appointment, dropping it will create a copy.

         For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendarRow) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.PlanningCalendarDnD/preview). 


-   `sap.m.PlanningCalendarRow`: The new `specialDates` aggregation allows you to mark special days on a row level. The aggregation is of type `sap.ui.unified.DayTypeRange` but you can set a specific type to the corresponding date. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendarRow/aggregations) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.PlanningCalendarWithLegend/preview).

-   `sap.m.SelectDialog`: With the new `growing` property, you can control the progressive loading of bound items. By default, it is set to `true` which means that features like the number of selected items in the info bar and search \(if present\) will work only for the currently loaded items. To make sure that all items in the table are loaded at once, and the above features work properly, you should set the growing property to `false`.

    > ### Note:  
    > The growing functionality cannot be used together with two-way binding.

     For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.SelectDialog/controlProperties). 

-   `sap.m.Slider / sap.m.RangeSlider`:

    -   You can create a custom scale \(for example, with dates\) for the sliders. To do this, you need to add custom scale and implement the `Iscale` interface.

    -   You can create a custom tooltip, by extending the class `sap.m.SliderTooltipBase` and overriding some methods. If you want to define your own content for the tooltip, you should override just the `renderTooltipContent` method.


    For more information, see [Sliders](Sliders_84ec82e.md) and the [API Reference](https://sdk.openui5.org/api/sap.m.Slider/controlProperties).

-   `sap.m.Table`:

    -   The new `sticky` property enables the column headers, infobar, and toolbar to remain in a fixed position at the top of the page during vertical scrolling.

        > ### Note:  
        > The API has changed slightly compared to the experimental API provided in version 1.54.

        For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Table/methods/getSticky) and the [Sample](https://sdk.openui5.org/sample/sap.ui.comp.sample.smarttable.mtableSticky/preview).

    -   The `popinLayout` property is now also supported for Microsoft Edge \(version 16 and higher\). For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Table/controlProperties) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.Table/preview).

-   `sap.m.TableSelectDialog`:
    -   A new property `growing` is added to the control. It determines the progressive loading. When set to `true`, the features *Selected Count* in `Info bar`, *Search*, and *Select/Deselect All*, if present, will work only for the currently loaded items. To ensure that all items in the table are loaded and these features work as expected, you need to set the property to `false`.

        > ### Note:  
        > The growing functionality cannot be used together with two-way binding.

        For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.TableSelectDialog) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.TableSelectDialogGrowing/preview). 

    -   The control now has a *Reset* button which allows you to clear the selection you have made in your Table Select dialog with one click. The button is enabled only when you make a selection. Otherwise, it is grayed out. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.TableSelectDialog) and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.TableSelectDialog/preview).


-   `sap.m.Tree`: You can now expand and collapse multiple rows at once by using the related methods. For more information, see the [API Reference for the `expand` method](https://sdk.openui5.org/api/sap.m.Tree/methods/expand), the [API Reference for the `collapse` method](https://sdk.openui5.org/api/sap.m.Tree/methods/collapse), and the [Sample](https://sdk.openui5.org/sample/sap.m.sample.TreeExpandMulti/preview).

-   `sap.ui.core.ScrollBar`: The control has been deprecated. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.core.ScrollBar).

-   `sap.ui.layout.BlockLayout`: The new `titleLink` aggregation allows the replacement of the title of a `BlockLayout` cell with a link using the `sap.m.Link` control. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.BlockLayout) and the [Sample](https://sdk.openui5.org/sample/sap.ui.layout.sample.BlockLayoutLinkTitle/preview).

-   `sap.ui.layout` library for `form.Form`, `form.SimpleForm` controls: Usability of the form controls has been improved: The form content is arranged in a flexible, horizontal way depending on the number of columns so the user doesn’t have to scroll unnecessarily, and no vertical space is wasted. A new layout `ColumnLayout` has been created for that purpose. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.layout.form.ColumnLayout) and the [Sample](https://sdk.openui5.org/sample/sap.ui.layout.sample.Form_Column_threeGroups234/preview). 

-   `sap.ui.unified.Calendar`: With the introduction of the `weekNumberSelect` event, the week numbers in Gregorian calendars have become interactive. The event indicates when you have clicked on a week number. Keep in mind that for the event to work, the `intervalSelection` property must be set to `true`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.unified.Calendar) and the [Sample](https://sdk.openui5.org/sample/sap.ui.unified.sample.CalendarSingleIntervalSelection/preview).

-   `sap.uxap.ObjectPageDynamicHeaderTitle`: UI Adaptation is enabled for the control and the following actions are possible:

    -   *Move*, *Split*, and *Combine* action buttons

    -   *Move* items defined in the `snappedContent` and `expandedContent` aggregations

    -   *Remove* and *Reveal* the whole control


    For more information, see the [Sample](https://sdk.openui5.org/sample/sap.uxap.sample.ObjectPageDynamicHeader/preview) and turn on the UI Adaptation using the wrench key button.

-   `sap.uxap.ObjectPageHeader`: The new `titleSelectorTooltip` aggregation now enables you to set a custom tooltip for the `titleSelector` button of the `sap.uxap.ObjectPageHeader`.For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageHeader/aggregations).


***

<a name="loio53b4b5ec2c83408a8da2cb6b9154c246__section_z2h_fh5_zcb"/>

### Documentation

We have a new tutorial: [Flexible Column Layout App](Flexible_Column_Layout_App_c4de2df.md). In this tutorial, we showcase how to structure your OpenUI5 app using the layout patterns that comply with the latest SAP Fiori design guidelines.

***

<a name="loio53b4b5ec2c83408a8da2cb6b9154c246__section_r5v_3h5_zcb"/>

### Demo Kit Improvements

-   We've added a *Change version* button in the Demo Kit's toolbar that enables you to easily switch the app to a different OpenUI5 version.

     ![](images/loio401b0b06690b4339856e6c517cb4c884_HiRes.png) 

-   In the *API Reference*, at the bottom of the API tree you can now find an *Index by Version* page that displays all APIs grouped by the release version they were first introduced in. Each release version is displayed as a separate tab.

     ![](images/loiod47b4612dd6d4fc68aa042c52c54f9a3_HiRes.png) 

    For more information, see *API Reference*: [Index by Version](https://sdk.openui5.org/api/since).


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

[What's New in OpenUI5 1.61](What_s_New_in_OpenUI5_1_61_de4d50b.md "With this release OpenUI5 is upgraded from version 1.60 to 1.61.")

[What's New in OpenUI5 1.60](What_s_New_in_OpenUI5_1_60_2a70354.md "With this release OpenUI5 is upgraded from version 1.58 to 1.60.")

[What's New in OpenUI5 1.58](What_s_New_in_OpenUI5_1_58_b28edde.md "With this release, OpenUI5 is upgraded from version 1.56 to 1.58.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_f29023e.md "With this release, OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_a09dd79.md "With this release, OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_a844984.md "With this release, OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_2818f80.md "With this release, OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_4cf0986.md "With this release, OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_4768f1a.md "With this release, OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

