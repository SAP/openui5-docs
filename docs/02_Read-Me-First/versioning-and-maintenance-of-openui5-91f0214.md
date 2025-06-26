<!-- loio91f021426f4d1014b6dd926db0e91070 -->

# Versioning and Maintenance of OpenUI5

Versioning and maintenance strategy for OpenUI5.

***

<a name="loio91f021426f4d1014b6dd926db0e91070__section_DC50B59D56AC4B52A2DBEFADFA4B0E98"/>

## Version Designation

OpenUI5 uses a three-number version identifier, for example, 1.71.22. The numbers have the following meaning:

-   The first part \(1\) specifies the release number \(major version\).
-   The second part \(71\) specifies the version number \(minor version\).
-   The third part \(22\) specifies the patch number.

To view the documentation for a specific version, check at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html) which versions are available. You can view the version-specific Demo Kit by adding the version number to the URL, for example, `https://sdk.openui5.org/1.71.22/` .

To get an overview of the new features of each version, see [What's New in OpenUI5](../01_Whats-New/what-s-new-in-openui5-99ac68a.md). To see the fixes contained in each patch, check the [Change Log](https://sdk.openui5.org/releasenotes.html).

***

<a name="loio91f021426f4d1014b6dd926db0e91070__section_qnr_ghw_ffc"/>

## Maintenance Strategy

Every month, OpenUI5 releases a new version for productive usage. Support periods vary by release type:


<table>
<tr>
<th valign="top" align="center">

Release Type

</th>
<th valign="top" align="center">

Support Period

</th>
<th valign="top" align="center">

Typical Release Cycle

</th>
</tr>
<tr>
<td valign="top">

Standard

</td>
<td valign="top">

6 weeks

</td>
<td valign="top">

Monthly

</td>
</tr>
<tr>
<td valign="top">

Mid-Term Support \(MTS\)

</td>
<td valign="top">

9 months

</td>
<td valign="top">

Anually \(6 months after LTS release\)

</td>
</tr>
<tr>
<td valign="top">

Long-Term Support \(LTS\)

</td>
<td valign="top">

15 months

</td>
<td valign="top">

Anually

</td>
</tr>
</table>

The release strategy follows the principle of "one innovation code line": Subsequent versions ensure continuous innovation with an evolving code line. All OpenUI5 versions receive critical security fixes until the version’s end of life \(EOL\) date.

Mid-term and long-term maintenance releases also receive bug fixes until their end of maintenance \(EOM\) date \(for standard releases, bug fixes are included in the next OpenUI5 version\). After the EOM date, only critical security patches are offered for a year, after which these versions reach their EOL date.

Whenever a new patch for a version is released, the older patch becomes outdated. One year after becoming outdated, it enters End of Cloud Provisioning \(EOCP\) and is removed from the Akamai content delivery network \(CDN\) at the start of the following quarter.

In the version overview at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html), you can find information on the maintenance status of all available OpenUI5 versions and the EOCP dates for each patch version.

***

## Availability of Multiple Versions on the Akamai Content Delivery Network

OpenUI5 resources are available on the Akamai content delivery network. There, you can also find multiple OpenUI5 versions, and you can use them in your code as described in [Variant for Bootstrapping from Content Delivery Network](../04_Essentials/variant-for-bootstrapping-from-content-delivery-network-2d3eb2f.md).

Check the available versions with respective maintenance status at [https://sdk.openui5.org/versionoverview.html](https://sdk.openui5.org/versionoverview.html).

***

<a name="loio91f021426f4d1014b6dd926db0e91070__section_b1g_xcw_dz"/>

## OpenUI5 Version

You can find which framework versions you use in your app in the [Technical Information Dialog](../04_Essentials/technical-information-dialog-616a3ef.md#loio616a3ef07f554e20a3adf749c11f64e9) \([Ctrl\] + [Shift\] + [Left Alt / Left Option\] + [P\] .

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

