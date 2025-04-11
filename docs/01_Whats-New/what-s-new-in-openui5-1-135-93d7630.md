<!-- loio93d76303615a428fb9e92e8ef1878a83 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

## What's New in OpenUI5 1.135

With this release OpenUI5 is upgraded from version 1.134 to 1.135.

> ### Note:  
> Content marked as <span style="color:#666666;"><span class="SAP-icons-V5"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)** is provided as a courtesy, without a warranty, and may be subject to change. For more information, see the [preview disclaimer](https://help.sap.com/docs/whats-new-disclaimer).

****


<table>
<tr>
<th valign="top">

Version

</th>
<th valign="top">

Type

</th>
<th valign="top">

Category

</th>
<th valign="top">

Title

</th>
<th valign="top">

Description

</th>
<th valign="top">

Action

</th>
<th valign="top">

Available as of

</th>
</tr>
<tr>
<td valign="top">

Upcoming 

</td>
<td valign="top">

Deleted 

</td>
<td valign="top">

Announcement 

</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q2/2025\)** 

</td>
<td valign="top">

**End of Cloud Provisioning for OpenUI5 Versions \(Q2/2025\)**

The following OpenUI5 versions will be removed from the OpenUI5 Content Delivery Network \(CDN\) after the end of Q2/2025.

**Minor Versions Reaching Their End of Cloud Provisioning**

The following versions including all patches will be removed entirely:

-   1.121
-   1.122
-   1.123
-   1.124

**Action**: Upgrade to a version that is still in maintenance.

**Patch Versions Reaching Their End of Cloud Provisioning**

The following patches will be removed:

-   Long-term maintenance versions:

    -   1.71.63 to 1.71.65
    -   1.84.44 to 1.84.45
    -   1.96.28 to 1.96.30
    -   1.108.27 to 1.108.29
    -   1.120.11 to 1.120.15

    **Action**: Upgrade to the latest available patch for the respective OpenUI5 version.


For more information, see [Version Overview](https://sdk.openui5.org/versionoverview.html).

<sub><span style="color:#666666;"><span class="SAP-icons-V5"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)**•Deleted•Announcement•Info Only•Upcoming</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

9999-01-01

</td>
</tr>
<tr>
<td valign="top">

Upcoming 

</td>
<td valign="top">

Deleted 

</td>
<td valign="top">

Announcement 

</td>
<td valign="top">

**Removal of *Belize* and *Blue Crystal* Themes** 

</td>
<td valign="top">

****Removal of *Belize* and *Blue Crystal* Themes****

> ### Note:  
> The following information concerns important upcoming changes for end users. These changes may require end users to adjust and/or test cases to be adapted, but they won't stop or disrupt software or processes.

We will remove the deprecated *Belize* theme family in the OpenUI5 1.136 version. We will also remove the *Blue Crystal* theme and the related *High Contrast Black* theme that have been deprecated for some time. Themes will automatically be switched to the *Horizon* theme family in your apps.

<sub><span style="color:#666666;"><span class="SAP-icons-V5"></span></span>**[Preview](https://help.sap.com/docs/whats-new-disclaimer)**•Deleted•Announcement•Info Only•Upcoming</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

9999-01-01

</td>
</tr>
<tr>
<td valign="top">

1.135 

</td>
<td valign="top">

Deprecated 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Deprecations** 

</td>
<td valign="top">

**Deprecations**

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://ui5.sap.com/#/api/deprecated).

<sub>Deprecated•Feature•Info Only•1.135</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-04-17

</td>
</tr>
<tr>
<td valign="top">

1.135 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.ui.layout.form*` ** 

</td>
<td valign="top">

**`sap.ui.layout.form*`**

To improve the accessibility of screen reader announcements, we have adapted the rendering of the `sap.ui.layout.form*` elements in forms with read-only content for the `columnLayout`. To enable this, the form is now rendered as a description list \(`<dl>` tag used\).

<sub>Changed•Control•Info Only•1.135</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-04-17

</td>
</tr>
<tr>
<td valign="top">

1.135 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**Enhanced Module Name Syntax for Factory APIs** 

</td>
<td valign="top">

**Enhanced Module Name Syntax for Factory APIs**

You can now use module name syntax when creating typed views, controllers, or JS fragments via a factory API. This removes the need for strict filename suffixes like `.view.js`, `.controller.js`, or `.fragment.js`, offering you more flexibility in naming and organizing your entities. For an example, see [Controller](../04_Essentials/controller-121b8e6.md).

<sub>Changed•Feature•Info Only•1.135</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-04-17

</td>
</tr>
<tr>
<td valign="top">

1.135 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Feature 

</td>
<td valign="top">

**OpenUI5 OData V4 Model** 

</td>
<td valign="top">

**OpenUI5 OData V4 Model**

The new version of the OpenUI5 OData V4 model introduces the following features:

-   We now support read-only bindings for Geometry types. This includes the possibility to address elements of collections via their indexes in read-only bindings.

-   We now evaluate [`com.sap.vocabularies.Common.v1.AddressViaNavigationPath`](https://github.com/SAP/odata-vocabularies/blob/main/vocabularies/Common.md) for PATCH and DELETE requests.

-   When reloading a list binding's data, the selection state is now validated if the `$$clearSelectionOnFilter` list binding parameter is set and if `$$aggregation` is not set. The selection state of contexts no longer matching the filter is reset.

-   We have introduced the experimental `copy` parameter to `sap.ui.model.odata.v4.Context#move`. It must not be set to `true` for productive applications yet.For more information, see the [API Reference](https://ui5.sap.com/#/api/sap.ui.model.odata.v4.Context%23methods/move).

-   We have provided the `sap.ui.model.odata.v4.ODataListBinding#getSelectionCount` method to return the number of selected items. The selection count may be bound by using the `$selectionCount` parameter in a similar way as for binding the `$count`. For more information, see [Binding Collection Inline Count](../04_Essentials/binding-collection-inline-count-77d2310.md).


<sub>Changed•Feature•Info Only•1.135</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-04-17

</td>
</tr>
<tr>
<td valign="top">

1.135 

</td>
<td valign="top">

Changed 

</td>
<td valign="top">

Control 

</td>
<td valign="top">

**`sap.m.Input, sap.m.MultiInput`** 

</td>
<td valign="top">

**`sap.m.Input, sap.m.MultiInput`**

Speech output for table suggestions in `sap.m.Input` and `sap.m.MultiInput` now includes column headers, not just cell values. This enhancement improves accessibility for screen-reader users.

<sub>Changed•Control•Info Only•1.135</sub>

</td>
<td valign="top">

Info Only 

</td>
<td valign="top">

2025-04-17

</td>
</tr>
</table>

