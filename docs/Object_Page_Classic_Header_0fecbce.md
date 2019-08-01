<!-- loio0fecbce45e39406aa939bd25e89823f4 -->

| loio |
| -----|
| 0fecbce45e39406aa939bd25e89823f4 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/0fecbce45e39406aa939bd25e89823f4) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/0fecbce45e39406aa939bd25e89823f4)</div>

## Object Page Classic Header

Overview of the structure and features for `sap.uxap.ObjectPageLayout`'s classic header.

***

### Main Structure

The `ObjectPageHeader` control consists of two main parts - Header Title and Header Content.

 ![](loioe8468207c7504dcb8126157792b37ecf_HiRes.png) 

1.  Header Title \(`headerTitle`\) - Displayed at the top of the header and always remains visible above the scrollable content of the page. It contains the title and most prominent details of the object.

2.  The Header Content \(`headerContent`\) - Scrolls along with the content of the page until it disappears \(collapsed header\). When scrolled back to the top it becomes visible again \(expanded header\). It contains all the additional information of the object.


   
  
Collapsing and Expanding the Header<a name="loio0fecbce45e39406aa939bd25e89823f4__fig_tzt_2gw_1cb"/>

 ![](loio4e081060fae54366b424de28f722860c_LowRes.gif "Collapsing and Expanding the Header") 

***

### Header Title

This part of the header contains the basic information of the object.

   
  
Navigation bar, Breadcrumbs and Actions in the Header Title<a name="loio0fecbce45e39406aa939bd25e89823f4__fig_a5m_qmh_ccb"/>

 ![](loiob2459223fc504ea1a380590ac0c45a41_HiRes.png "Navigation bar, Breadcrumbs and Actions in the Header Title") 

The top area in the Header Title is for the navigation bar \(`navigationBar`\). It contains the top-most element \(`sap.m.Bar`\) and provides the option to have a *Back* button for returning to the previous selection and navigation actions on the opposite side.

The area below the navigation bar is reserved for breadcrumbs navigation on one side \(`breadcrumbs`\) and actions on the other \(`actions`\). The actions are declared as `sap.uxap.ObjectPageHeaderActionButton` instances.

   
  
Title with Optional Indicators and Subtitle<a name="loio0fecbce45e39406aa939bd25e89823f4__fig_rqv_1vh_ccb"/>

 ![](loio553c7d7128404063a00a4afba69a966d_HiRes.png "Title with Optional Indicators and Subtitle") 

You can set title \(`objectTitle`\) and subtitle \(`objectSubtitle`\). On larger screens the subtitle is displayed next to the title. After a certain breakpoint, the subtitle moves below the title.

You can display several optional indicators right after the title. They are considered part of the title and when there is not enough space they are wrapped and moved to more lines along with the title text.

Optional indicators in the title<a name="loio0fecbce45e39406aa939bd25e89823f4__table_oxs_blm_2cb"/>

|Optional Indicator|API Properties|
|------------------|--------------|
| ![](loio7813cf4ed2754695a91a1aa67e94de39_HiRes.png) *Favorite* | `markFavorite` |
| ![](loio4c5abbfbce524a4aba4e48724c36a345_HiRes.png) *Flagged* | `markFlagged` |
| ![](loio52d023e0f3674110ac99f4a72b74b428_HiRes.png) *Locked* | `markLocked` |
| ![](loiof89451a47cc54e0186d1e597f2f18682_HiRes.png) *Unsaved changes* | `markChanges` |
| ![](loiod7144c249b8d4168a7129f583e7c5674_HiRes.png) *Selector* | `showTitleSelector` |

> Note:
> Keep in mind that *Locked* and *Unsaved changes* are mutually exclusive. If both of them are set to be visible, only the *Locked* state is displayed.
> 
> 

You can show and hide both the markers \(*Favorite* and *Flagged*\) simultaneously with the `showMarkers` boolean property.

   
  
Object Image in Circle and Square Shapes<a name="loio0fecbce45e39406aa939bd25e89823f4__fig_uc4_2rh_ccb"/>

 ![](loiodf92915521c34aaf8e2d1f7e7b509ab7_LowRes.gif "Object Image in Circle and Square Shapes") 

You can add an icon-sized image before the title by defining the image location in the `objectImageURI` property. You can set the text used for the `Alt` and `Tooltip` attributes of the image with the `objectImageAlt` property. To set the shape to `Circle` or `Square`, use the `objectImageShape` property.

You can control whether the image, title, subtitle, and actions are always visible or visible only when the header is collapsed \(snapped\).

> Note:
> To build a custom `headerTitle`, you can extend the `ObjectPageHeader` class and then use any control in the `headerTitle` aggregation. The `ObjectPageLayout`, however, needs correct values for the `objectImageURI` / `objectImageShape` and `headerDesign`, as those properties are important for the `headerContent` in order to style it properly.
> 
> 

***

### Header Content

The second part of the header is the Header Content. This is an aggregation of controls that are displayed in a float layout underneath the Header Title. The controls that can be used in the `headerContent` aggregation are the standard OpenUI5 controls and they are automatically styled to fit the current header style.

With the use of the `sap.uxap.ObjectPageHeaderLayoutData` class, you can specify for each control used in the `headerContent` aggregation, whether it's visible on small, medium or large-sized layouts, what width it takes and whether it has a visual separator displayed before and/or after itself.

   
  
Header Content with `sap.uxap.ObjectPageHeaderLayoutData` - large, middle and small-sized layout<a name="loio0fecbce45e39406aa939bd25e89823f4__fig_azb_j1n_ccb"/>

 ![](loio40e357c0789d4982a5223ea6f9143315_LowRes.gif "Header Content with sap.uxap.ObjectPageHeaderLayoutData - large, middle
					and small-sized layout") 

**Related information**  


[API Reference: `sap.uxap.ObjectPageHeader`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.uxap.ObjectPageHeader.html)

[API Reference: `sap.uxap.ObjectPageHeaderLayoutData`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.uxap.ObjectPageHeaderLayoutData.html)

[API Reference: `sap.uxap.ObjectPageLayout`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.uxap.ObjectPageLayout.html)

[Object Page Headers](Object_Page_Headers_d2ef009.md)

[Object Page Headers Comparison](Object_Page_Headers_Comparison_9c9d94f.md)

