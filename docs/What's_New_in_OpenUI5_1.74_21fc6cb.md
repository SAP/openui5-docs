<!-- loio21fc6cb77b0c44aab55f045812e69c98 -->

| loio |
| -----|
| 21fc6cb77b0c44aab55f045812e69c98 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/21fc6cb77b0c44aab55f045812e69c98) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/21fc6cb77b0c44aab55f045812e69c98)</div>

## What's New in OpenUI5 1.74

With this release OpenUI5 is upgraded from version 1.73 to 1.74.

***

<a name="loio21fc6cb77b0c44aab55f045812e69c98__section_yxw_pxt_zcb"/>

### New Features

|**Test Recorder**

The Test Recorder tool is now part of the OpenUI5 framework and is available in all browsers. Use it in any OpenUI5 app to inspect the rendered user interface, view the control properties, and get hints about writing tests. The tool is aligned with the two official OpenUI5 testing tools – OPA5 and UIVeri5.

 ![](loio639a7041dc2740c2b9f0183a7aee41bb_HiRes.png) 

For more information, see [Test Recorder](Test_Recorder_2535ef9.md).

|

***

<a name="loio21fc6cb77b0c44aab55f045812e69c98__section_qwl_pb5_zcb"/>

### Improved Features

|**`Card Explorer`**

We have enhanced the functionality to download samples from the Card Explorer, and now there are 3 optional file formats available: JSON, ZIP, and CARD.For more information, see [Card Explorer](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/index.html).

|
|**Navigation in Nested Components**

In recent releases, the capabilities to [Navigate with Nested Components](Navigate_with_Nested_Components_8e9d6e4.md) were enhanced significantly. In addition to the available documentation, a [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.core.routing.Router/sample/sap.ui.core.sample.RoutingNestedComponent) has been added to showcase some fundamental possibilities of using components to structure applications and how to interconnect them via routing. 

|
|**Negative Predefined CSS Margin Classes**

We’ve introduced the following negative CSS margin classes to help you align controls that have their own default margins:

-   `sapUiTinyNegativeMarginBeginEnd`

-   `sapUiSmallNegativeMarginBeginEnd`

-   `sapUiMediumNegativeMarginBeginEnd`

-   `sapUiLargeNegativeMarginBeginEnd`


For more information, see [Using Predefined CSS Margin Classes](Using_Predefined_CSS_Margin_Classes_777168f.md)and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.core.StandardMargins/sample/sap.m.sample.StandardNegativeMarginsTwoSided).

|
|**Responsive Padding Enablement**

We've introduced responsive paddings to the `sap.m.IconTabBar`, `sap.m.ObjectHeader`, and `sap.m.TabContainer` controls. For more information, see [Enabling Responsive Paddings According to the Control Width](Enabling_Responsive_Paddings_According_to_the_Control_Width_3b718b5.md).

|
|**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   The `autoExpandSelect:true` model setting has been enhanced for property bindings that are added later.

-   We have added the `sap.ui.model.v4.ODataListBinding.getDownloadUrl` method.
-   `sap.ui.model.v4.AnnotationHelper.format` can now be used for operation parameters.
-   For messages returned in error responses of operation calls, targets pointing to operation parameters are now parsed correctly.
-   The `sap.ui.model.v4.Context.setProperty` method can be used to set properties locally on the client by specifying `null` as the `groupId`. The set value is then not included in PATCH and POST requests to create the new entity.
-   Annotation targets for \(overloaded\) bound operations in 4.01 Format are also supported in value list metadata.

> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double-check the detailed documentation of the features, as certain parts of a feature may be missing. While we aim to be compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(such as tree binding\). This also applies to controls such as `TreeTable` and `AnalyticalTable`, which are not supported in combination with the OpenUI5 OData V4 model. The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

|

***

<a name="loio21fc6cb77b0c44aab55f045812e69c98__section_rqn_wd5_zcb"/>

### Improved Controls

|**`sap.m.Avatar`**

We've added *remove* and *reveal* actions in the `Avatar` design-time metadata. Now, the control can be removed and revealed when using UI adaptation at runtime.For more information, see the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.m.Avatar/sample/sap.m.sample.Avatar).

|
|**`sap.m.ColorPalette`**

We have introducted a *Recent Colors* section, showing the last 5 recently used colors. This feature is enabled by default, making it is easier to find and select the exact colors. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ColorPalette) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ColorPalette/sample/sap.m.sample.ColorPalettePopover).

|
|**`sap.m.DateRangeSelection`**

We have introduced the ability to select month and year ranges. This improves the user experience when only a month or a year range has to be selected, and is defined by the `displayFormat` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.DateRangeSelection) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.DateRangeSelection/sample/sap.m.sample.DateRangeSelection).

|
|**`sap.m.List, sap.m.Table, sap.m.Tree`**

The busy indicator is now displayed in the center of the visible area of the UIs of these controls and is no longer vertically centered and therefore not always visible. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.List/sample/sap.m.sample.ListDeletion).

|
|**`sap.m.NavContainer`**

In version 1.69, the default value for the `defaultTransitionName` property was visually updated to behave as a slide & fade animation and the classic slide animation was no longer an option. Now, we've added the previous slide behavior as a new type of transition. To use it, set the `defaultTransitionName` property to `baseSlide`.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.NavContainer) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.NavContainer/sample/sap.m.sample.NavContainer).

|
|**`sap.m.NotificationListItem`**

The avatar background color can now be managed by the application developer using the new `authorAvatarColor` property. Now, if any of the `authorPicture` or `authorInitials` properties are not set, the default icon will not be displayed. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.NotificationListItem) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.NotificationListItem/sample/sap.m.sample.NotificationListItem).

|
|**`sap.m.plugins.DataStateIndicator`**

This plugin for the table controls \(`sap.m.List, sap.m.Table, sap.ui.table.Table`\) allows you to implement binding-related messages and show them on the UI using a message strip. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.plugins.DataStateIndicator) 

|
|**`sap.m.Select`**

With the new `required` property, you can now indicate whether user input is required. This property is helpful for accessibility purposes when a single relationship between the field and a label can't be established, for example, when one label exists for multiple fields.For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Select).

|
|**`sap.m.StandardListItem`**

The new `infoStateInverted` property changes the rendering behavior of the information state and information text. If it is set to `true`, the color defined by the `infoState` property is then shown as the background color of the information text. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.StandardListItem) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.StandardListItem/sample/sap.m.sample.StandardListItemInfoStateInverted).

|
|**`sap.m.Table`**

A more comprehensive message text is now shown if no data is available because all table columns are hidden. For more information, see the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.Table/sample/sap.m.sample.TablePerso).

|
|**`sap.m.ViewSettingsDialog`**

We have introduced a new button to display only the selected items in the filter tab, and to hide items that are not selected. This button works in combination with the Search field, so the displayed items are both filtered by title and selection. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ViewSettingsDialog) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ViewSettingsDialog/sample/sap.m.sample.ViewSettingsDialog).

|
|**`sap.m.Wizard`**

We have enhanced the `sap.m.Wizard` control for better integration in the `sap.f.DynamicPage`. In order to make use of it, you need to make certain configurations. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.Wizard). 

|
|**`sap.tnt.InfoLabel`**

We have introduced the option to add an icon to the `sap.tnt.InfoLabel` content. It is defined by the new `icon` property. For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.tnt.InfoLabel) and the [Sample](https://openui5.hana.ondemand.com/#/entity/sap.tnt.InfoLabel/sample/sap.tnt.sample.InfoLabel).

 ![](loiocadac6c2a6e74ac18c574ee7f3b4b0df_LowRes.png) 

|
|**`sap.ui.integration.widgets.Card`**

-   A new experimental Calendar Card type is now available . Its purpose is to give an overview of a single entity \(a person, for example\). It consists of an interactive calendar, legend, and a schedule. For more information, see [Calendar Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/calendar) in the Card Explorer.
-   We have enabled Data Sources to be used in the descriptor for `sap.ui.integration.widgets.Card`. Data Sources are named and reusable manifest entities that hold configuration settings for services. Referenced using special double-bracketed syntax, they are used to construct data request URLs. Data Sources are defined in the `sap.app` part of the manifest. For more information, see [Data Sources](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/dataSources) in the Card Explorer.
-   We have introduced new number formatters to represent the data on the UI in human-readable format. Now we have predefined number formatters for:

    -   Currency
    -   Date and Time
    -   Floating-point numbers
    -   Integers
    -   Percent
    -   Units of measurement
For more information, see [Card Formatters](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/formatters) in the Card Explorer.

-   We now also support objects as values for manifest parameters. Until now only string values were supported. For more information, see [Manifest Parameters](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/manifestParameters) section in the Card Explorer.
-   We have introduced a new experimental type of card - Adaptive Card. With this type of card, you can visualize and reuse cards created using the Microsoft Adaptive Cards specification and manifest, while achieving fully adapted SAP Fiori 3 user experience, out of the box. For more information, see [Adaptive Card](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/types/adaptive) in the Card Explorer.

|
|**`sap.uxap.ObjectPageLayout`**

You can now move the corresponding section numbers that are displayed in the `AnchorBar` when using UI adaptation at runtime.For more information, see the [Samples](https://openui5.hana.ondemand.com/#/entity/sap.uxap.ObjectPageLayout).

|

***

<a name="loio21fc6cb77b0c44aab55f045812e69c98__section_z2h_fh5_zcb"/>

### Documentation

|**Performance Checklist**

Ensuring that your OpenUI5 apps run fast is an important topic in application development. To support you in this task, we have improved the existing performance-related documentation as well as added some new information. Please use the comprehensive [Performance Checklist](Performance_Checklist_9c6400e.md) as a starting point for best practices to help you to review and speed up your OpenUI5 apps.

|

