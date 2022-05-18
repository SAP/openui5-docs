<!-- loiocfcbde260f354bcba07d2686f02a1708 -->

| loio |
| -----|
| cfcbde260f354bcba07d2686f02a1708 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/cfcbde260f354bcba07d2686f02a1708) | [demo kit latest release](https://sdk.openui5.org/topic/cfcbde260f354bcba07d2686f02a1708)</div>

## High Contrast Themes for OpenUI5 Controls

 OpenUI5 offers two high contrast themes for controls - High Contrast Black \(HCB\) and High Contrast White \(HCW\). These themes support people with visual impairments and are required by the **Accessibility** product standard. The themes can be switched on by adding a dedicated URL parameter.

***

### OpenUI5 library support

Currently, the following libraries support the high contrast themes:

-   `sap.f`

-   `sap.m`

-   `sap.tnt`

-   `sap.ui.layout`

-   `sap.ui.suite`

-   `sap.ui.table`

-   `sap.ui.unified`

-   `sap.uxap`


***

### Switching on the HCB theme

You can switch on the High Contrast Black theme by appending the `sap_fiori_3_hcb` URL parameter as in the following example.

> ### Example:  
> HCB Theme Enablement
> 
> <code>http://&lt;hostname&gt;:&lt;port&gt;...?&lt;parameter&gt;=&lt;value&gt;&amp;...&amp;<b>sap_fiori_3_hcb</b></code>

***

### Switching on the HCW theme

You can switch on the High Contrast White theme by appending the `sap_fiori_3_hcw` URL parameter as in the following example.

> ### Example:  
> HCW Theme Enablement
> 
> <code>http://&lt;hostname&gt;:&lt;port&gt;...?&lt;parameter&gt;=&lt;value&gt;&amp;...&amp;<b>sap_fiori_3_hcw</b></code>

> ### Note:  
> Have in mind that OpenUI5 is optimized for the high contrast mode of Windows when using Chrome and Edge. If you have enabled both the Windows contrast setting and the OpenUI5 high contrast theme and you are using browser different than Chrome and Edge, this may cause conflicts, and deficiencies in the theme can occur. In such cases, please switch off the Windows setting or use another browser.

**Related Information**  


[Supported Combinations of Themes and Libraries](Supported_Combinations_of_Themes_and_Libraries_38ff8c2.md "This chapter gives an overview of the possible combinations of themes and libraries for the OpenUI5 versions that are still in maintenance.")

