<!-- loio4cf0986450ca43e5a8d12dd66e999a77 -->

| loio |
| -----|
| 4cf0986450ca43e5a8d12dd66e999a77 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/4cf0986450ca43e5a8d12dd66e999a77) | [demo kit latest release](https://sdk.openui5.org/topic/4cf0986450ca43e5a8d12dd66e999a77)</div>

## What's New in OpenUI5 1.46

With this release, OpenUI5 is upgraded from version 1.44 to 1.46.

***

### New Features

***

#### New Themes

The High Contrast White \(HCW\) and High Contrast Black \(HCB\) themes \(`sap_belize_hcw` / `sap_belize_hcb`\) are now delivered with all SAP Fiori-related libraries. They offer a better visual experience for people with visual impairments. For more information, see [Accessibility](Accessibility_322f55d.md).

***

#### Support for Persian Calendar

All our controls now support the Persian calendar. The Persian calendar is also sometimes referred to as "Solar Hijri", "Iranian" or "Farsi" calendar.

The Persian calendar year begins around March 21st of each Gregorian year and ends at around March 20th of the following year. To convert the Persian calendar years into the equivalent Gregorian year, add 621 or 622 years to the Persian calendar year depending on whether the Persian calendar year has begun or not.

 ![](images/loiobbe5a6aa64b74db6bcf6f0bc510f0d34_LowRes.png) 

***

### New Controls

-   `sap.f.Avatar` is an SAP Fiori 2.0 image-like control that has different display options for representing images, initials, and icons. It allows the usage of different content, shapes, and sizes depending on the use case.

     ![](images/loiob6de75d7ec6745ef9bd006c430325948_LowRes.png) 

    There are several predefined sizes, as well as an option to set a custom size.

     ![](images/loio9127c435630540d890ff85b14cbed308_LowRes.png) 

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.Avatar) and the [sample](https://sdk.openui5.org/sample/sap.f.sample.Avatar/preview).

-   `sap.f.FlexibleColumnLayout`: This control represents the new SAP Fiori 2.0 base layout for an app. It implements the master-detail-detail paradigm by displaying up to three pages in separate columns. The columns are referred to as `Begin`, `Mid`, and `End`, and their width is variable depending on the current layout.

    There are several possible layouts that can be changed with the control's API, and also by the user with navigation arrows.

     ![](images/loio2d2dc782d40843f391a6da7b3c056acb_LowRes.png) 

    For more information, see [Building an App with the Flexible Column Layout and Related Classes](Building_an_App_with_the_Flexible_Column_Layout_and_Related_Classes_59a0e11.md), the [API Reference](https://sdk.openui5.org/api/sap.f.FlexibleColumnLayout), and the [sample](https://sdk.openui5.org/sample/sap.f.sample.FlexibleColumnLayoutSimple/preview).

-   `sap.f.semantic.SemanticPage`: This new SAP Fiori 2.0 control represents an enhanced `sap.f.DynamicPage` that contains controls with semantic-specific meaning. You can set different actions using the available aggregations, and the `sap.f.semantic.SemanticPage` will automatically position them in dedicated sections of the title or the footer of the page, facilitating the implementation of the SAP Fiori 2.0 design guidelines.

       
      
    <a name="loio4cf0986450ca43e5a8d12dd66e999a77__fig_dxg_h4j_5y"/>Different types of actions in the title positioned in a predefined order

     ![](images/loio12fc65627dd9416e98d8a25fc31d2410_LowRes.png "Different types of actions in the title positioned in a predefined
    							order") 

       
      
    <a name="loio4cf0986450ca43e5a8d12dd66e999a77__fig_zvx_1wh_wy"/>Different types of actions in the footer’s right and left areas, positioned in a predefined order

     ![](images/loio57b825fe5df7414e89013e92e0ee30e8_LowRes.png "Different types of actions in the footer’s right and left areas,
    							positioned in a predefined order") 

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.semantic.SemanticPage) and the [sample](https://sdk.openui5.org/sample/sap.f.sample.SemanticPageFreeStyle/preview).

-   `sap.ui.codeeditor.CodeEditor`: You can use this control to visualize source code of various types, with syntax highlighting and line numbers, in edit and read-only mode, for example, in scenarios where you want the user to inspect and edit source code. The `CodeEditor` is a wrapper control for the open-source *Ace* code editor \(see [https://ace.c9.io](https://ace.c9.io)\). For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.codeeditor.CodeEditor) and the [sample](https://sdk.openui5.org/sample/sap.ui.codeeditor.sample.CodeEditor/preview).


***

### Improved Features

***

#### OpenUI5 OData V4 Model

The new version of the OpenUI5 OData V4 model now supports the following features:

-   Changing query options on `sap.ui.model.odata.v4.ODataListBinding` and `sap.ui.model.odata.v4.ODataContextBinding`

-   Requesting `$count` system query option on `sap.ui.model.odata.v4.ODataListBinding`

-   Accessing value lists

-   Forwarding the `$search` system query option

-   Branching from OData V4 model into metadata using the hash \(`#`\) character \(see [sap.ui.model.odata.v4.Context\#getObject\(\)](https://sdk.openui5.org/api/sap.ui.model.odata.v4.ODataModel/methods/createBindingContext)\) in `template:with`


> ### Caution:  
> **Incompatibility Due to Bug Fix**
> 
> The following bug has been reported: If you call the [sap.ui.model.odata.v4.Context\#getObject\(\)](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/getObject) or the [sap.ui.model.odata.v4.Context\#requestObject\(\)](https://sdk.openui5.org/api/sap.ui.model.odata.v4.Context/methods/requestObject) methods without a parameter, the expected and documented behavior is that the same result is returned as if the parameter `sPath=""` had been specified. Due to the bug, however, the return value wraps the expected output that can then only be accessed via `.value[0]`, for example `oContext.getObject().value[0]`.
> 
> **If you have used this workaround, your application will break starting with OpenUI5 version 1.44.6.**
> 
> **Solution**: If your application needs to run with both the fixed and unfixed versions of OpenUI5, specify the `sPath=""` parameter, for `sPath` parameter. In both cases, you **must not** use the workaround with `.value[0]` any longer.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [sample](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel).

***

#### OData V2 Model

For OData V2 models, the V2 annotation `sap:aggregation-role=”dimension”` is now converted into V4 annotation `"com.sap.vocabularies.Analytics.v1.Dimension" : { "Bool" : "true" }`.

V2 annotation `sap:aggregation-role="measure"` is now converted into V4 annotation `"com.sap.vocabularies.Analytics.v1.Measure" : { "Bool" : "true" }`. For more information, see [Meta Model for OData V2](OData_V2_Model_6c47b2b.md#loio341823349ed04df1813197f2a0d71db2) and the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.ODataMetaModel). 

***

#### One Page Acceptance Tests \(OPA5\)

The new `LabelFor` matcher checks if a given control is associated with the `sap.m.Label` control by their `labelFor` property. You can use it when searching by the text property or by the `i18n` key of the `sap.m.Label` control. For more information, see [Cookbook for OPA5](Cookbook_for_OPA5_ce4b180.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.test.matchers.LabelFor), and the [sample](https://sdk.openui5.org/sample/sap.ui.core.sample.matcher.LabelFor/preview). 

***

### Improved Controls

-   `sap.m.ComboBox`:

    -   The value state error message is now visible above all list items in the dropdown list of the `sap.m.ComboBox`. This improves the usability on mobile devices \(tablets and phones\).

    -   When the `ComboBox` displays two columns \(for example, key and value\), you can search and filter for matching strings in both columns. This is enabled with the `filterSecondaryValues` property. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ComboBox/methods/getFilterSecondaryValues) and the [sample](https://sdk.openui5.org/sample/sap.m.sample.ComboBoxSearchBoth/preview).


-   `sap.m.DatePicker`: We have introduced a new `navigate` event. While navigating in the calendar popup of the `sap.m.DatePicker`, you can now receive an event containing the first and the last dates that are currently visible. You can use this information for lazy loading of special dates. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.DatePicker/events/navigate).

-   `sap.m.GenericTile`: The new `Actions` `scope` property was added to provide an editing option for the `GenericTile` control when included on a Web page, for example, on the SAP Fiori launchpad. It is aligned explicitly with the interaction design of the SAP Fiori launchpad’s *Edit* mode. Both the `sap.m.GenericTile` and `sap.m.SlideTile` controls have been extended with this feature. You use the new `scope` property to switch the visual representation of the `GenericTile` or `SlideTile` on a Web page from the `Display` scope to the `Actions` scope. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.GenericTile) and the [sample](https://sdk.openui5.org/sample/sap.m.sample.GenericTileLineMode/preview).

-   `sap.m.Input` and all inheriting controls now allow filtering and searching in two or more columns. Matching is done only on the initial character and the matching sequence is displayed in bold in the suggestion list.

     ![](images/loiof31e644295ca4df1a16300064c886e28_LowRes.png) 

    For more information, see the [sample](https://sdk.openui5.org/sample/sap.m.sample.InputAssistedTwoValues/preview).

-   `sap.m.MessageBox` can now hold and display formatted text \(`sap.m.FormattedText`\) and JSON content. This allows you to display message boxes with complex content. For more information, see the [sample](https://sdk.openui5.org/sample/sap.m.sample.MessageBoxInfo/preview).

-   `sap.m.MultiComboBox`: The delay for text validation in the `sap.m.MultiComboBox` has been changed in order to react correctly to special inputs in non-Latin languages \(for example, Chinese\).

-   `sap.m.MultiInput` has been refactored to improve performance and accessibility. The `tokenChange()` event is deprecated and replaced with the new `tokenUpdate()`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.MultiInput/events/tokenUpdate).

-   `sap.m.NotificationListItem` and `sap.m.NotificationListGroup`: We have implemented several new features:

    -   When the maximum number of notifications is reached, a message is shown on the bottom of the `NotificationListGroup` notifying the user about additional notifications that are hidden.

         ![](images/loio4387085657e0455786240dbffb89fe5b_LowRes.png) 

    -   Action buttons have been moved from the footer of the `NotificationListItem` to the header to improve usability.

         ![](images/loio2b1c9e05fad34795bb189c9c28975b1d_LowRes.png) 


    For more information, see the samples [Notification List Item](https://sdk.openui5.org/sample/sap.m.sample.NotificationListItem/preview) and [Notification List Group with Max Number of Notifications Reached](https://sdk.openui5.org/sample/sap.m.sample.MaxNumberOfNotificationsReached/preview). 

-   `sap.m.PlanningCalendar`: We have introduced a new `rowHeaderClick` event. You can now receive an event when a row header of the `sap.m.PlanningCalendar` is clicked. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.PlanningCalendar/events/rowHeaderClick).

-   `sap.m.QuickView` and `sap.m.QuickViewCard` have a new parameter called `navOrigin` that improves the navigation when you use data binding. The new parameter is set in the `navigate` and `afterNavigate` events and holds a link to the originating card. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.QuickViewBase/events/afterNavigate).

-   `sap.m.Slider` and `sap.m.RangeSlider` can display labels for tick marks. The labels are defined and represented as a `sap.m.ResponsiveScale`, which is logically decoupled from the slider. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ResponsiveScale) and the [sample](https://sdk.openui5.org/sample/sap.m.sample.Slider/preview).

     ![](images/loiob11c763f854c4b069eb89f58423bb993_LowRes.png) 

-   `sap.m.Table`: Screen reader support for sap.m.Table has been improved. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Table).

-   `sap.m.UploadCollection`: To add an item to the upload list, you can also use drag & drop on your desktop or tablet. This feature is available in both the *Instant Upload* and *Upload Pending* scenarios. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.UploadCollection) and the [sample](https://sdk.openui5.org/entity/sap.m.UploadCollection).

-   `sap.ui.layout.form.Form`: The samples in the Demo Kit have been improved.

-   `sap.ui.table.*`:

    -   Keyboard navigation has been enhanced for *Edit* mode.

    -   You can now define row-specific actions, such as navigation. The actions remain available on the right even when you scroll horizontally.


     For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.Table) and the [sample](https://sdk.openui5.org/sample/sap.ui.table.sample.RowAction/preview). 


***

### Demo Kit and Documentation Changes

You can now switch the *Samples* to the new *High Contrast White* theme from the *Settings* menu.

We reworked the landing page for the *Demo Apps* in the Demo Kit. It now features and highlights demo apps in multiple categories, and tests and related documentation chapters are now linked. Check it out at [Demo Apps](https://sdk.openui5.orgdemoapps).

New and reworked demo apps:

-   *Browse Orders*: A new master-detail app with features for browsing orders

     ![](images/loio67c304672d8241b4a6496b969c01d972_LowRes.png) 

-   *Shop Administrator*: The tool page demo app has been completely renovated and now showcases a shop administration scenario with controls from the `sap.tnt`, `sap.ui.layout`, and `sap.suite.ui` library.

     ![](images/loioa053afde39624bf29121f26802d1d168_LowRes.png) 


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

[What's New in OpenUI5 1.56](What_s_New_in_OpenUI5_1_56_53b4b5e.md "With this release, OpenUI5 is upgraded from version 1.54 to 1.56.")

[What's New in OpenUI5 1.54](What_s_New_in_OpenUI5_1_54_f29023e.md "With this release, OpenUI5 is upgraded from version 1.52 to 1.54.")

[What's New in OpenUI5 1.52](What_s_New_in_OpenUI5_1_52_a09dd79.md "With this release, OpenUI5 is upgraded from version 1.50 to 1.52.")

[What's New in OpenUI5 1.50](What_s_New_in_OpenUI5_1_50_a844984.md "With this release, OpenUI5 is upgraded from version 1.48 to 1.50.")

[What's New in OpenUI5 1.48](What_s_New_in_OpenUI5_1_48_2818f80.md "With this release, OpenUI5 is upgraded from version 1.46 to 1.48.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.42](What_s_New_in_OpenUI5_1_42_4768f1a.md "With this release, OpenUI5 is upgraded from version 1.40 to 1.42.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

