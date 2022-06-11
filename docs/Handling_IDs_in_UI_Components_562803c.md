<!-- loio562803c6f55c49608d01a453cc0590ab -->

| loio |
| -----|
| 562803c6f55c49608d01a453cc0590ab |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/562803c6f55c49608d01a453cc0590ab) | [demo kit latest release](https://sdk.openui5.org/topic/562803c6f55c49608d01a453cc0590ab)</div>

## Handling IDs in UI Components

Components are usually used with a root view and in this case, the component handles the prefixing of IDs of views, elements, or controls, with the component ID.

This works similar to the prefixing of control IDs in XML views, see [Support for Unique IDs](Support_for_Unique_IDs_91f28be.md). However, if you implement your own `createContent` function, you need to handle this yourself. The following two options exist:

-   Set the `sap.ui5/autoPrefixId` attribute in the `manifest.json` file to `true`. This is the easiest option.

-   Use the `createId` function of the UI component to prefix the respective ID of a view, element, or control yourself.


Use the `byId` function of the UI component to retrieve the views, controls, and elements that have been created in a UI component.

