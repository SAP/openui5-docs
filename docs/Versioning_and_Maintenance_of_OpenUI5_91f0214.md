<!-- loio91f021426f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f021426f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/91f021426f4d1014b6dd926db0e91070) | [demo kit latest release](https://sdk.openui5.org/topic/91f021426f4d1014b6dd926db0e91070)</div>

## Versioning and Maintenance of OpenUI5

Versioning and maintenance strategy for OpenUI5.

***

OpenUI5 uses a three-number version identifier, for example, 1.71.22. The numbers have the following meaning:

-   The first part \(1\) specifies the release number \(major version\).
-   The second part \(71\) specifies the version number \(minor version\).
-   The third part \(22\) specifies the patch number.

To view the documentation for a specific version, check at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html) which versions are available. You can view the version-specific Demo Kit by adding the version number to the URL, for example, `https://sdk.openui5.org/1.71.22/` .

To get an overview of the new features of each version, see [What's New in OpenUI5](What_s_New_in_OpenUI5_99ac68a.md). To see the fixes contained in each patch, check the [Change Log](https://sdk.openui5.org/releasenotes.html).

***

<a name="loio91f021426f4d1014b6dd926db0e91070__section_dpk_pcw_dz"/>

### Maintenance Strategy

Every month, OpenUI5 releases a new version for productive usage.

The release strategy follows the principle of "one innovation code line”: Subsequent versions ensure continuous innovation with an evolving code line.

Once a year, a version with long-term support is released. All other versions do not have a maintenance period and no patches are provided. Required fixes are available with the next minor versions together with the new features. However, in exceptional cases, also the most recent version may be patched with correction code.

In the version overview at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html), you can see which of the OpenUI5 versions have an extended maintenance.

***

### Availability of Multiple Versions on the Akamai Content Delivery Network

OpenUI5 resources are available on the Akamai content delivery network. There, you can also find multiple OpenUI5 versions, and you can use them in your code as described in [Variant for Bootstrapping from Content Delivery Network](Variant_for_Bootstrapping_from_Content_Delivery_Network_2d3eb2f.md).

Check the available versions with respective maintenance status at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html).

***

<a name="loio91f021426f4d1014b6dd926db0e91070__section_b1g_xcw_dz"/>

### OpenUI5 Version

You can find which framework versions you use in your app in the [Technical Information Dialog](Technical_Information_Dialog_616a3ef.md#loio616a3ef07f554e20a3adf749c11f64e9) \([Ctrl\] + [Shift\] + [Left Alt\] /[Option\] + [P\] \).

To access the OpenUI5 version at runtime, you can use the following code:

```js
sap.ui.require([
    "sap/ui/VersionInfo",
    "sap/base/util/Version"
], (VersionInfo, VersionUtil) => {
    VersionInfo.load().then(oCurrentVersionInfo => {
    const oOpenUI5Version = new VersionUtil(oCurrentVersionInfo.version);
        // ...
    });
});
```

> ### Note:  
> Standalone apps, e.g. apps using the `self-contained` build of [UI5 Tooling](https://sap.github.io/ui5-tooling), will report the version of the app itself. Only if the framework resources are provided by a content delivery network \(CDN\) or a similar shared installation will the main version of the framework be retrieved as shown above.

