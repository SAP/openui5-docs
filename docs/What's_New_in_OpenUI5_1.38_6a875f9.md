<!-- loio6a875f998994489483e8085705347d72 -->

| loio |
| -----|
| 6a875f998994489483e8085705347d72 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/6a875f998994489483e8085705347d72) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/6a875f998994489483e8085705347d72)</div>

## What's New in OpenUI5 1.38

With this release, OpenUI5 is upgraded from version 1.36 to 1.38.

In the following sections, we list the main new features and enhancements to OpenUI5. For a complete, detailed list of all new and enhanced functions, see: [Change Log](https://openui5.hana.ondemand.com/#releasenotes.html).

***

### Documentation Improvements

Thanks a lot to all of you who have used the Demo Kit feedback function! We have received lots of comments, many of which regarding our tutorials, and are continuously improving the documentation based on your findings.

Please carry on giving us your feedback: even though we cannot update the documentation straight away, your feedback will be considered in the next version!

New or reworked documentation chapters that are not mentioned in the following sections:

-   Chapter [Routing and Navigation](Routing_and_Navigation_3d18f20.md) is now updated and reworked.


***

### Deprecation

The following libraries are deprecated as of this version:

-   `sap.ui.commons`

-   `sap.ui.ux3`

-   `sap.makit`


The following themes are also deprecated as of this version:

-   `sap_ux`

-   `sap_platinum`

-   `sap_goldreflection`


For more information, see [Deprecated Themes and Libraries](Deprecated_Themes_and_Libraries_a87ca84.md).

***

### jQuery Upgraded to Version 2.2.3

jQuery has been upgraded to version 2.2.3. This upgrade may have an impact on apps developed with OpenUI5.

***

### New Features

-   We have 46 new icons, and some existing icons have been redesigned - check the [Icon Explorer](https://openui5.hana.ondemand.com/test-resources/sap/m/demokit/iconExplorer/webapp/index.html) in the Demo Kit for details.

-   **Multiple preprocessors for XML views**

    We have enhanced the XML view so that it is now capable of running more than one preprocessor per hook. Additionally, the new hook `viewxml` has been introduced. For more information, see [Preprocessing XML Views](Preprocessing_XML_Views_48b81b9.md).

-   **OpenUI5 OData V4 model**

    We are providing an initial version of the OpenUI5 OData V4 Model. This model supports the following:

    -   Read access

    -   Updating properties of OData entities via two-way-binding

    -   Operation \(function and action\) execution

    -   Grouping data requests in a batch request

    -   Server-side sorting and filtering

    > Restriction:  
    > This is the first version of the OpenUI5 OData V4 model. Due to its limited feature scope, we recommend you do not use this release to develop applications that are to be used in production systems. Please look at the detailed documentation of the features, as certain parts of a feature may be missing which you might expect as given. While our intention was to be compatible with existing controls, existing controls might not work due to small incompatibilities compared to `sap.ui.model.odata.(v2.)ODataModel`, or due to missing features in the model. Up to now, only limited tests with controls have been done with the OpenUI5 OData V4 model. The interface for applications has been changed to make usage of the model easier and more efficient. A summary of these changes is documented in the section [Changes Compared to OData V2 Model](Changes_Compared_to_OData_V2_Model_abd4d7c.md).

    For more information see [OData V4 Model](OData_V4_Model_5de13cf.md), the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4), and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.model.odata.v4.ODataModel).


***

### New Controls

-   **`sap.m.FormattedText`**: You can use this control to display formatted texts in HTML format.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.FormattedText) and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.m.FormattedText).

-   **`sap.m.MenuButton`**: The control opens a hierarchical menu and enables quick triggering of the last action of the menu item selected. In `Regular` mode it always opens the menu, whereas in `Split` mode it can be also used directly as a button to trigger the currently displayed menu item’s action. In `Split` mode it can display either the default menu item or the last selected one.

    |Regular Mode

|Split Mode

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>    </th>
			<th>--------------</th>
			<th>------------</th>
		</tr>
	</thead>
	<tbody>

			<td> 

![](loio3fb088782e4e49bab3f05920066794c1_HiRes.png) 
			</td>
		</tr>
	</tbody>
</table>

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.MenuButton) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.MenuButton/preview).

-   **`sap.m.ObjectMarker`**: The `ObjectMarker` control represents the status of an object with icon and/or text. It can be interactive \(as a link\) or non-interactive. It has the following predefined types:

-   `Flagged`

-   `Favorite`

-   `Draft`

-   `Locked`

-   `Unsaved`

    An object might have multiple `ObjectMarker`s at the same time but the editing states \(`Locked`, `Draft`, and `Unsaved`\) are mutually exclusive.

     ![](loio63be65114f584a01bda20eb866894ace_HiRes.png) 

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ObjectMarker) and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ObjectMarker).

-   **`sap.m.RangeSlider`** is a new input control that is used to select a range of values. The `RangeSlider` has two slider handles that can be moved along a predefined numerical range scale. This control extends the `sap.m.Slider` and introduces additional functionality.

     ![](loiod6a92b6c14db4bbab8d0a845489155e6_HiRes.png) 

-   `sap.m.StepInput`: The `StepInput` control allows the user to change the input value with a predefined step. The value can be changed using the increment/decrement buttons or keys on the keyboard. On the desktop, when using the keyboard [PgUp\] and [PgDn\] keys, the value increases/decreases two steps at a time.

     ![](loio40eb4db5863944c88839db0ff3d7e6cb_HiRes.png) 

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.StepInput) and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.m.StepInput).

-   **`sap.ui.layout.ResponsiveSplitter`** is a layout control that is used to visually divide the content of its parent. The control is responsive and can adjust its contents to any screen size. On smaller screens, pagination is used to allow navigation to all splitter panes.

     ![](loio542861b7dc7c452a994fe98beadf6d10_HiRes.png) 

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.ui.layout.ResponsiveSplitter) and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.ui.layout.ResponsiveSplitter)


***

### Improved Features

-    **One page acceptance test \(OPA\)**:

    The `Press` and `EnterText` actions now support a larger number of controls and can now be executed on embedded controls by specifying the control suffix. For more information, see the API Reference for [`Press`](https://openui5.hana.ondemand.com/#/api/sap.ui.test.actions.Press) and [`EnterText`](https://openui5.hana.ondemand.com/#/api/sap.ui.test.actions.EnterText) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.core.sample.OpaAction/preview).


***

### Improved Controls

-   **`sap.m.ComboBox`**:

-   Is now supported on mobile phones. The list of available values will open as a full-screen dialog on small devices.

-   The new `loadItem` event makes it possible to defer initialization of items in the `ComboBox` dropdown list control to a point in time when the items are required. This helps to improve performance.

    For more information, see the [sample](https://openui5.hana.ondemand.com/#/entity/sap.m.ComboBox).

-   **`sap.m.DatePicker`**, **`sap.m.DateTimePicker`**, **`sap.m.PlanningCalendar`**, and **`sap.ui.unified.Calendar`**: You can now set minimum and maximum dates to limit the range of available dates.

    For more information, see the API Reference for [`sap.m.DatePicker`](https://openui5.hana.ondemand.com/#/api/sap.m.DatePicker), [`sap.m.DateTimePicker`](https://openui5.hana.ondemand.com/#/api/sap.m.DateTimePicker), [`sap.m.PlanningCalendar`](https://openui5.hana.ondemand.com/#/api/sap.m.PlanningCalendar), and [`sap.ui.unified.Calendar`](https://openui5.hana.ondemand.com/#/api/sap.ui.unified.Calendar), and the samples for [`sap.m.DatePicker`](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.DatePicker/preview), [`sap.m.PlanningCalendar`](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.PlanningCalendarMinMax/preview), and [`sap.ui.unified.Calendar`](https://openui5.hana.ondemand.com/#/sample/sap.ui.unified.sample.CalendarMinMax/preview).

-   **`sap.m.GenericTile`**: The `GenericTile` control has a new responsive design that significantly improves the user experience, it has also been optimized for larger smartphones. The `GenericTile` adjusts its size to fit all the different display sizes of the current devices supported by OpenUI5 \(see [Browser and Platform Support](Browser_and_Platform_Support_74b59ef.md)\). The main changes are the tile size, font size, padding, the new `ImageContent` control, and new samples showing the variety of use cases for the `GenericTile`.

    The `sap.m.ImageContent` control can be used to include images in a tile. It can be embedded in the content area of the `GenericTile` control.

    For more information, see the API Reference for [`sap.m.GenericTile`](https://openui5.hana.ondemand.com/#/api/sap.m.GenericTile) and [`sap.m.ImageContent`](https://openui5.hana.ondemand.com/#/api/sap.m.ImageContent), the samples for [`GenericTile`](https://openui5.hana.ondemand.com/#/entity/sap.m.GenericTile) and [`ImageContent`](https://openui5.hana.ondemand.com/#/entity/sap.m.ImageContent), and [Generic Tile](Generic_Tile_a1998ec.md).

-   **`sap.m.List`** and **`sap.m.Table`**: The new `keyboardMode` property for the `List` and `Table` controls determines the keyboard handling for these controls. The `Navigation` value of the property enables a mode that allows you to navigate within a large number of items, for example, table cells, using the tab key, whereas the `Edit` mode can be used to edit a limited number of items.

-   **`sap.m.MaskInput`**: You can now use escape characters in the `MaskInput` definition to be able to use the predefined rule characters as immutable ones.

-   **`sap.m.MessagePopover`** has been improved and can now be resized. Resizing is only possible when the `MessagePopover` is opened from the footer on a desktop.

     ![](loio8443028265c54ddaa40cd223bf401d2f_HiRes.png) 

-   **`sap.m.NotificationListItem`**: The control has two improvements:

-   The control responsiveness is updated for better usability on large screens \(more than 640 pixels width\) – the buttons are now located on the right side of the text.

-   The *Show More* button for toggling expand/collapse mode can now be hidden with the use of the new property `hideShowMoreButton`.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.NotificationListItem) and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.m.NotificationListItem).

-   **`sap.m.Popover`** has four new values for its `PlacementType`:

-   `PreferredBottomOrFlip`

-   `PreferredLeftOrFlip`

-   `PreferredRightOrFlip`

-   `PreferredTopOrFlip`

They determine the preferred position of the `Popover` and how it behaves when there is insufficient space for it on the screen. These properties allow the `Popover` to flip over and cover some of the content below it.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.PlacementType) and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.m.PlacementType).

-   **`sap.m.TextArea`** can now grow and shrink to adapt to the entered text.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.TextArea) and the [sample](https://openui5.hana.ondemand.com/#/sample/sap.m.sample.TextAreaGrowing/preview).

-   **`sap.m.UploadCollection`**: To upload a new version of a file to the `UploadCollection` list, the `openFileDialog` method is available. You can provide a pushbutton in the header area and if one entry in the `UploadCollection` list is selected, the API method will be called.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.UploadCollection) and the [sample](https://openui5.hana.ondemand.com/#/entity/sap.m.UploadCollection)t.

-   **`sap.m.ViewSettingsDialog`**: The `ViewSettingsDialog` control now gives you the opportunity to modify filter detail page items on the fly with the help of the new event `filterDetailPageOpened`. This event is fired each time after the filter detail page is accessed, notifying the outside world that the page is loaded along with the information for which filter the respective details are displayed. This allows a handler to be attached that alters the filter detail items aggregation.

    For more information, see the [API Reference](https://openui5.hana.ondemand.com/#/api/sap.m.ViewSettingsDialog) in the Demo Kit.

-   **`sap.tnt.SideNavigation`**: Root items with no children can now be opened with a single click when the `SideNavigation` control is in collapsed mode.

-   **`sap.tnt.ToolPage`**: Animation is now added when expanding and collapsing the `SideNavigation` control within the `ToolPage`.

    For more information, see the [sample](https://openui5.hana.ondemand.com/#/sample/sap.tnt.sample.ToolPage/preview).

-   **`sap.ui.commons.ColorPicker`** supports HSL \(Hue Saturation and Lightness\) mode. This mode works better with modern browsers and it does not require intermediate conversion back to RGB. Additionally, there is a new input field for the `alpha` \(transparency\) value for more precise color definition.

     ![](loioafef27d2b0ef41b1b8dfa7517047bda8_HiRes.png) 

-   **`sap.ui.layout.Form`** and **`sap.ui.layout.SimpleForm`**: You can now add a toolbar to a form container or the form itself.

    For more information, see the [sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.layout.sample.FormToolbar/preview).

-   **`sap.ui.table.DataTable`** has been deleted.

-   **`sap.ui.table.TreeTable`** now supports `AutoExpand` paging if it is bound to an OData model.

    By setting `numberOfExpandedLevels` as a binding parameter \(e.g. in the `bindRows` call of the `TreeTable`\), you now can specify the initial expansion depth. This feature is only available for OData services exposing a property marked with the annotation `hierarchy-node-descendant-count-for`. This also means the service has to respect a `$filter` statement on the annotated `Level` property, and returns the entries sorted. You can find the specification for this and all other hierarchy annotations in the SAP Community Network under [SAP Annotations for OData Version 2.0](http://scn.sap.com/docs/DOC-44986)

-   **`sap.ui.unified.Menu`**: To significantly increase the usability of `sap.ui.unified.Menu`, a delay has been added to the closing of submenus.

    For more information, see the [sample](https://openui5.hana.ondemand.com/#/sample/sap.ui.unified.sample.MenuItemEventing/preview)t.

-   **`sap.uxap.ObjectPageHeader`** ObjectPageHeader can be integrated with the `SideContent` scenario. A new `sideContentButton` aggregation has been added. This aggregation has a new button, which appears after the actions buttons and triggers opening the side content for additional information.

     ![](loio8e2908435c774fe58ab9b8107be5f4fb_HiRes.png) 

    For more information, see the [sample](https://openui5.hana.ondemand.com/#/sample/sap.uxap.sample.ObjectPageDynamicSideContentBtn/preview).

-   **`sap.uxap.ObjectPageLayout`**:

-   It supports scrolling to a particular section, based on its ID. This allows easier access to all parts of the application and consistent navigation back to a previous position within the `ObjectPage`.

    For more information, see the [sample](https://openui5.hana.ondemand.com/#/sample/sap.uxap.sample.ObjectPageLazyLoadingWithoutBlocks/preview).

-   Performance is improved for the use case with no `Blocks`. The `ObjectPage` now supports lazy loading with the stashed property of the `ObjectPageLazyLoader`. As a result, you avoid the additional creation of XML views for each `Block`.

    For more information, see the [sample](https://openui5.hana.ondemand.com/#/sample/sap.uxap.sample.ObjectPageState/preview) and [Object Page Scrolling](Object_Page_Scrolling_bc410e9.md).


