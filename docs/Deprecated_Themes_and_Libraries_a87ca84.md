<!-- loioa87ca843bcee469f82a9072927a7dcdb -->

| loio |
| -----|
| a87ca843bcee469f82a9072927a7dcdb |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a87ca843bcee469f82a9072927a7dcdb) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a87ca843bcee469f82a9072927a7dcdb)</div>

## Deprecated Themes and Libraries

As OpenUI5 evolves over time, some of the UI controls are replaced by others, or their concepts abandoned entirely. This chapter gives an overview on theme and library level of the most important deprecations. Individual control deprecations and more information about the controls replacing them can be found in the API reference within the Demo Kit.

***

### Themes that are no longer supported

***

#### sap\_hcb

The **sap\_hcb** theme is deprecated as of version 1.48. It has been replaced by the **sap\_belize\_hcb** theme.

**sap\_hcb** is the High Contrast Black theme used for the already deprecated **sap\_goldreflection** and **sap\_bluecrystal** themes. For **sap\_belize** and **sap\_belize\_plus** there are two high contrast themes available: **sap\_belize\_hcb** \(High Contrast Black\) and **sap\_belize\_hcw** \(High Contrast White\).

***

#### sap\_bluecrystal

The **sap\_bluecrystal** theme is no longer supported as of version 1.40. It has been replaced by **sap\_belize** as the default theme for OpenUI5 applications.

Custom themes based on `sap_bluecrystal` are no longer supported with 1.40 or higher.

***

#### sap\_ux

The **sap\_ux** theme is no longer supported as of version 1.40. This was one of the very first OpenUI5 themes and is only implemented by a small subset of the **sap.ui.commons** and **sap.ui.ux3** controls, which are also deprecated.This theme has been removed with OpenUI5 version 1.48.

***

#### sap\_platinum

The **sap\_platinum** theme is no longer supported as of version 1.40. This was one of the very first OpenUI5 themes and is only implemented by a small subset of the **sap.ui.commons** and **sap.ui.ux3** controls, which are also deprecated. This theme has been removed with OpenUI5 version 1.48.

***

#### sap\_goldreflection

The **sap\_goldreflection** theme is no longer supported as of version 1.40. This was one of the first OpenUI5 themes and is only implemented by the **sap.ui.commons** and **sap.ui.ux3** controls, which are also deprecated. This theme has been removed with OpenUI5 version 1.48.

***

### Deprecated Libraries

***

#### sap.ui.commons

The **sap.ui.commons** library is deprecated as of version 1.38.

**sap.ui.commons** was available from the very beginning of OpenUI5. It contains a large number of basic UI controls like buttons, input fields and dropdowns. With version 1.16, the **sap.m** library was introduced. It contains semantically identical controls \(button, input and select\) that, at that time, were only supported on mobile platforms. In later versions, **sap.m** was extended to support desktop platforms as well. For more information about this, see [Browser and Platform Support](Browser_and_Platform_Support_74b59ef.md). The **sap.m** controls were bigger in size to support mobile displays that require a larger touch area. The “Compact Content Density” feature explained under [Content Densities](Content_Densities_e54f729.md) was then added to OpenUI5, allowing you to display a control in a more compact screen size. Today, applications should be built one single time using **sap.m** \(and other libraries\) and their content density switched at runtime depending on the environment. As such, the redundant library **sap.ui.commons** should no longer be used.

Some of the controls in **sap.ui.commons.layout** have been replaced by the new dedicated layout library called **sap.ui.layout**, which runs on the same platforms as **sap.m**.

Some of the old controls have been made available again through the non-deprecated **sap.ui.unified** library \(e.g. FileUploader, Menu\), which runs on the same platforms as **sap.m**.

Some concepts such as Accordion and Row Repeater have been abandoned completely.

***

#### sap.ui.ux3

The **sap.ui.ux3** library is deprecated as of version 1.38.

This library contains more complex UI controls that were based on **sap.ui.commons** along the UX3 design approach. The **sap.m** library - successor to **sap.ui.commons** - implements SAP’s new SAP Fiori design \[http://experience.sap.com/fiori-design/\], which supersedes UX3. As such, the **sap.ui.ux3** library is also deprecated. Some of the UX3 concepts are reflected in SAP Fiori, some are abandoned, as outlined in the following table:

|Concept|What's Happened?|
|-------|----------------|
|Feeds|Replaced by sap.m \(`sap.m.Feed`\*\).|
|Notification Bar|Replaced by sap.m \(`sap.m.MessagePopover` and `sap.m.semantic`\*\).|
|Thing Inspector|Indirectly replaced by a different design for displaying object data.|
|Shell|Partially replaced by `sap.ui.unified.Shell`.|
|Data Set|Not part of SAP Fiori.|
|Exact|Not directly part of SAP Fiori. Use `sap.ui.comp.FilterBar` or `sap.m.IconTabBar` for filtering.|
|Quick Views|Concept abandoned as the concept of “hovering with the mouse pointer over a control” does not exist on mobile devices.|

For more information about the SAP Fiori design, see the [SAP Fiori design guidelines](http://experience.sap.com/fiori-design/).

**Related information**  


[Index of Deprecated APIs](https://openui5.hana.ondemand.com/#docs/api/deprecation.html)

[Supported Library Combinations](Supported_Library_Combinations_363cd16.md)

[Supported Combinations of Themes and Libraries](Supported_Combinations_of_Themes_and_Libraries_38ff8c2.md)

