<!-- loio3e9c0104db864fbabc9fc786cbdf76a4 -->

| loio |
| -----|
| 3e9c0104db864fbabc9fc786cbdf76a4 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3e9c0104db864fbabc9fc786cbdf76a4) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3e9c0104db864fbabc9fc786cbdf76a4)</div>

## ARIA Attribute Mapping

Navigation with the keyboard and screen reader have to both work properly at the same time. In order for this to happen, you need to use the correct ARIA attributes and to map them to their HTML counterparts.

***

### Attribute Mapping

The ARIA `role=application` is added to the body of each page by OpenUI5 Core to ensure that the page can be properly navigated using the keyboard. If this is not the case, the OpenUI5 JavaScript key handler code may get overridden by the screen reader and this will hinder keyboard handling.

The mapping of HTML attributes to ARIA attributes is described in the following table:Attribute Mapping<a name="loio3e9c0104db864fbabc9fc786cbdf76a4__table_i55_wg4_ds"/>

|HTML Attribute|ARIA Attribute|
|--------------|--------------|
| `editable` | `aria-readonly` |
| `enabled` | `aria-disabled` |
| `visible` | `aria-hidden` |
| `required` | `aria-required` |
| `checked` | `aria-checked` |
| `selected` | `aria-selected` |

For custom controls, not part of the ARIA 1.0 role definitions, mapping to similar and existing ARIA base role concepts is applied. In special cases, custom role names can be added by the OpenUI5 framework using `aria-describedby` or `aria-labelledby` references.

***

### Additional API Associations

In order to ease the setting of ARIA attributes, we have introduced two new associations to the OpenUI5 API:

1.  • ariaLabelledBy - holds a reference to the control that has the `aria-labelledby` attribute set

2.  • ariaDescribedBy - holds a reference to the control that has the `aria-describedby` attribute set


These associations have the following structure:

> Note:
> ```
> ariaLabelledBy : {
> 
> type : "sap.ui.core.Control",
> 
> multiple : true,
> 
> singularName : "ariaLabelledBy"
> 
> }
> 
> ```
> 
> 

> Note:
> ```
> ariaDescribedBy : {
> 
> type : "sap.ui.core.Control",
> 
> multiple : true,
> 
> singularName : "ariaDescribedBy"
> 
> }
> 
> ```
> 
> 

