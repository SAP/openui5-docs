<!-- loio1586c19a9d854f6e82613fd75290c34f -->

| loio |
| -----|
| 1586c19a9d854f6e82613fd75290c34f |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/1586c19a9d854f6e82613fd75290c34f) | [demo kit latest release](https://sdk.openui5.org/topic/1586c19a9d854f6e82613fd75290c34f)</div>

## Facet Filter: Simple Type

The simple type of the `FacetFilter` control is only available for desktop and tablets.

The active facets are displayed as individually selectable buttons on the toolbar as shown in the following figure.

 ![](images/loio0c7cf9fee5ff4148ad1838cec80fa1ea_LowRes.png) 

If the user selects a facet in the toolbar, a popover list of the available filters for the selected facet is displayed.

 ![](images/loio5dd47289104c4f50b6f0748e8f39a372_LowRes.png) 

The simple type provides the following functions:

-   With the `showPopoverOkButton` property of the `FacetFilter` control you can display an *OK* button in the popover. The *OK* button enables the user to close the popover in addition to the standard behavior of `sap.m.Popover`.

-   With the `showPersonalization` property you enable the user to add facets to the toolbar by selecting the *Add Facet* icon. Personalization is disabled by default.

-   With the `showSummaryBar` property you can display the active facets as a non-selectable summary bar. You use this property if you preset facet filters and the user is not allowed to change them.

    ![](images/loio53a401c2261b46ec9f4253fbf2363c28_LowRes.png)


