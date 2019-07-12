| loio |
| -----|
| 91f2f9396f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/91f2f9396f4d1014b6dd926db0e91070.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f2f9396f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f2f9396f4d1014b6dd926db0e91070)</div>
<!-- loio91f2f9396f4d1014b6dd926db0e91070 -->

## sap.ui.model.type.Boolean

The `Boolean` data type represents a string.

The source value \(value given in the model\) must be given as boolean and is transformed into the type of the bound control property:

-    `boolean`: No transformation needed
-    `string`: "true" or "X" are interpreted as true, "false" and "" as false

The `Boolean` type has **no** format or validation constraint options.

Example how a `Boolean` type can be initialized:

```lang-js
// "TypeBoolean" required from module "sap/ui/model/type/Boolean"
// The source value is given as boolean.
var oType = new TypeBoolean();
```

