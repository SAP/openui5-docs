<!-- loio9feb96da02c2429bb1afcf6534d77c79 -->

| loio |
| -----|
| 9feb96da02c2429bb1afcf6534d77c79 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/9feb96da02c2429bb1afcf6534d77c79) | [demo kit latest release](https://sdk.openui5.org/topic/9feb96da02c2429bb1afcf6534d77c79)</div>

## Compatibility Version Information

Compatibility version flags were introduced to allow applications to react to incompatible changes in OpenUI5.

> ### Caution:  
> The concept of compatibility versions has been abandoned as of OpenUI5 version 1.28. Therefore, no new compatibility version flags will be introduced in the future. If you start building a new application, please set `data-sap-ui-compat-version="edge"` on your OpenUI5 bootstrap tag. This ensures that the newest behavior of all features is applied.

***

<a name="loio9feb96da02c2429bb1afcf6534d77c79__section_dxf_c4r_zcc"/>

### Previous Function of the Compatibility Version Flag \(deprecated\)

As described in the compatibility rules, changes to OpenUI5 features are compatible; see [Compatibility Rules](Compatibility_Rules_91f0873.md) for more information. In some cases, however, it used to make sense to change the behavior of a feature, for example, in order to change the default values or to use an optimized implementation. These changes could result in incompatibilities.

> ### Note:  
> We recommend adopting new feature versions as soon as possible.

The compatibility version configuration worked as follows:

-   A version flag was introduced if a feature change was incompatible.
-   The version flag had to be defined in the OpenUI5 bootstrap tag, either globally \(via `data-sap-ui-compat-version`\) or individually for each feature \(for example `data-sap-ui-compat-version-xyz`\). Example with `compat-version "1.18"`:

    ```html
    <script id="sap-ui-bootstrap" 
            type="text/javascript"
            src="resources/sap-ui-core.js"
            data-sap-ui-theme="sap_horizon"
            data-sap-ui-libs="sap.m"
            data-sap-ui-compat-version="1.18"
            data-sap-ui-compat-version-xyz="1.16"
            >
    </script> 
    ```

-   If no compatibility version is defined, the default behavior of the feature applies.
-   If an explicit version is specified, the behavior of the specified version is applied \(deprecated\).
-   If **`edge`** is specified as the compatibility version, the newest behavior of the feature is applied.
-   A fallback mechanism is implemented. The following table is an example of possible configuration options for feature "xyz":


    <table>
    <tr>
    <th valign="top">

    data-sap-ui-compat-version
    
    </th>
    <th valign="top">

    data-sap-ui-compat-version-xyz
    
    </th>
    <th valign="top">

    Default feature xyz
    
    </th>
    <th valign="top">

    Resulting compatibility version
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    \--
    
    </td>
    <td valign="top">
    
    \--
    
    </td>
    <td valign="top">
    
    1.14
    
    </td>
    <td valign="top">
    
    1.14
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    1.16

    \(deprecated\)
    
    </td>
    <td valign="top">
    
    \--
    
    </td>
    <td valign="top">
    
    1.14
    
    </td>
    <td valign="top">
    
    1.16
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    \--
    
    </td>
    <td valign="top">
    
    1.16
    
    </td>
    <td valign="top">
    
    1.14
    
    </td>
    <td valign="top">
    
    1.16
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    1.18

    \(deprecated\)
    
    </td>
    <td valign="top">
    
    1.16
    
    </td>
    <td valign="top">
    
    1.14
    
    </td>
    <td valign="top">
    
    1.16
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    edge
    
    </td>
    <td valign="top">
    
    ..
    
    </td>
    <td valign="top">
    
    1.14
    
    </td>
    <td valign="top">
    
    1.18
    
    </td>
    </tr>
    </table>
    

OpenUI5 supports the following compatibility version flags:


<table>
<tr>
<th valign="top">

Flag

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`data-sap-ui-compat-version-sapMeTabContainer`

</td>
<td valign="top">

The `TabContainer` was deprecated in 1.15. When the compatibility version is 1.16 or higher, an error is logged to the console indicating that `sap.m.IconTabBar` should be used instead.

Default value: 1.14

</td>
</tr>
<tr>
<td valign="top">

`data-sap-ui-compat-version-sapMeProgessIndicator`

</td>
<td valign="top">

\--

</td>
</tr>
<tr>
<td valign="top">

`data-sap-ui-compat-version-sapMGrowingList`

</td>
<td valign="top">

\--

</td>
</tr>
<tr>
<td valign="top">

`data-sap-ui-compat-version-sapMListAsTable`

</td>
<td valign="top">

\--

</td>
</tr>
<tr>
<td valign="top">

`data-sap-ui-compat-version-sapMDialogWithPadding`

</td>
<td valign="top">

By default, the content area of `Dialog` had paddings. To make the padding consistent with other popups, the padding is removed for compatibility versions 1.16 or higher. If the padding is still needed inside the content area of `Dialog`, you can use the [Container Content Padding CSS Classes](Using_Container_Content_Padding_CSS_Classes_c71f6df.md).

Default value: 1.14

</td>
</tr>
</table>

**Related Information**  


[Compatibility Rules](Compatibility_Rules_91f0873.md "The following sections describe what SAP can change in major, minor, and patch releases. Always consider these rules when developing apps, features, or controls with or for OpenUI5.")

