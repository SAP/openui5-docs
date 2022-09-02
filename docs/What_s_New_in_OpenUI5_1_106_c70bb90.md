<!-- loioc70bb907d05a4f9fb6c36ecf73b3fb2e -->

| loio |
| -----|
| c70bb907d05a4f9fb6c36ecf73b3fb2e |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/c70bb907d05a4f9fb6c36ecf73b3fb2e) | [demo kit latest release](https://sdk.openui5.org/topic/c70bb907d05a4f9fb6c36ecf73b3fb2e)</div>

## What's New in OpenUI5 1.106

With this release OpenUI5 is upgraded from version 1.105 to 1.106.

***

<a name="loioc70bb907d05a4f9fb6c36ecf73b3fb2e__section_pzq_t5d_s5b"/>

### Preview and Announcements

The following information concerns important upcoming changes. UI changes may have an impact on the user experience and may require test cases to be adapted.


<table>
<tr>
<th valign="top">

Type



</th>
<th valign="top">

Description



</th>
<th valign="top">

Available as of OpenUI5 Version



</th>
</tr>
<tr>
<td valign="top">

Announcement



</td>
<td valign="top">

**Deactivation of Default Time Zone Configuration Feature**

We needed to deactivate the feature to configure the default time zone via the time zone configuration option in [`sap.ui.core.Configuration`](https://sdk.openui5.org/api/sap.ui.core.Configuration) and the API method [`sap.ui.core.Configuration.setTimezone`](https://sdk.openui5.org/api/sap.ui.core.Configuration/methods/setTimezone). Reason: There was a risk that dates are visualized by one day off. This wrong date might have been persisted to the back end.

This feature was introduced with UI5 1.102.0. The following UI5 versions still contain this feature:

-   1.102.0 to 1.102.5
-   1.103
-   1.104

If you are on one of these releases, we recommend that you upgrade to a higher version where this feature is deactivated.

We plan to bring this feature back in a different form at a later point in time.



</td>
<td valign="top">

Deactivated as of:

1.106

1.105

1.102.6



</td>
</tr>
<tr>
<td valign="top">

Announcement



</td>
<td valign="top">

**Reminder: Outdated OpenUI5 Versions to Be Removed from the CDN**

For security reasons, OpenUI5 versions that are no longer maintained will be removed from the UI5 content delivery network \(CDN\) one year after their end of maintenance. If a version is still in maintenance, patches of that version that are older than one year will also be removed. We have noted that a number of customers are still using such outdated versions or patches. If this affects you, please note that once these versions or patches are removed, your applications will break. Please update to a more recent version or patch. For more information, see: [Removing Outdated UI5 Versions from UI5 CDN](https://blogs.sap.com/2021/01/26/removing-outdated-ui5-versions-from-ui5-cdn/) as well as the UI5 notifications in the Demo Kit.



</td>
<td valign="top">

 



</td>
</tr>
</table>

***

<a name="loioc70bb907d05a4f9fb6c36ecf73b3fb2e__section_rqn_wd5_zcb"/>

### Improved Controls


<table>
<tr>
<td valign="top">

**`sap.m.Image` \(Experimental\)**

We have enabled inline rendering of SVG files, so that they can be themeable and overstyled with a custom CSS. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.m.Image). 



</td>
</tr>
<tr>
<td valign="top">

**`sap.ui.integration.widgets.Card`**

-   We have made the loading placeholder for Timeline card more detailed to better reveal the expected loading content. For more information, see the [Sample](https://sdk.openui5.org/entity/sap.ui.integration.widgets.Card/sample/sap.ui.integration.sample.LazyLoading).

-   We have \(experimentally\) enabled the Object card to validate the user input provided in the card form fields. As a card developer, using the available validation functions, you can now specify if the input is required, limit the number of characters, or restrict the input to some predefined options. You can also set the validation message and the validation type \(`Error`, `Warning`, or `Information`\). For more information, see the [Input Validation](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/inputValidation) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/formWithValidation) in the Card Explorer.

-   We have \(experimentally\) introduced new properties that enable you to format Object card content:

    -   `titleMaxLines` - limits the number of lines in which the group title will be wrapped.
    -   `labelWrapping` - a Boolean property that determines whether the labels of the group items will be wrapped.

    For more information, see the [Object Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/object) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/object/titleMaxLinesAndLabelWrapping) in the Card Explorer.

-   You can now control the visibility of List card item’s attributes using the new `visible` Boolean property.

    For more information, see the [List Card](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/typesDeclarative/list) section and the [Sample](https://sdk.openui5.org/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/attributesVisibility) in the Card Explorer.




</td>
</tr>
<tr>
<td valign="top">

**`sap.uxap.ObjectPageSection`**

We have introduced a new `heading` aggregation that allows you to include content, such as message strips, at the beginning of a section. For more information, see the [API Reference](https://sdk.openui5.org/api/sap.uxap.ObjectPageSection) and the [Samples](https://sdk.openui5.org/entity/sap.uxap.ObjectPageSection).



</td>
</tr>
</table>

***

<a name="loioc70bb907d05a4f9fb6c36ecf73b3fb2e__section_cps_cg5_zcb"/>

### Deprecations


<table>
<tr>
<td valign="top">

There are currently no major deprecations. For a complete list of all deprecations, see [Deprecated APIs](https://sdk.openui5.org/api/deprecated). 



</td>
</tr>
</table>

