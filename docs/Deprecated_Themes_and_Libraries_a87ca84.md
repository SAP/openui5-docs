<!-- loioa87ca843bcee469f82a9072927a7dcdb -->

| loio |
| -----|
| a87ca843bcee469f82a9072927a7dcdb |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/a87ca843bcee469f82a9072927a7dcdb) | [demo kit latest release](https://sdk.openui5.org/topic/a87ca843bcee469f82a9072927a7dcdb)</div>

## Deprecated Themes and Libraries

As OpenUI5 evolves over time, some of the UI controls are replaced by others, or their concepts abandoned entirely. This chapter gives an overview on theme and library level of the most important deprecations. Individual control deprecations and more information about the controls replacing them can be found in the API reference within the Demo Kit.

***

### Themes that are no longer supported

The following themes have been deprecated and/or removed entirely:

**Deprecated Themes**


<table>
<tr>
<th valign="top">

Theme

</th>
<th valign="top">

Deprecated as of

</th>
<th valign="top">

Removed as of

</th>
<th valign="top">

Recommendation\(\*\)

</th>
</tr>
<tr>
<td valign="top">

`sap_fiori_3` \(Quartz\)

</td>
<td valign="top">

1.120

</td>
<td valign="top">

 

</td>
<td valign="top">

Do not use for new projects.

</td>
</tr>
<tr>
<td valign="top">

`sap_belize` 

</td>
<td valign="top">

1.120

</td>
<td valign="top">

 

</td>
<td valign="top">

Switch to `sap_horizon`.

</td>
</tr>
<tr>
<td valign="top">

`sap_hcb` 

</td>
<td valign="top">

1.48

</td>
<td valign="top">

 

</td>
<td valign="top">

Switch to `sap_horizon_hcb`.

</td>
</tr>
<tr>
<td valign="top">

`sap_bluecrystal` 

</td>
<td valign="top">

1.40

</td>
<td valign="top">

 

</td>
<td valign="top">

Switch to `sap_horizon`.

</td>
</tr>
<tr>
<td valign="top">

`sap_ux` 

</td>
<td valign="top">

1.40

</td>
<td valign="top">

1.48

</td>
<td valign="top">

n/a

</td>
</tr>
<tr>
<td valign="top">

`sap_platinum` 

</td>
<td valign="top">

1.40

</td>
<td valign="top">

1.48

</td>
<td valign="top">

n/a

</td>
</tr>
<tr>
<td valign="top">

`sap_goldreflection` 

</td>
<td valign="top">

1.40

</td>
<td valign="top">

1.48

</td>
<td valign="top">

n/a

</td>
</tr>
</table>

\(\*\) Also valid for custom themes based on the respective theme

For a list of the available themes, see [Available Themes](Available_Themes_da0d2e7.md).

***

### Deprecated Libraries

The following libraries have been deprecated and/or removed entirely:

**Deprecated Libraries**


<table>
<tr>
<th valign="top">

Library

</th>
<th valign="top">

Deprecated as of

</th>
<th valign="top">

Note

</th>
</tr>
<tr>
<td valign="top">

`sap.ui.suite`

</td>
<td valign="top">

1.108

</td>
<td valign="top">

Partly deprecated. For the deprecated parts, see [API Reference: `sap.ui.suite`](https://sdk.openui5.org/api/sap.ui.suite). 

</td>
</tr>
<tr>
<td valign="top">

`sap.landvisz`

</td>
<td valign="top">

1.98

</td>
<td valign="top">

Removed as of 1.120

</td>
</tr>
<tr>
<td valign="top">

`sap.ui.vtm`

</td>
<td valign="top">

1.96.10

</td>
<td valign="top">

Partly deprecated. For the deprecated parts, see [API Reference: `sap.ui.vtm`](https://sdk.openui5.org/api/sap.ui.vtm). 

</td>
</tr>
<tr>
<td valign="top">

`sap.zen.commons`

</td>
<td valign="top">

1.89

</td>
<td valign="top">

Partly deprecated. For the deprecated parts, see [API Reference: `sap.zen.commons`](https://sdk.openui5.org/api/sap.zen.commons). 

</td>
</tr>
<tr>
<td valign="top">

`sap.zen.crosstab`

</td>
<td valign="top">

1.89

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`sap.zen.dsh`

</td>
<td valign="top">

1.89

</td>
<td valign="top">

Partly deprecated. For the deprecated parts, see [API Reference: `sap.zen.dsh`](https://sdk.openui5.org/api/sap.zen.dsh). 

</td>
</tr>
<tr>
<td valign="top">

`sap.ui.commons`

</td>
<td valign="top">

1.38

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`sap.ui.ux3`

</td>
<td valign="top">

1.38

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`sap.makit`

</td>
<td valign="top">

1.38

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`sap.me`

</td>
<td valign="top">

1.34

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`sap.ca`

</td>
<td valign="top">

1.22

</td>
<td valign="top">

Partly deprecated. For the deprecated parts, see [API Reference: `sap.ca`](https://sdk.openui5.org/api/sap.ca). 

</td>
</tr>
</table>

To find out whether these libraries have been replaced by other content, check them at [API Reference: `deprecated`](https://sdk.openui5.org/api/deprecated).

**Related Information**  


[Index of Deprecated APIs](https://sdk.openui5.org/api/deprecated)

[Supported Library Combinations](Supported_Library_Combinations_363cd16.md "OpenUI5 provides a set of JavaScript and CSS libraries, which can be combined in an application using the combinations that are supported.")

[Supported Combinations of Themes and Libraries](Supported_Combinations_of_Themes_and_Libraries_38ff8c2.md "This chapter gives an overview of the possible combinations of themes and libraries for the OpenUI5 versions that are still in maintenance.")

[Available Themes](Available_Themes_da0d2e7.md "Provides a list of themes and their names.")

