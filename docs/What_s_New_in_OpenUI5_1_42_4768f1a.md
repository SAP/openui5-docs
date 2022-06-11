<!-- loio4768f1ac7f0645929b4e9ea9981bb65e -->

| loio |
| -----|
| 4768f1ac7f0645929b4e9ea9981bb65e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/4768f1ac7f0645929b4e9ea9981bb65e) | [demo kit latest release](https://sdk.openui5.org/topic/4768f1ac7f0645929b4e9ea9981bb65e)</div>

## What's New in OpenUI5 1.42

With this release, OpenUI5 is upgraded from version 1.40 to 1.42.

***

### Acceleration of OpenUI5 Cloud Deployment

We now deploy new versions of OpenUI5 earlier to `https://sdk.openui5.org/`. As soon as a new minor version is released, it will also be available there. Check the version overview at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html). To access a specific version, add the version number to the URL, for example, `https://sdk.openui5.org/1.40.11/`. For more information, see [Variant for Bootstrapping from Content Delivery Network](Variant_for_Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

***

### New Controls

-   `sap.f.DynamicPage`: This control is an SAP Fiori 2.0 control, designed to support the basic SAP Fiori 2.0 floorplans. You can use this control as a basic layout for an app. It consists of a title, a header, content area, and a floating footer. It offers dynamic behavior when scrolling, where part of the header snaps to the title. It offers additional capabilities, such as expanding or snapping the header when clicking on the title, pinning or unpinning the header so that it always stays expanded, and more.

      
      
    <a name="loio4768f1ac7f0645929b4e9ea9981bb65e__fig_art_k25_mx"/>Expanded Mode

     ![](images/loiob6e9d79a2c164db79b30b7fa57ec4317_LowRes.png "Expanded Mode") 

      
      
    <a name="loio4768f1ac7f0645929b4e9ea9981bb65e__fig_pvc_l25_mx"/>Collapsed Mode

     ![](images/loioa4eb96875f7d4d1faae0d40aa4b38c52_LowRes.png "Collapsed Mode") 

    There is an option for displaying a footer as a toolbar with additional actions. The footer is also known as a “floating footer”, as it appears to float above the content of the page. The benefit of the new footer look-and-feel is that it is easily recognized by the end user.

     ![](images/loio2f364cef44194cdca2e2ea99a343e8db_LowRes.png) 

    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.f.DynamicPage) and the [sample](https://sdk.openui5.org/entity/sap.f.DynamicPage).

-   `sap.m.LightBox`: The `LightBox` control is used to display an image in its original size. When the user clicks on a thumbnail, a `LightBox` containing the image opens in a new popup. The popup also contains a title and subtitle. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.LightBox) and the [sample](https://sdk.openui5.org/entity/sap.m.LightBox).

     ![](images/loio5a6da1afb5074d329263474f4afabc68_LowRes.png) 

-   `sap.m.Tree`: The `Tree` control provides a tree structure for displaying data in a hierarchy. Since it extends `sap.m.ListBase`, it provides many of the same features already known from `sap.m.List`. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Tree) and the [sample](https://sdk.openui5.org/entity/sap.m.Tree).


***

### Improved Controls

-   `sap.m.Carousel`: The `Carousel` control has two enhancements.

    -   The enumeration `CarouselArrowsPlacement` determines where the arrows will be placed \(on the sides of the content or on the sides of the page indicator\).

    -   The page indicator now shows numbers instead of bullets, when the number of items in the `Carousel` is above nine.


    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Carousel/methods/getArrowsPlacement) and the [sample](https://sdk.openui5.org/sample/sap.m.sample.CarouselWithDisplayOptions/preview). 

     ![](images/loioa698aa6c990b41458195603167aa70fe_LowRes.png) 

-   `sap.m.Combobox`: The `Combobox` control now automatically scrolls to the selected element, so that the user sees the element selected in the initial dropdown box, which may not be visible in large dropdown boxes.

-   `sap.m.FeedListItem`: The `FeedListItem` control now incorporates the `sap.m.FormattedText` control that allows HTML-formatted text to be displayed. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.FeedListItem) and the [sample](https://sdk.openui5.org/entity/sap.m.FeedListItem).

-   `sap.m.FlexBox`: The render type `Bare` has been added to the `FlexBox` control. It allows flex items to be rendered without a wrapping HTML tag. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.FlexRendertype) and the [sample](https://sdk.openui5.org/sample/sap.m.sample.FlexBoxRenderType/preview).

-   `sap.m.IconTabBar`: The `IconTabBar` control has two enhancements:

    -   `headerMode` has a new value called `Inline`. This mode displays the text and the count in one row.

    -   `showOverflowSelectList` can be enabled when you have a large number of tabs and cannot display them all at once. When this property is set, all tabs that cannot be shown are added to an overflow list.


    For more information, see the API Reference for [sap.m.IconTabHeaderMode](https://sdk.openui5.org/api/sap.m.IconTabHeaderMode) and [sap.m.IconTabBar.getShowOverflowSelectList](https://sdk.openui5.org/api/sap.m.IconTabBar/methods/getShowOverflowSelectList), and the samples [Overflow Select List](https://sdk.openui5.org/sample/sap.m.sample.IconTabBarOverflowSelectList/preview) and [Inline Mode](https://sdk.openui5.org/sample/sap.m.sample.IconTabBarInlineMode/preview). 

-   `sap.m.MultiComboBox`: We have implemented touch support on mobile devices for the `MultiComboBox` control. The behavior of the control is now aligned with other similar controls such as `Select` and `ComboBox`.

-   `sap.m.Slider` and `sap.m.RangeSlider`: These controls have two new properties:

    -   `inputsAsTooltips` adds an input field above the slider handle. This enables users to directly enter the desired `Slider` value.

    -   `showAdvancedTooltip` when enabled, the handle will always display the slider value as a tooltip.


    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Slider/methods/getInputsAsTooltips) and the [sample](https://sdk.openui5.org/sample/sap.m.sample.Slider/preview). 

-   `sap.m.ObjectListItem` and `sap.m.ObjectHeader`: These controls can now display all markers of type `sap.m.ObjectMarker` with the use of a new `marker` aggregation. The possible values are `Flagged`, `Favorite`, `Locked`, `Draft`, and `Unsaved`. For more information, see the API Reference for [sap.m.ObjectListItem](https://sdk.openui5.org/api/sap.m.ObjectListItem) and [sap.m.ObjectHeader](https://sdk.openui5.org/api/sap.m.ObjectHeader), and the samples [Object List Item - Markers Aggregation](https://sdk.openui5.org/sample/sap.m.ObjectListItemMarkers/preview) and [Object Header - Markers Aggregation](https://sdk.openui5.org/sample/sap.m.sample.ObjectHeaderMarkers/preview).

-   `sap.m.ObjectMarker`: With the use of a new `additionalInfo` property, you can now add descriptive text next to the displayed marker, for example *Locked by User*. For more information, see [API Reference](https://sdk.openui5.org/api/sap.m.ObjectMarker).

-   `sap.m.UploadCollection`: The `UploadCollection` control has the following new properties:

    -   `uploadButtonInvisible`: With this new property, you can make the *Upload* button invisible in your application if you want to prevent the user from uploading a file, either in the instant upload or in the upload pending scenario of the `UploadCollection` control.

    -   `terminationEnabled`: With this new property, you can make the *Terminate Upload* button invisible in your application if you want to prevent the user from terminating an instant upload in the `UploadCollection` control.


    For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.UploadCollection) and the [sample](https://sdk.openui5.org/entity/sap.m.UploadCollection). 

-   `sap.m.ViewSettingsDialog`: You can now customize the search behavior in the filter details page with the use of the new property `filterSearchOperator` with the possible values `Contains`, `Equals`, and `Starts With`. There is also a new method `setFilterSearchCallback` that can set a custom filter callback if the predefined filters are not sufficient. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.ViewSettingsDialog) and the [sample](https://sdk.openui5.org/sample/sap.m.sample.ViewSettingsDialogCustomFilterDetails/preview).

-   `sap.ui.layout.BlockLayout`: The `BlockLayout` control has been updated to comply to the new SAP Fiori 2.0 design. The color schemes for `Mixed`, `Bright`, and `Accent` have been updated to the new design. For more information, see the [sample](https://sdk.openui5.org/sample/sap.ui.layout.sample.BlockLayoutDefault/preview).

-   `sap.uxap.ObjectPageLayout`: You can set the footer with the footer aggregation and toggle its visibility using the `showFooter` property. The footer is slightly transparent, showing the underlying content and is used to provide additional actions. This aligns the `Object Page` control with the SAP Fiori 2.0 design concepts. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageLayout/methods/getFooter) and the [sample](https://sdk.openui5.org/sample/sap.uxap.sample.ObjectPageOnJSON/preview).


***

### Behavior-Driven Development with Gherkin

OpenUI5 now supports behavior-driven development \(BDD\) with Gherkin. Gherkin allows you to write feature files that get translated into executable regression tests. So you can keep your documentation and specification in sync with the actual implementation in your application. It integrates seamlessly with OPA5 and you can completely reuse your OPA and page objects. You only need to translate an OPA journey to a feature file. For more information, see [Behavior-driven Development with Gherkin](Behavior_driven_Development_with_Gherkin_45ac9f1.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.test.gherkin), and the [sample](https://sdk.openui5.org/entity/sap.ui.test.gherkin). 

***

### Improved Features

***

#### OpenUI5 OData V4 Model

The new version of the OpenUI5 OData V4 model introduces the following features:

-   Deleting entries

-   Loading annotation files


> ### Restriction:  
> Due to the limited feature scope of this version of the OpenUI5 OData V4 model, check that all required features are in place before developing applications. Double check the detailed documentation of the features, as certain parts of a feature may be missing although you might expect these parts as given. While we aimed at being compatible with existing controls, some controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model \(like tree binding\). The interface for applications has been changed for easier and more efficient use of the model. For a summary of these changes, see [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

For more information, see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://sdk.openui5.org/api/sap.ui.model.odata.v4), and the [sample](https://sdk.openui5.org/entity/sap.ui.model.odata.v4.ODataModel) in the Demo Kit.

***

#### One Page Acceptance Tests \(OPA5\)

-   `waitFor` statements in actions and automatic waiting: When writing custom actions you can now add `waitFor` statements inside the `action` and they will be executed before the `success` callback. This allows you to have complex reuse actions that interact with multiple controls.

    There is a new entry `autoWait` in the `sap.ui.test.Opa.config`.

    ```
    Opa5.extendConfig({
            autoWait: true
        });
    
    ```

    If it is set to `true`, every `waitFor` statement will execute extra checks before executing an `action` or `success` to see if the UI is in a stable state. For example, there is automatic waiting for `XMLHttpRequests` \(request to your server\). OPA will not continue before those requests are done. It also works with a mock server that has a delay. For more information, see [API Reference: `sap.ui.test.Opa5.waitFor`](https://sdk.openui5.org/api/sap.ui.test.Opa5/methods/waitFor).

-   New matcher `sap.ui.test.matchers.I18NText`: The `I18NText` matcher checks if a control property has the same value as a text from an i18n file. It also checks that the key is in the property file. This allows you to catch all your typos and make your tests independent from the browsers language. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.ui.test.matchers.I18NText) and the [sample](https://sdk.openui5.org/entity/sap.ui.test.matchers.I18NText).

-   Improved troubleshooting: When OPA encounters a timeout, it collects the most recent logs logged under the `sap.ui.test` namespace and puts it in the test's failure message. All parameters of the `waitFor` method are now validated up front to immediately cause the test to fail if there is a typo.

-   Slowing down the execution: You can now use the new URL parameter `paExecutionDelay` to pass on `myOpaTest.qunit.html?opaExecutionDelay=700` to every OPA test. This means there will be a pause for 700 milliseconds before a new `waitFor` statement is executed. It helps when troubleshooting or if you want to watch OPA clicking through your application because it might be too fast to follow. There is also a dropdown list with three predefined values in your QUnit site.

     ![](images/loio08dd0bebf10c4561b1ee146f4ac5a6ab_LowRes.png) 


***

#### Navigation and Routing

You can now use the `title` property for targets and a `titleTarget` for routes in the routing configuration to change the displayed title of an app. For more information, see [Using the title Property in Targets](Using_the_title_Property_in_Targets_1238d70.md).

***

#### New Icons

We have 10 new icons - check out the [Icon Explorer](https://sdk.openui5.org/test-resources/sap/m/demokit/iconExplorer/webapp/index.html) in the Demo Kit for details.

***

### Deprecation

-   The `HeaderCell` and `HeaderCellItem` controls have been deprecated with this release in `sap.suite.ui.commons` library. Please use other container controls instead \(such as `sap.m.VBox` or `sap.m.HBox`\).

-   The `prefetchNavigationTargets` property and the `prefetchDone` event of `sap.ui.comp.navpopover.SemanticObjectController`, which is used in the `sap.ui.comp.navpopover.SmartLink` control, have been deprecated since the navigation target behavior for the `SmartLink` control has been changed to improve performance.


***

### Documentation Changes

The documentation for QUnit testing has been updated and aligned with the new QUnit 2.0 API. All code samples have been replaced to match the new syntax: [Unit Testing with QUnit](Unit_Testing_with_QUnit_09d145c.md)

We have updated the following tutorials:

-   [Data Binding](Data_Binding_e531093.md)

-   [Walkthrough](Walkthrough_3da5f4b.md)


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

[What's New in OpenUI5 1.46](What_s_New_in_OpenUI5_1_46_4cf0986.md "With this release, OpenUI5 is upgraded from version 1.44 to 1.46.")

[What's New in OpenUI5 1.44](What_s_New_in_OpenUI5_1_44_05ce1dc.md "With this release, OpenUI5 is upgraded from version 1.42 to 1.44.")

[What's New in OpenUI5 1.40](What_s_New_in_OpenUI5_1_40_e659bd2.md "With this release, OpenUI5 is upgraded from version 1.38 to 1.40.")

[What's New in OpenUI5 1.38](What_s_New_in_OpenUI5_1_38_6a875f9.md#loio6a875f998994489483e8085705347d72 "With this release, OpenUI5 is upgraded from version 1.36 to 1.38.")

