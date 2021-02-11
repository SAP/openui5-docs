<!-- loiob28edde1f4ad425d9247f3bbcdc5d9b7 -->

| loio |
| -----|
| b28edde1f4ad425d9247f3bbcdc5d9b7 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/b28edde1f4ad425d9247f3bbcdc5d9b7) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/b28edde1f4ad425d9247f3bbcdc5d9b7)</div>

## What's New in OpenUI5 1.58

With this release, OpenUI5 is upgraded from version 1.56 to 1.58.

***

<a name="loiob28edde1f4ad425d9247f3bbcdc5d9b7__section_yxw_pxt_zcb"/>

### New Features

***

#### Support Assistant

**Rule Presets**

-   A **rule preset management** feature has been introduced. It allows you to import, export, and switch between multiple user-defined subsets of preselected rules. You can see all imported rule presets in a dropdown menu and easily switch between them. Your current selection of rules is saved in *My Selection*.

     ![](loio7ec578324dce47239eb80b997494089f_HiRes.png) 

    > Note:  
    > To make sure that your last selection remains available for future use, choose *I agree to use local storage persistency* in the Support Assistant Settings menu.

-   An **ID field** has been added to the *Export a Rule Preset* dialog. The ID is a string of alphanumeric symbols added manually by the user when creating a rule preset. It is useful in case you want to collect data and generate reports on specific rule preset executions within your organization.

     ![](loioed742b68d91044a890eea023741b9c9d_HiRes.png) 

    For more information, see [Rules Management](Rules_Management_3fc864a.md).


**Rules View Personalization**

The Support Assistant now allows you to personalize the *Rules View* by:

-   Choosing which columns to be visible and which to remain hidden

-   Sorting the information within a column or filtering it by keyword. To access these options, click on a column header. A dropdown menu opens from which you can choose the desired action.


 ![](loiobaf460d2ca344bb3a6c2655fff96facc_HiRes.png) 

For more information, see [Rules Management](Rules_Management_3fc864a.md).

***

#### UI5 Inspector

The latest version 0.9.5 of the UI5 Inspector includes two main features:

-   Now it supports a dark theme, for when you use Google Development Tools in dark mode.

-   In previous versions, the UI5 Inspector did not properly display composite binding structures. Now it shows all parts of the bindings on the *Bindings* tab, including individual models, paths, and values. Clicking on the model link displays the whole model with all values.

     ![](loio460e1e3933a14e9cb5358b2a55317485_HiRes.png) 


For more information, see [UI5 Inspector](UI5_Inspector_b24e724.md).

***

<a name="loiob28edde1f4ad425d9247f3bbcdc5d9b7__section_qwl_pb5_zcb"/>

### Improved Features

***

#### OpenUI5 OData V4 Model

The new version of the OpenUI5 OData V4 model introduces the following features:

-   Messages sent in the `sap-messages` header are evaluated by the model and transmitted to the message model.

-   Messages sent in the data response of success responses are processed by the OData V4 model and forwarded to the message model. The message property needs to have the documented structure and its existence needs to be communicated using the dedicated metadata annotation `com.sap.vocabularies.Common.v1.Messages`. For more information, see [OData V2 Messages](OData_V2_Messages_81c735e.md).

-   Batch groups whose names start with `$auto.` are handled like the predefined group `$auto`.

-   Exclude filters `NB` \(not between\), `NotContains`, `NotEndsWith`, and `NotStartsWith` are supported.


> Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).

***

#### XML Templating: No Preloading Required for Asynchronous Views

With the new version of XML templating, preloading of OData V4 metadata is no longer required if the view is asynchronous.

For more information, see the [API Reference: `sap.ui.core.util.XMLPreprocessor`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.util.XMLPreprocessor) and the [API Reference: `sap.ui.core.mvc.XMLView`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.mvc.XMLView).

***

<a name="loiob28edde1f4ad425d9247f3bbcdc5d9b7__section_rqn_wd5_zcb"/>

### Improved Controls

-   `sap.f.DynamicPage`:

-   You can now use the `sapUiContentPadding`, `sapUiNoContentPadding`, and `sapUiResponsiveContentPadding` CSS classes to adjust the content padding of the `DynamicPage` control.For more information, see [Using Container Content Padding CSS Classes](Using_Container_Content_Padding_CSS_Classes_c71f6df.md) and the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPage/aggregations). 

-   The `sap.f.DynamicPageHeader` and `sap.f.DynamicPageTitle` classes now introduce a new `backgroundDesign` property which has three background options - `Solid`, `Transparent`, or `Translucent`. For the new property to be supported correctly when using the dynamic header in `sap.uxap.ObjectPageLayout`, a new `backgroundDesignAnchorBar` property is added to `sap.uxap.ObjectPageLayout`, which is used to control the background color of the `sap.uxap.AnchorBar` through its own newly added `backgroundDesign` property.For more information, see the *API Reference* for [`sap.f.DynamicPageHeader`](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPageHeader), [`sap.f.DynamicPageTitle`](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPageTitle), [`sap.uxap.ObjectPageLayout`](https://openui5.hana.ondemand.com/#/api/sap.uxap.ObjectPageLayout), and [`sap.uxap.AnchorBar`](https://openui5.hana.ondemand.com/#/api/sap.uxap.AnchorBar).

-   `sap.f.FlexibleColumnLayout`: The control now supports reveal effect animation to ensure smooth performance when a new column is opened or column width is changed.For more information, see the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.f.FlexibleColumnLayout).

-   `sap.f.semantic.SemanticPage`:

-   The `titleExpandedHeading` and `titleSnappedHeading` aggregations are now available for the `sap.f.semantic.SemanticPage` class, and you can display different content in the expanded and collapsed states of the page header.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.semantic.SemanticPage/aggregations).

-   The `areaShrinkRatio` property is now available for the `sap.f.semantic.SemanticPage` class. The property assigns shrinking ratios to the title areas \(Heading, Content, Actions\) of the `SemanticPage`. The greater value a section has, the faster it shrinks when the screen size is reduced.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.semantic.SemanticPage/controlProperties).

-   With the use of the new `sapFSemanticPageAlignContent` CSS class, you can now vertically align the content in the `SemanticPage` header and page content areas.

-   `sap.m.App`: The `mobileWebAppCapable` property is now available. It determines whether the `sap.m.App` is displayed without an address bar when opened from an exported home screen icon on a mobile device.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.App/controlProperties).

-   `sap.m.CheckBox`: The new `partiallySelected` property now allows the `CheckBox` control to be rendered as partially selected.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.CheckBox/controlProperties) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.CheckBoxTriState/preview).

-   `sap.m.ColorPalette`:

-   The tooltips of the predefined colors have been formatted in order to be more easily recognizable by users. Now they start with a capital letter, and there are intervals between the words, for example "indianred" has been changed to "Indian Red". For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.ColorPalette/preview).

-   The keyboard navigation has been improved by implementing a more intuitive use of the *Up*, *Down*, *Home*, and *End* keys. In terms of navigation, the color swatch items are treated as columns. For example, if the focus is on the first or on the last item, pressing *Up* or *Down* will move the focus respectively to the *Default Color* or *More Colors* button. *Home* moves the focus to the first color in the row, to the first color in the container, or to the *Default Color* button. *End* moves the focus to the last color in the row, to the last color in the container, or to the *More Colors* button. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.ColorPalettePopover/preview).

-   `sap.m.DateTimePicker`: The Time Picker is now vertically aligned with the Calendar for better user experience. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.DateTimePicker/preview).

-   `sap.m` library for `List` and `Tree` controls: The new `sticky` property is now also available for these controls \(in `sap.m.ListBase`\). It enables the column headers, infobar, and toolbar to remain in a fixed position at the top of the page during vertical scrolling. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase/controlProperties) for the `sticky` property and the [`ListToolbar` Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.ListToolbar/preview) as well as the [`TreeExpandMulti` Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.TreeExpandMulti/preview).

> Note:  
> The `sticky` property is not supported in all browsers. For more information about browser limitations, see the [API Reference: `sap.m.ListBase`](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase).

-   `sap.m.MessagePopover/sap.m.MessageView`: The `sap.m.MessageItems` that are aggregated in these controls have a new property - `activeTitle`. If set to `true`, the item’s title will be rendered as a link. Then, an event handler function should be provided for the `activeTitlePress` event, which is an event fired by the control when an active item title is pressed. This allows application developers to link a message in the control to the originating UI element in the application and, for example, automatically scroll to it. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.MessagePopoverMessageHandling/preview).

-   `sap.m.MultiComboBox`: The autocomplete functionality is available in the `sap.m.MultiComboBox` control. By default, the autocomplete option works with the "**starts with**" logic for every word in the list item, regardless of the filtering of the items. If a matching item is already selected, it will not trigger the autocomplete.

-   `sap.m.MultiComboBox/sap.m.ComboBox`: The default filtering function has been changed from "**starts with**" to "**starts with per term**". You can also use a custom filtering function by providing it to the `setFilterFunction` method. In this case, the highlighting will also switch back to the default "**starts with per term**".

-   `sap.m.MultiComboBox/sap.m.MultiInput`: All overflowing tokens are now available in a separate popover indicated with an *N-more* label, which serves as an opening trigger. This behavior is used to replace the multi-line mode for both controls, which is now deprecated.

     ![](loioa9a6a77a29c547feb1a9859636e05632_HiRes.png) 

-   `sap.m.OverflowToolbar`: Shrinking of controls is now enabled. For the new functionality to work, each control should have the `OverflowToolbarLayoutData` with the `shrinkable` property set to `true` and a specified `minWidth`. This way the control will first shrink to `minWidth` and then, if there is still not enough place, it will move to the overflow area.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.OverflowToolbarSimple/preview).

-   `sap.m.P13nFilterPanel`: You can now search for an empty string in the filter conditions of the personalization dialog . For example, you can search for all sales orders that do not contain supplier information by choosing *empty* from the dropdown menu. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.comp.sample.smartfilterbar.example1/preview).

-   `sap.m.PlanningCalendar`: The background color of the week numbers has been updated to more clearly display which parts of the date navigation of the Planning Calendar are clickable.

-   `sap.m.SelectDialog`: A *Clear* button has been added to allow you to clear your selection with one click. The button is always positioned at the top right-hand corner of the `sap.m.SelectDialog`. Its visibility is handled by the `showClearButton` property. By default, the property is set to `false`, and the button is not visible.

-   `sap.m.TableSelectDialog`:
    -   The column headers and the info toolbar are now sticky, which means that they remain fixed on top when scrolling. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.TableSelectDialog) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.TableSelectDialog/preview).

        > Note:  
        > The `sticky` property is not supported in all browsers. For more information about browser limitations, see the [API Reference: `sap.m.ListBase`](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase).

    -   The *Reset* button is replaced by a *Clear* button. The name has been changed to reflect better the functionality of the button which is to clear a selection made in the Table Select Dialog. The control also has a new `showClearButton` property that allows you to choose whether you want the button to be visible or not. Its default value is `false`. To display the button, set the property to `true`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.TableSelectDialog) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.TableSelectDialog/preview).

-   `sap.m.TimePicker`: The sliders are now vertically centered for better user experience. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.TimePicker/preview).

-   `sap.ui.layout.form`: You can now use the `Switch` control in all the forms that are editable. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Switch).

-   `sap.ui.model.base.ManagedObjectModel`: You can now use the model for data binding to the properties and aggregations of your managed objects,especially your controls. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.base.ManagedObjectModel).

-   `sap.ui.unified.Calendar`:

-   Colors are adjusted to make a clearer distinction between working and nonworking days in `sap.ui.unified.Calendar` and in `sap.ui.unified.CalendarLegend`. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.unified.sample.CalendarSpecialDaysLegend/preview).

-   A newly introduced sample demonstrates the recommended usage of the deselection logic when the calendar is in single selection mode. The implementation of this logic allows the app to support deselection of dates so that the user can deselect a previously selected date. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.unified.sample.CalendarDateDeselection/preview).

-   A new `weekNumberSelect` event is introduced which allows you to select a complete week by clicking on the week number. This function works for Gregorian calendars only and if `intervalSelection` is set to `true`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.unified.Calendar) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.unified.sample.CalendarSingleIntervalSelection/preview).

-   `sap.ui.unified.ColorPicker`: The new `displayMode` property determines how the control will be displayed. There are three display options - `default`, `large`, and `simplified`. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.unified.sample.ColorPicker/preview). 

-   `sap.uxap.ObjectPageLayout`:

    -   The `sap.uxap.AnchorBar` has new functionality for submenu navigation. When activating an anchor/button from the main navigation, it now scrolls directly to the corresponding section.

    -   UI Adaptation is enabled for the `sap.uxap.ObjectPageHeaderActionButton` control with the possible actions *Hide*, *Reveal*, and *Rename*.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.uxap.sample.ObjectPageHeaderActionButtons/preview) and activate UI Adaptation using the wrench key button.

    -   The `sap.f.DynamicPageHeader` and `sap.f.DynamicPageTitle` classes now introduce a new `backgroundDesign` property which has three options - `Solid`, `Transparent`, or `Translucent` background. For the new property to be supported correctly when using the dynamic header in `sap.uxap.ObjectPageLayout`, a new `backgroundDesignAnchorBar` property is added to `sap.uxap.ObjectPageLayout`, which is used to control the background color of the `sap.uxap.AnchorBar` through its own newly added `backgroundDesign` property.For more information, see the *API Reference* for [`sap.f.DynamicPageHeader`](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPageHeader), [`sap.f.DynamicPageTitle`](https://openui5.hana.ondemand.com/#/api/sap.f.DynamicPageTitle), [`sap.uxap.ObjectPageLayout`](https://openui5.hana.ondemand.com/#/api/sap.uxap.ObjectPageLayout), and [`sap.uxap.AnchorBar`](https://openui5.hana.ondemand.com/#/api/sap.uxap.AnchorBar).


***

<a name="loiob28edde1f4ad425d9247f3bbcdc5d9b7__section_z2h_fh5_zcb"/>

### Documentation Changes and Tutorials

***

#### New QUnit/OPA Testing Recommendations

We have updated our recommendations for QUnit and OPA tests in the *Walkthrough* tutorial, the *Testing* tutorial, and in the *Demo Apps*. The tests are now in line with the latest best practices for the unit/integration test setup and no longer use synchronous APIs. For more information, see the following sections in our *Walkthrough* tutorial:

-   [Step 28: Unit Test with QUnit](Step_28_Unit_Test_with_QUnit_e1ce1de.md)

-   [Step 29: Integration Test with OPA](Step_29_Integration_Test_with_OPA_9bf4dce.md)


***

#### Alignment with SAP Fiori 2.0 Design Concepts

We have updated our *Master-Detail* template as well as our *Browse Orders* demo app. They now adhere to the SAP Fiori 2.0 guidelines and use the flexible column layout \(`sap.f.FlexibleColumnLayout`\) instead of the split app pattern. For more information, see:

-   [Master-Detail Template](Master-Detail_Template_8ed9339.md)

-   [Master-Detail Demo App](https://openui5.hana.ondemand.com/test-resources/sap/m/demokit/master-detail/webapp/test/mockServer.html)
-   [Browse Orders Demo App](https://openui5.hana.ondemand.com/test-resources/sap/m/demokit/orderbrowser/webapp/test/mockServer.html)

***

<a name="loiob28edde1f4ad425d9247f3bbcdc5d9b7__section_r5v_3h5_zcb"/>

### Demo Kit Improvements

Until now the *API Reference* tree displayed by default all APIs including deprecated ones. Now we've added an *Include deprecated* checkbox above the tree that allows you to choose whether to see the full list. If it's selected, the deprecated items are displayed in the tree with the label *Deprecated* so you can easily identify them without opening each class.

 ![](loio6d95e67e41c041588ce453ca5ea8e25e_HiRes.png) 

