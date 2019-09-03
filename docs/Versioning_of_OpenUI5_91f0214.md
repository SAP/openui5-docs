<!-- loio91f021426f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f021426f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f021426f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f021426f4d1014b6dd926db0e91070)</div>

## Versioning of OpenUI5

Versioning and maintenance strategy for OpenUI5.

***

OpenUI5 uses a 3-digit version identifier, for example 1.60.2. The digits have the following meaning:

-   The first digit \(1\) specifies the release number \(major version\).
-   The second digit \(60\) specifies the version number \(minor version\) .
-   The third digit \(2\) specifies the patch number.

To view the documentation for a specific version, check at [https://openui5.hana.ondemand.com/versionoverview.html](https://openui5.hana.ondemand.com/versionoverview.html) which versions are available. You can view the version-specific Demo Kit by adding the version number to the URL, for example, `https://openui5.hana.ondemand.com/1.60.2/`

To get an overview of the new features of each version, see [What's New in OpenUI5](What's_New_in_OpenUI5_99ac68a.md), to see the fixes contained in each patch check the  [Change Log](https://openui5.hana.ondemand.com/#releasenotes.html).

***

<a name="loio91f021426f4d1014b6dd926db0e91070__section_dpk_pcw_dz"/>

### Maintenance Strategy

Every month, OpenUI5 releases a new version for productive usage.

The release strategy follows the principle of “one innovation code line”: subsequent versions ensure continuous innovation with an evolving code line.

Once a year, a version with long-term support is released. All other versions do not have a maintenance period and no patches are provided. Required fixes are available with the next minor versions together with the new features. However, in exceptional cases, also the most recent version may be patched with correction code.

For the decision to consume a new version, we recommend the following guideline:

-   For SAP Cloud Platform, we recommend to upgrade to the latest available version.

-   For AS ABAP/SAP Fiori Frontend Server, or in case regular version updates are not feasible, we recommend to update to the respective long-term maintenance versions as outlined in the *Minimal Installation Requirements* and *SAP Fiori Frontend Server* notes.


For example, the following versions have a long-term maintenance:

-   1.38

-   1.44

-   1.52

-   1.60


In the version overview at [https://openui5.hana.ondemand.com/versionoverview.html](https://openui5.hana.ondemand.com/versionoverview.html), you can see which of the OpenUI5 versions have an extended maintenance.

***

### Availability of Multiple Versions on the Akamai Content Delivery Network

All OpenUI5 resources are available on the content delivery network Akamai. There, you can also find multiple OpenUI5 versions, and you can use them in your code as described in [Variant for Bootstrapping from Content Delivery Network](Variant_for____________Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

Check the available versions with respective maintenance status at [https://openui5.hana.ondemand.com/versionoverview.html](https://openui5.hana.ondemand.com/versionoverview.html).

***

<a name="loio91f021426f4d1014b6dd926db0e91070__section_b1g_xcw_dz"/>

###  OpenUI5 Version \(Core Version\)

You can find which patch versions you use in you app in the technical information dialog \(* Ctrl Left Alt Shift P *\).

To access the OpenUI5 version \(core version\) at runtime, you use the following code:

``` js
var oConfig = sap.ui.getCore().getConfiguration();
var oVersion = oConfig.getVersion();

```

For more information, see [SAPUI5 vs. OpenUI5](SAPUI5_vs._OpenUI5_5982a97.md).

