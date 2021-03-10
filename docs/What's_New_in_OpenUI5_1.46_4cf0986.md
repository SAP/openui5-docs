<!-- loio4cf0986450ca43e5a8d12dd66e999a77 -->

| loio |
| -----|
| 4cf0986450ca43e5a8d12dd66e999a77 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/4cf0986450ca43e5a8d12dd66e999a77) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/4cf0986450ca43e5a8d12dd66e999a77)</div>

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

 ![](loiobbe5a6aa64b74db6bcf6f0bc510f0d34_LowRes.png) 

***

### New Controls

-   `sap.f.Avatar` is an SAP Fiori 2.0 image-like control that has different display options for representing images, initials, and icons. It allows the usage of different content, shapes, and sizes depending on the use case.

     ![](loiob6de75d7ec6745ef9bd006c430325948_LowRes.png) 

    There are several predefined sizes, as well as an option to set a custom size.

     ![](loio9127c435630540d890ff85b14cbed308_LowRes.png) 

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.Avatar) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.f.sample.Avatar/preview).

-   `sap.f.FlexibleColumnLayout`: This control represents the new SAP Fiori 2.0 base layout for an app. It implements the master-detail-detail paradigm by displaying up to three pages in separate columns. The columns are referred to as `Begin`, `Mid`, and `End`, and their width is variable depending on the current layout.

    There are several possible layouts that can be changed with the control's API, and also by the user with navigation arrows.

     ![](loio2d2dc782d40843f391a6da7b3c056acb_LowRes.png) 

    For more information, see [Building an App with the Flexible Column Layout and Related Classes](Building_an_App_with_the_Flexible_Column_Layout_and_Related_Classes_59a0e11.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.FlexibleColumnLayout), and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.f.sample.FlexibleColumnLayoutSimple/preview).

-   `sap.f.semantic.SemanticPage`: This new SAP Fiori 2.0 control represents an enhanced `sap.f.DynamicPage` that contains controls with semantic-specific meaning. You can set different actions using the available aggregations, and the `sap.f.semantic.SemanticPage` will automatically position them in dedicated sections of the title or the footer of the page, facilitating the implementation of the SAP Fiori 2.0 design guidelines.

       
      
    <a name="loio4cf0986450ca43e5a8d12dd66e999a77__fig_dxg_h4j_5y"/>Different types of actions in the title positioned in a predefined order

     ![](loio12fc65627dd9416e98d8a25fc31d2410_LowRes.png "Different types of actions in the title positioned in a predefined
    							order") 

       
      
    <a name="loio4cf0986450ca43e5a8d12dd66e999a77__fig_zvx_1wh_wy"/>Different types of actions in the footer’s right and left areas, positioned in a predefined order

     ![](loio57b825fe5df7414e89013e92e0ee30e8_LowRes.png "Different types of actions in the footer’s right and left areas,
    							positioned in a predefined order") 

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.semantic.SemanticPage) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.f.sample.SemanticPageFreeStyle/preview).

-   `sap.ui.codeeditor.CodeEditor`: You can use this control to visualize source code of various types, with syntax highlighting and line numbers, in edit and read-only mode, for example, in scenarios where you want the user to inspect and edit source code. The `CodeEditor` is a wrapper control for the open-source *Ace* code editor \(see [https://ace.c9.io](https://ace.c9.io)\). For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.codeeditor.CodeEditor) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.codeeditor.sample.CodeEditor/preview).


***

### Improved Features

***

#### OpenUI5 OData V4 Model

The new version of the OpenUI5 OData V4 model now supports the following features:

-   Changing query options on `sap.ui.model.odata.v4.ODataListBinding` and `sap.ui.model.odata.v4.ODataContextBinding`

-   Requesting `$count` system query option on `sap.ui.model.odata.v4.ODataListBinding`

-   Accessing value lists

-   Forwarding the `$search` system query option

-   Branching from OData V4 model into metadata using the hash \(`#`\) character \(see [sap.ui.model.odata.v4.Context\#getObject\(\)](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/methods/createBindingContext)\) in `template:with`


> Caution:  
> **Incompatibility Due to Bug Fix**
> 
> The following bug has been reported: If you call the [sap.ui.model.odata.v4.Context\#getObject\(\)](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/getObject) or the [sap.ui.model.odata.v4.Context\#requestObject\(\)](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.Context/methods/requestObject) methods without a parameter, the expected and documented behavior is that the same result is returned as if the parameter `sPath=""` had been specified. Due to the bug, however, the return value wraps the expected output that can then only be accessed via `.value[0]`, for example `oContext.getObject().value[0]`.
> 
> **If you have used this workaround, your application will break starting with OpenUI5 version 1.44.6.**
> 
> **Solution**: If your application needs to run with both the fixed and unfixed versions of OpenUI5, specify the `sPath=""` parameter, for `sPath` parameter. In both cases, you **must not** use the workaround with `.value[0]` any longer.

> Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).

***

#### OData V2 Model

For OData V2 models, the V2 annotation `sap:aggregation-role=”dimension”` is now converted into V4 annotation `"com.sap.vocabularies.Analytics.v1.Dimension" : { "Bool" : "true" }`.

V2 annotation `sap:aggregation-role="measure"` is now converted into V4 annotation `"com.sap.vocabularies.Analytics.v1.Measure" : { "Bool" : "true" }`. For more information, see [Meta Model for OData V2](OData_V2_Model_6c47b2b.md#loio341823349ed04df1813197f2a0d71db2) and the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.ODataMetaModel). 

***

#### One Page Acceptance Tests \(OPA5\)

The new `LabelFor` matcher checks if a given control is associated with the `sap.m.Label` control by their `labelFor` property. You can use it when searching by the text property or by the `i18n` key of the `sap.m.Label` control. For more information, see [Cookbook for OPA5](Cookbook_for_OPA5_ce4b180.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.test.matchers.LabelFor), and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.core.sample.matcher.LabelFor/preview). 

***

### Improved Controls

-   `sap.m.ComboBox`:

-   The value state error message is now visible above all list items in the dropdown list of the `sap.m.ComboBox`. This improves the usability on mobile devices \(tablets and phones\).

-   When the `ComboBox` displays two columns \(for example, key and value\), you can search and filter for matching strings in both columns. This is enabled with the `filterSecondaryValues` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ComboBox/methods/getFilterSecondaryValues) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.ComboBoxSearchBoth/preview).

-   `sap.m.DatePicker`: We have introduced a new `navigate` event. While navigating in the calendar popup of the `sap.m.DatePicker`, you can now receive an event containing the first and the last dates that are currently visible. You can use this information for lazy loading of special dates. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.DatePicker/events/navigate).

-   `sap.m.GenericTile`: The new `Actions` `scope` property was added to provide an editing option for the `GenericTile` control when included on a Web page, for example, on the SAP Fiori launchpad. It is aligned explicitly with the interaction design of the SAP Fiori launchpad’s *Edit* mode. Both the `sap.m.GenericTile` and `sap.m.SlideTile` controls have been extended with this feature. You use the new `scope` property to switch the visual representation of the `GenericTile` or `SlideTile` on a Web page from the `Display` scope to the `Actions` scope. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.GenericTile) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.GenericTileLineMode/preview).

-   `sap.m.Input` and all inheriting controls now allow filtering and searching in two or more columns. Matching is done only on the initial character and the matching sequence is displayed in bold in the suggestion list.

     ![](loiof31e644295ca4df1a16300064c886e28_LowRes.png) 

    For more information, see the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.InputAssistedTwoValues/preview).

-   `sap.m.MessageBox` can now hold and display formatted text \(`sap.m.FormattedText`\) and JSON content. This allows you to display message boxes with complex content. For more information, see the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.MessageBoxInfo/preview).

-   `sap.m.MultiComboBox`: The delay for text validation in the `sap.m.MultiComboBox` has been changed in order to react correctly to special inputs in non-Latin languages \(for example, Chinese\).

-   `sap.m.MultiInput` has been refactored to improve performance and accessibility. The `tokenChange()` event is deprecated and replaced with the new `tokenUpdate()`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.MultiInput/events/tokenUpdate).

-   `sap.m.NotificationListItem` and `sap.m.NotificationListGroup`: We have implemented several new features:

-   When the maximum number of notifications is reached, a message is shown on the bottom of the `NotificationListGroup` notifying the user about additional notifications that are hidden.

     ![](loio4387085657e0455786240dbffb89fe5b_LowRes.png) 

-   Action buttons have been moved from the footer of the `NotificationListItem` to the header to improve usability.

     ![](loio2b1c9e05fad34795bb189c9c28975b1d_LowRes.png) 

For more information, see the samples [Notification List Item](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.NotificationListItem/preview) and [Notification List Group with Max Number of Notifications Reached](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.MaxNumberOfNotificationsReached/preview).

-   `sap.m.PlanningCalendar`: We have introduced a new `rowHeaderClick` event. You can now receive an event when a row header of the `sap.m.PlanningCalendar` is clicked. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar/events/rowHeaderClick).

-   `sap.m.QuickView` and `sap.m.QuickViewCard` have a new parameter called `navOrigin` that improves the navigation when you use data binding. The new parameter is set in the `navigate` and `afterNavigate` events and holds a link to the originating card. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.QuickViewBase/events/afterNavigate).

-   `sap.m.Slider` and `sap.m.RangeSlider` can display labels for tick marks. The labels are defined and represented as a `sap.m.ResponsiveScale`, which is logically decoupled from the slider. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ResponsiveScale) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.Slider/preview).

     ![](loiob11c763f854c4b069eb89f58423bb993_LowRes.png) 

-   `sap.m.Table`: Screen reader support for sap.m.Table has been improved. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Table).

-   `sap.m.UploadCollection`: To add an item to the upload list, you can also use drag & drop on your desktop or tablet. This feature is available in both the *Instant Upload* and *Upload Pending* scenarios. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.UploadCollection) and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.m.UploadCollection).

-   `sap.ui.layout.form.Form`: The samples in the Demo Kit have been improved.

-   `sap.ui.table.*`:

-   Keyboard navigation has been enhanced for *Edit* mode.

-   You can now define row-specific actions, such as navigation. The actions remain available on the right even when you scroll horizontally.

 For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.Table) and the [sample](https://openui5.hana.ondemand.com/sample/sap.ui.table.sample.RowAction/preview).


***

### Demo Kit and Documentation Changes

You can now switch the *Samples* to the new *High Contrast White* theme from the *Settings* menu.

We reworked the landing page for the *Demo Apps* in the Demo Kit. It now features and highlights demo apps in multiple categories, and tests and related documentation chapters are now linked. Check it out at [Demo Apps](https://openui5.hana.ondemand.com/#demoapps).

New and reworked demo apps:

-   *Browse Orders*: A new master-detail app with features for browsing orders

     ![](loio67c304672d8241b4a6496b969c01d972_LowRes.png) 

-   *Shop Administrator*: The tool page demo app has been completely renovated and now showcases a shop administration scenario with controls from the `sap.tnt`, `sap.ui.layout`, and `sap.suite.ui` library.

     ![](loioa053afde39624bf29121f26802d1d168_LowRes.png) 


