<!-- loio148892ff9aea4a18b912829791e38f3e -->

| loio |
| -----|
| 148892ff9aea4a18b912829791e38f3e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/148892ff9aea4a18b912829791e38f3e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/148892ff9aea4a18b912829791e38f3e)</div>

## Tables: Which One Should I Choose?

The libraries provided by OpenUI5 contain various different table controls that are suitable for different use cases. The table below outlines which table controls are available, and what features are supported by each one.

Overview of Tables and Supported Features<a name="loio148892ff9aea4a18b912829791e38f3e__table_uzb_zmy_vs"/>

|Feature Supported?|Responsive Table [\(sap.m.Table\)](https://openui5.hana.ondemand.com/#/api/sap.m.Table) |Grid Table [\(sap.ui.table.Table\)](https://openui5.hana.ondemand.com/#/api/sap.ui.table.Table) |Analytical Table [\(sap.ui.table.AnalyticalTable\)](https://openui5.hana.ondemand.com/#/api/sap.ui.table.AnalyticalTable) |Tree Table [\(sap.ui.table.TreeTable\)](https://openui5.hana.ondemand.com/#/api/sap.ui.table.TreeTable) |
|------------------|---------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
|Desktop| ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|Touch device \(`sap.ui.table`\*: not valid for phones\)| ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|Responsive \(hide column, popin support\)| ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
|Compact density| ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|Condensed density| ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|Cozy density| ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|Summarized cell| ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
|Hierarchical data| ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|Large number of rows \(\> 100\)| ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|Grouping| ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
|Freeze columns| ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|Horizontal scrolling| ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|Merge duplicates| ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
|Supported controls|Supports all kinds of controls inside a line item|Supports a limited set of controls<sup>1</sup> |Supports a limited set of controls<sup>1</sup> |Supports a limited set of controls<sup>1</sup> |
|Row-based| ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) |
|Column-based| ![No](loio5befb5af20ed42fd9052a99014d953a3_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) | ![Yes](loio3cb17ee88aed44d2bf1d14b97728c709_LowRes.gif) |
|OData-based|Requires manual modifications|Requires manual modifications|Requires manual modifications|Requires manual modifications|

1\) `Text`, `Label`, `ObjectStatus`, `Icon`, `Button`, `Input`, `DatePicker`, `Select`, `ComboBox`, `MultiComboBox`, `CheckBox`, `Link`, `Currency`, `RatingIndicator`, `ProgressIndicator`; To keep the control height always stable, the `wrapping` and `renderWhitespace` properties in the `sap.m.Text` control, for example, must be set to `false`. For more information, search for cell level in the  [SAP Fiori Design Guidelines](https://experience.sap.com/fiori-design-web/).

