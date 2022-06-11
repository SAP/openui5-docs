<!-- loio91f021426f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f021426f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/91f021426f4d1014b6dd926db0e91070) | [demo kit latest release](https://sdk.openui5.org/topic/91f021426f4d1014b6dd926db0e91070)</div>

## Versioning and Maintenance of OpenUI5

Versioning and maintenance strategy for OpenUI5.

***

OpenUI5 uses a 3-digit version identifier, for example 1.71.22 The digits have the following meaning:

-   The first digit \(1\) specifies the release number \(major version\).
-   The second digit \(71\) specifies the version number \(minor version\).
-   The third digit \(22\) specifies the patch number.

To view the documentation for a specific version, check at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html) which versions are available. You can view the version-specific Demo Kit by adding the version number to the URL, for example, `https://sdk.openui5.org/1.71.22/`.

To get an overview of the new features of each version, see [What's New in OpenUI5](What_s_New_in_OpenUI5_99ac68a.md), to see the fixes contained in each patch check the  [Change Log](https://sdk.openui5.orgreleasenotes.html).

***

<a name="loio91f021426f4d1014b6dd926db0e91070__section_dpk_pcw_dz"/>

### Maintenance Strategy

Every month, OpenUI5 releases a new version for productive usage.

The release strategy follows the principle of “one innovation code line”: Subsequent versions ensure continuous innovation with an evolving code line.

Once a year, a version with long-term support is released. All other versions do not have a maintenance period and no patches are provided. Required fixes are available with the next minor versions together with the new features. However, in exceptional cases, also the most recent version may be patched with correction code.

For example, the following versions have a long-term maintenance:

-   1.38

-   1.52

-   1.60

-   1.71


In the version overview at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html), you can see which of the OpenUI5 versions have an extended maintenance.

***

### Availability of Multiple Versions on the Akamai Content Delivery Network

OpenUI5 resources are available on the Akamai content delivery network. There, you can also find multiple OpenUI5 versions, and you can use them in your code as described in [Variant for Bootstrapping from Content Delivery Network](Variant_for_Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

Check the available versions with respective maintenance status at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html).

***

<a name="loio91f021426f4d1014b6dd926db0e91070__section_b1g_xcw_dz"/>

###  OpenUI5 Version \(Core Version\)

You can find which patch versions you use in your app in the technical information dialog \( [Ctrl\] + [Left Alt\] + [Shift\] + [P\] \).

To access the OpenUI5 version \(core version\) at runtime, you use the following code:

```js
var oConfig = sap.ui.getCore().getConfiguration();
var oVersion = oConfig.getVersion();

```

For more information, see [SAPUI5 vs. OpenUI5](SAPUI5_vs_OpenUI5_5982a97.md).

