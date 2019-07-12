| loio |
| -----|
| 8bb4723002ef4dc19a065b2e30c5498f |

<div id="loio">

view on: [help.sap.com](https://help.sap.com/viewer/DRAFT/3237636b137e43519a20ad5513c49ccb/latest/en-US/8bb4723002ef4dc19a065b2e30c5498f.html) | [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8bb4723002ef4dc19a065b2e30c5498f) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8bb4723002ef4dc19a065b2e30c5498f)</div>
<!-- loio8bb4723002ef4dc19a065b2e30c5498f -->

## Programmatic Access to RTL

Some controls need to provide specific coding for right-to-left mode \(RTL\), for example, because they position or animate elements programmatically, and not via CSS. To read the OpenUI5 RTL configuration, use the following function call:

```lang-js

var bRtl = sap.ui.getCore().getConfiguration().getRTL();
```

