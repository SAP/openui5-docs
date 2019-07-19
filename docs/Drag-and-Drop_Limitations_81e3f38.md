<!-- loio81e3f38f5e3e4194bb32675c86b49ba2 -->

| loio |
| -----|
| 81e3f38f5e3e4194bb32675c86b49ba2 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/81e3f38f5e3e4194bb32675c86b49ba2) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/81e3f38f5e3e4194bb32675c86b49ba2)</div>

## Drag-and-Drop Limitations

There are some known limitations when using drag and drop.

When you use drag and drop, the following limitations apply:

-   Drag and drop is not supported on mobile devices.

-   The transparency of the dragging ghost element and the cursor during drag-and-drop operations is not configurable.

-   Defining constraints for the drag position is not possible.

-   Texts in draggable controls cannot be selected. The text of input fields in draggable controls can be selected, but not dragged.

-   Microsoft Internet Explorer 11 only supports the plain text MIME type for the `DataTransfer` object \(DTO\). Also, defining a custom dragging ghost element is not possible.


Note that drag and drop is not accessible. Applications must provide an alternative for users with special needs for drag-and-drop operations.

