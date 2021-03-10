<!-- loio2a70354a2a38492a873333edc4b9a303 -->

| loio |
| -----|
| 2a70354a2a38492a873333edc4b9a303 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/2a70354a2a38492a873333edc4b9a303) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/2a70354a2a38492a873333edc4b9a303)</div>

## What's New in OpenUI5 1.60

With this release OpenUI5 is upgraded from version 1.58 to 1.60.

***

<a name="loio2a70354a2a38492a873333edc4b9a303__section_yxw_pxt_zcb"/>

### New Features

***

#### Hyphenation for Text Controls

OpenUI5 now allows you to hyphenate words in multiline texts when controls are in wrapping mode. You can enable hyphenation through the `wrappingType` property for the `sap.m.Text`, `sap.m.Title`, and `sap.m.Label` text controls, or you can use the API of the `sap.ui.core.hyphenation.Hyphenation` class directly.

 ![](loio8a74466e5393433c856234e3a40f126a_HiRes.png) 

> Caution:  
> The hyphenation feature uses third-party and browser-native tools. We are not responsible for any inconsistencies or incorrect grammar. Also, the variety of supported languages is outside the scope of our control and may be subject to future changes.

For more information, see [Hyphenation for Text Controls](Hyphenation_for_Text_Controls_6322164.md), the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.core.sample.HyphenationAPI/preview), and the *API Reference* for [`sap.m.Text`](https://openui5.hana.ondemand.com/#/api/sap.m.Text), [`sap.m.Title`](https://openui5.hana.ondemand.com/#/api/sap.m.Title), [`sap.m.Label`](https://openui5.hana.ondemand.com/#/api/sap.m.Label), and [`sap.ui.core.hyphenation.Hyphenation`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.hyphenation.Hyphenation).

***

#### Support Assistant

**System Presets**

In addition to the custom rule presets that users can create, we've introduced system-defined presets. They constitute a selection of rules related within the context of a certain scenario, functional area, or other aspects of the application UI that can be checked using support rules. System presets are part of the Support Assistant code and appear by default for all users. They cannot be deleted but can be modified and exported as regular presets.

The first system preset we've introduced is for accessibility-related rules.

 ![](loioae05ff406b4e4fcc83d01eaf896e7ae4_HiRes.png) 

For more information, see [Rules Management](Rules_Management_3fc864a.md).

**Rule Presets in the Analysis Report**

The Analysis Report now includes information about the rule preset used during the analysis. This information is also available in the downloadable HTML report and in all JSON formats that the API supports, through `jQuery.sap.support.getAnalysisHistory()` and `jQuery.sap.support.getFormattedAnalysisHistory()`.

We have also improved the design of the report itself.

 ![](loiod44c5ac7009b49d49441abb28ddf93c9_HiRes.png) 

For more information, see [Analysis Report](Analysis_Report_29bcdec.md).

**Support Assistant API**

The `jQuery.sap.support.analyze` method of the Support Assistant API can now accept a rule preset and use it to run an analysis as an alternative to manually listed rule selection. For more information, see [Support Assistant API](Support_Assistant_API_a34eb58.md).

***

#### UI5 Evolution

UI5 evolution represents fundamental improvements that have been introduced into the framework in an ongoing effort to advance OpenUI5, so that it allows applications to run faster and code to become more modular. By embracing web standards and emerging technologies, OpenUI5 continues to be a future-proof, enterprise-proven solution. These innovations are provided in a largely compatible way, encouraging developers to actively support and leverage the new capabilities.

**Modular Core**

Existing modules in the modulare core have been reworked to follow the AMD-like \(asynchronous module definition\) syntax of OpenUI5, which ensures that modules and their dependencies can be loaded and evaluated asynchronously. The Asynchronous Module Definition \(AMD\) specifies a mechanism for defining modules so that the module and its dependencies can be loaded asynchronously. It allows you to avoid accessing modules via global variables and enforces a strict dependency declaration. The documentation has been enhanced accordingly and also made more prominent.For more information, see [Modules and Dependencies](Modules_and_Dependencies_91f23a7.md).

The core part of the framework has improved its modular structure by leveraging OpenUI5's AMD-like features such as [sap.ui.define](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.define) and [sap.ui.require](https://openui5.hana.ondemand.com/#/api/sap.ui/methods/sap.ui.require). Already starting with 1.58, the former `jQuery.sap` modules were replaced by new, more granular modules. The new modules are separated either into a regular browser-dependent "UI" layer or into a "base" layer that is independent from the browser-native API and the DOM.For more information, see [Adapting to the Modularization of the Core](Adapting_to_the_Modularization_of_the_Core_b8fdf0c.md).

Several mechanisms have been introduced to allow existing applications to continue to run without changes. Nevertheless, all OpenUI5 projects should start to migrate their code and leverage the new core modules to get rid of the deprecated modules and benefit from current or upcoming improvements, especially towards the AMD-like syntax of OpenUI5.

A comprehensive overview shows how you can replace legacy `jQuery.sap` modules and `jQuery` extensions with new modules or native browser APIs. For more information, see [Legacy jQuery.sap Replacement](Legacy_jQuery.sap_Replacement_a075ed8.md). The Support Assistant also comes with new rules to help identify legacy code, and best practices for module definition and asynchronous loading are also provided.For more information, see [Best Practices for Loading Modules](Best_Practices_for_Loading_Modules_00737d6.md).

**Asynchronous API**

In order to benefit from asynchronous behavior and to avoid synchronous requests \(as browsers start to deprecate sync XHR\), future-proof OpenUI5 code should use asynchronous APIs. One important step to get there with your existing code is to replace synchronous factory functions, such as global functions in the `sap.ui` namespace, with asynchronous alternatives. Many asynchronous factories are now available via a consistent and elegant API. The documentation provides examples of former sync factories and their preferred async alternatives.For more information, see [Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md).

***

<a name="loio2a70354a2a38492a873333edc4b9a303__section_bkm_s15_zcb"/>

### New Controls

-   `sap.f.GridList`: A list-based control with grid layout capabilities. It is based on the `sap.m.ListBase` control, and it adds flexibility to configure different grid layouts. The layout used is based on the CSS display grid, and the control has a default configuration.

    ![](loioc43df4c27715425ba98a7a7a40e71fd4_HiRes.png)

    For more information, see [Grid Controls](Grid_Controls_32d4b9c.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.f.GridList), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.f.GridList).

-   `sap.ui.layout.cssgrid.CSSGrid`: A layout control, used to create full-page layouts or user interface elements. It is a two-dimensional layout based on the browser-native CSS display grid that handles both columns and rows. The control can be used together with `sap.m.FlexBox` which is the one-dimensional alternative for layouting.

    ![](loio2bdf9f5e96f44a2aa2bd626c9cabcbff_HiRes.png)

    For more information, see [Grid Controls](Grid_Controls_32d4b9c.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.cssgrid.CSSGrid), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.cssgrid.CSSGrid).

-   `sap.ui.unified.ColorPickerPopover`: A wrapper around the `sap.ui.unified.ColorPicker` control that allows it to be displayed as a popover or a dialog depending on the device. The `ColorPickerPopover` has the same properties as the `ColorPicker` control but it has two additional methods - `openBy` and `close` to control the popover. Another difference between the new control and the `ColorPicker` control is that there is no `liveChange` event, and the `change` event is fired only when the *Submit* button is pressed. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.unified.ColorPickerPopover) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.unified.sample.ColorPickerPopover/preview).

     ![](loioc983fe12e5f2461a9ca0f608d9e03415_LowRes.png) 


***

<a name="loio2a70354a2a38492a873333edc4b9a303__section_qwl_pb5_zcb"/>

### Improved Features

***

#### OpenUI5 OData V4 Model

The new version of the OpenUI5 OData V4 model introduces the following features:

-   Batch requests with `create`, `update`, and `delete` change operations for the same group ID are no longer sent in parallel. The next batch request waits for the previous request to return.

-   The path of a transient context changes to the key predicate path when the new entity is successfully submitted. The key predicate path can be used for binding the entity elsewhere.

-   If the same entity is returned by the operation, the binding parameter of a bound operation is automatically updated.

-   V4 Analytics: We now support grand total calculation without visual grouping.

-   We now support the `ValueList` annotation in addition to the `ValueListMapping` annotation.

-   `sap.ui.model.odata.v4.ODataListBinding#create`:

    -   When calling `sap.ui.model.odata.v4.ODataListBinding#create`, you no longer have to specify all properties that are used in the binding. If available, the binding provides the default values. If no default values are available, the binding provides null.

    -   The new parameter `bSkipRefresh` suppresses the refresh after the POST request.

-   We have introduced the new binding parameter `$$patchWithoutSideEffects` for context bindings, to avoid updating the UI with the data response of a PATCH request.


> Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported together with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).

***

#### Aggregation Forwarding for Composite Controls

Aggregation forwarding for composite controls now offers the following options:

-   Child controls in a public, forwarded aggregation are now automatically cloned by the framework together with the composite control.

-   You can now define forwarding from a single \(to-1\) to a multiple aggregation \(to-n\).

-   A control that has been forwarded will always have the same models as the ones available at the original location **before** the forwarding.

    For example, a model that a composite control developer sets on an inner control is not propagated to the child controls of this inner control if they have been moved there by aggregation forwarding. Instead, the models available at the original location of these child controls will be propagated to them.


For more information, see [Aggregation Forwarding](Aggregation_Forwarding_64a5e17.md).

***

#### Drag and Drop

Drag and drop is no longer experimental with this version.

> Note:  
> If you want to use drag and drop for a control, the control must allow drag and drop \(per definition in the metadata\), and you have to make the required settings in the relevant aggregation.

 For more information, see [Drag and Drop](Drag_and_Drop_3ddb6cd.md), the [API Reference: `dragDropConfig` aggregation](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Element/aggregations), and the [API Reference: `sap.m.ListBase`](https://openui5.hana.ondemand.com/#/api/sap.m.ListBase) \(control that allows drag and drop\).

***

<a name="loio2a70354a2a38492a873333edc4b9a303__section_rqn_wd5_zcb"/>

### Improved Controls

-   `sap.f.FlexibleColumnLayout`: A new sample now shows the control as an app with routing that displays different pages in the initial column. The first page is only displayed in `OneColumn` layout type. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.f.sample.FlexibleColumnLayoutWithFullscreenPage/preview).

-   `sap.m.Image`: То optimize app performance, we changed the default value of the `densityAware` property to `false`. App developers should enable this property only if the app provides the corresponding image versions for high-density devices.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Image/controlProperties).

-   `sap.m.MessageView`/`sap.m.MessagePopover`: A keyboard accelerator for the * Alt Enter * event has been added. Now, when the focus is on *item* with the `activeTitle` property set to `true`, and when the * Alt Enter * is triggered, the `activeTitlePress` callback is fired. Screen reader support was also improved. Information that the defined keyboard accelerators can be used for easier navigation has been provided to its users.

-   `sap.m.MultiComboBox`:

    -   We have implemented a dropdown list with a two-column layout. You can now use the `MultiComboBox` with a two-column layout to display additional information for your options. To enable this feature, you need to set the `showSecondaryValues` property to `true`. This feature was initially available only for the `ComboBox` and has now been enabled for the `MultiComboBox` as well. This property indicates whether the text values of the `additionalText` property of a `sap.ui.core.ListItem` are shown.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.MultiComboBoxTwoColumnsLayout/preview).

    -   We have introduced grouping in the suggestion list of `sap.m.MultiComboBox`. This feature allows you to easily group items by common characteristics and to display a header describing the characteristics for each group. If data binding is used, grouping is defined on the `Sorter` in data binding. Alternatively, a group header could be added programmatically, as an instance of `sap.ui.core.SeparatorItem` with `key` and/or `text` properties, by adding it to the `items` aggregation of the `sap.m.MultiComboBox` control.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.MultiComboBoxGrouping/preview).

-   `sap.m.Page`: We have made `sap.m.Page` a droppable area.

-   `sap.m.PlanningCalendar`: The `stickyHeader` property is no longer experimental.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar).

-   `sap.m.SearchField`: The live search function of the control was originally designed to trigger a backend call after each keystroke to retrieve partially-matching suggestions. Now, we have introduced a default delay of 400 ms before sending the searched data to the backend, to ensure better performance and optimal user experience. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.SearchFieldSuggestions/preview).

-   `sap.m.table`:

-   The `contextualWidth` property is now available in the responsive table which allows you to control the popin behavior based on the size of a container rather than a whole page. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Table/controlProperties) for the `contextualWidth` property and the [`ContextualWidthDynamic` Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.TableContextualWidthDynamic/preview) as well as the [`ContextualWidthStatic` Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.TableContextualWidthStatic/preview).

-   The `paste` event has been added to the responsive table. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Table/events/paste) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.TableEditable/preview).
-   `sap.m.UploadCollection`: The control's functionality has been unified, so the behavior is now more consistent, regardless of whether the `instantUpload` mode is enabled. With the new `beforeUploadTermination` event, you can adjust the control’s behavior when the file upload is terminated by the user before completion. If the default upload behavior is not applicable to your app, you can now also implement custom upload logic using the `CollectionUploader` class.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.UploadCollection).

-   `sap.m.ViewSettingsDialog`: Several visual improvements were implemented - the *OK* button is now displayed as emphasized and there is a better visual separation of the items displayed in the *Sort By*, *Filter By* and *Group By* tabs.For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.ViewSettingsDialog/preview).

-   `sap.ui.core.AccessibleLandmarkRole`: We have extended the `AccessibleLandmarkRole` enumeration with the roles Form and ContentInfo. These accessible landmarks could be applied to the container elements of `sap.m.Page`. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.AccessibleLandmarkRole).

-   `sap.ui.core.ValueState`: We have introduced `sap.ui.core.ValueState.Information` as a new semantic color value to the `ValueState` enumeration. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.core.ValueState) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.InputValueState/preview).

-   `sap.ui.table`: The `paste` event has been added to the grid table. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.table.Table/events/paste) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.table.sample.Basic/preview).

-   `sap.ui.unified.Calendar`:

-   **Week selection**: Users can now select/deselect all the days in a given week at once by choosing the week number or by pressing * SHIFT SPACE * on any day of the week.

-   **Range selection**: We introduced two more shortcuts - * SHIFT ENTER * and * SHIFT Left Mouse Button *. Both of them select/deselect all days between the two selected dates.

    For more information, see the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.unified.sample.CalendarMultipleDaySelection/preview).

-   `sap.uxap.ObjectPageLayout`: With the new `sapUxAPObjectPageSubSectionAlignContent` CSS class, you can now vertically align the content of the header with the content of the subsection. When using `sap.ui.layout.form.Form`, `sap.m.Panel`, `sap.m.Table`, and `sap.m.List` in the subsection content area of the `ObjectPageLayout`, if the content is not already aligned, you need to adjust the left text offset to achieve the vertical alignment. To do this, apply the `sapUxAPObjectPageSubSectionAlignContent` CSS class to them and set their `width` property to `auto` \(if not set by default\).

    ``` xml
    <Panel class="sapUxAPObjectPageSubSectionAlignContent" width="auto"></Panel>
    ```

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.uxap.ObjectPageSubSection/aggregations) and the [Sample](https://openui5.hana.ondemand.com/#/sample/sap.uxap.sample.ObjectPageLazyLoadingWithoutBlocks/preview).


***

<a name="loio2a70354a2a38492a873333edc4b9a303__section_z2h_fh5_zcb"/>

### Documentation Changes and Tutorials

***

#### Accessibility Improvements in Demo Apps and in the Walkthrough Tutorial

We have improved the accessibility of our demo apps. In addition, we have updated our *Walkthrough* tutorial and added a new step. Developers can improve the accessibility of their Walkthrough app by adding ARIA elements \(landmarks\). For more information, see [Step 38: Accessibility](Step_38_Accessibility_ff7cab1.md).

