<!-- loio91f29fea6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f29fea6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f29fea6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f29fea6f4d1014b6dd926db0e91070)</div>

## Object Metadata and Implementation

OpenUI5 supports the extension of plain objects that are not elements or controls.

For these objects, only the following metadata is available:

-   `interfaces`: String array that denotes the implemented interfaces \(optional\)

-   `publicMethods`: List of methods that should be part of the public API \(optional\)

-   `abstract`: Flag to mark the type as abstract \(optional\)

-   `final`: Flag to mark the type as final \(optional\)


> ### Note:  
> This metadata can also be used when extending controls.

Regarding the implementation, all methods given outside the metadata are attached to the new type. The method name `constructor` is reserved for the constructor function of the new class. Although it is possible from a technical point of view, we recommend **not** to define a constructor for new elements and controls. Your control may otherwise break in some scenarios, such as in combination with list bindings, or may no longer be compatible in later versions of OpenUI5 when the constructor signature is extended.

