<!-- loiob8fdf0c903424c9191f142842323ae22 -->

| loio |
| -----|
| b8fdf0c903424c9191f142842323ae22 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/b8fdf0c903424c9191f142842323ae22) | [demo kit latest release](https://sdk.openui5.org/topic/b8fdf0c903424c9191f142842323ae22)</div>

## Adapting to the Modularization of the Core

Small, predefined modules for specific purposes, providing standalone functionality can be used any time OpenUI5 is loaded.

The modules are either Browser-dependent \(`sap/ui/core`\) and use the DOM or any other Browser-native API, or not Browser-dependent \(`sap/base`\) and could run in `node.js` without DOM access. Note that `node.js` is not an officially supported environment.

***

<a name="loiob8fdf0c903424c9191f142842323ae22__section_dcz_jnh_y2b"/>

### Compatibility With Existing Modules

The modules are introduced with OpenUI5 version 1.58 and replace the existing larger core modules to make the code easier to understand and maintain, and to decrease the initial payload of OpenUI5. To avoid that the removal of dependencies caused by the switch to the new modules causes exceptions, a lazy loading of the legacy modules is provided. For compatibility reasons, this lazy loading is done synchronously and it provides just the API namespace without loading the actual implementation.

![](images/loio81e22f4606b044638780935701a279c8_LowRes.png)

As it may not be obvious where those calls occur or where a dependency is missing, a rule in the Support Assistant reports the use and provides guidance on how to avoid them. A second rule with lower priority reports the use of an `jQuery.sap` API in general. There are also log warnings in the console of the browser's development tools, including a stack trace which makes it easy to locate the call in your coding.

***

<a name="loiob8fdf0c903424c9191f142842323ae22__section_wbd_lph_y2b"/>

### Migration

To benefit from the improvements provided by the modules, perform the following steps:

-   Always declare the full dependencies as described in [Loading a Module](Loading_a_Module_d12024e.md).

-   Migrate to the new module API as described in [Legacy jQuery.sap Replacement](Legacy_jQuery_sap_Replacement_a075ed8.md). Do **not** use the global `jQuery.sap` API anymore.

-   Do **not** use the global `sap.ui` factory functions. Instead, use their replacements, see [Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md).


-   **[Legacy jQuery.sap Replacement](Legacy_jQuery_sap_Replacement_a075ed8.md "Overview of the mapping of legacy APIs to the new APIs for the migration")**  
Overview of the mapping of legacy APIs to the new APIs for the migration
-   **[Legacy Factories Replacement](Legacy_Factories_Replacement_491bd9c.md "Overview of the replacement of global functions with the factory
		functions")**  
Overview of the replacement of global functions with the factory functions
-   **[Troubleshooting](Troubleshooting_20f6ea7.md "")**  


