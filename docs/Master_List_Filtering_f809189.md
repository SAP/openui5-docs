<!-- loiof809189153034d7586468e7213aa8cf1 -->

| loio |
| -----|
| f809189153034d7586468e7213aa8cf1 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/f809189153034d7586468e7213aa8cf1) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/f809189153034d7586468e7213aa8cf1)</div>

## Master List Filtering

You can use the following best practices when implementing search, sorting, filtering and grouping functions for a master list in your Master-Detail apps.

A search field is displayed in the master list to filter the list items for a custom keyword. In the header toolbar of the master list, options for sorting, filtering, and grouping are displayed. When searching or using one of the options in the header, the list content is updated automatically, and the search result is displayed.

All four options adjust the master list content \(search, sort, filter, group\) and are managed and applied in the logic of the master controller. This section describes the implementation details for these four options.

***

### Search

The search is implemented in a manual mode and the list operation mode is "server". This means that the search has to be triggered explicitly by pressing enter or the search button, and the results are always fetched from the server.

The search function is implemented using the standard OpenUI5 `sap.ui.model.Filter` objects. The options are added to an internal state object of the controller and applied together with the filters that can be selected in the filter options. The type of these filters is "Application", and these filters are added on top of the predefined filters from the framework of type "Control".

The *Search* field also displays a *Refresh* button. Pressing this button triggers a simple refresh for the list binding.

***

### Sorting, Filtering and Grouping

Sorting, filtering, and grouping can be implemented by using a semantic button that opens a `sap.m.ViewSettingsDialog` containing options for sorting, grouping, and filtering.

The event handlers that are called when selecting a sorting and grouping option are similar. They are implemented as an XML fragment with a `sap.m.ViewSettingsDialog` in a fragment. Therefore, we process the selected options in the handler of the dialog's `confirm` event. The event handlers create a `sap.ui.model.Sorter` object on the *key* field of the selected item. For the grouping functionality, a custom grouper is loaded and applied to the selected entry. Both sorting and grouping options are applied together on the binding of the master list. A `sap.ui.model.Filter` object is created for each filter option that has been selected in the dialog and applied together with the search option on the master list.

The filter message is automatically updated with the chosen filter texts. It is displayed on top of the master list and can be clicked to reopen the filter settings.

**Related information**  


[SAP Fiori Design Guidelines: Master List](https://experience.sap.com/fiori-design/floorplans/master-list/)

