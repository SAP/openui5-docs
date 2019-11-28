<!-- loio3b718b5372fa457c92cf5087a673e953 -->

| loio |
| -----|
| 3b718b5372fa457c92cf5087a673e953 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3b718b5372fa457c92cf5087a673e953) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3b718b5372fa457c92cf5087a673e953)</div>

## Enabling Responsive Paddings

Apply responsive paddings over separate parts of the controls.

> Note:
> You can enable the responsive paddings only for the SAP Quartz themes.
> 
> 

***

<a name="loio3b718b5372fa457c92cf5087a673e953__section_d2f_1pv_jjb"/>

### Usage

As a control developer, you can enable application developers to apply responsive paddings over separate parts of the controls. If you implement `sap.ui.core.util.ResponsivePaddingsEnablement`, the breakpoints and layout paddings are determined by the container's width.

***

#### How to Enable Responsive Paddings

Here is an example of how to implement the utility when you are developing a control:

```
ResponsivePaddingsEnablement.call(MyCustomControl.prototype, {
					header: {suffix: "-myCustomControlHeader"},
					content: {selector: ".myCustomControlContent"}
					});
				
```

As the example demonstrates, there are two ways to select an element:

-   Using suffix: This enables you to select an element by its ID.
-   Using selector: This covers all possible CSS selections.

To call the utility, when initializing the control, use:

```
MyCustomControl._initResponsivePaddingsEnablement()
```

As a result, application developers will be able to use classes, such as `sapUiResponsivePadding—header` and `sapUiResponsivePadding—content`, to enable the paddings on the respective element.

***

#### Applied Paddings

Based on the container’s size, one of the following classes is added, and the corresponding padding-left and padding-right are applied:

|Container Size \(pixels\)|Class|Padding-Left and Padding-Right Applied|
|-------------------------|-----|--------------------------------------|
|<= 600|sapM-Std-PaddingS|1rem|
|\>600|sapM-Std-PaddingM|2rem|
|\>1024|sapM-Std-PaddingL|2rem|
|\>1440|sapM-Std-PaddingXL|3rem|

***

#### Supported Controls

The following list shows the controls that support responsive paddings:

-   `sap.m.Page`
-   `sap.m.Popover`
-   `sap.m.Dialog`
-   `sap.m.Wizard`

To enable this concept and to add responsive paddings to an element of the controls, add the following classes to the controls, depending on your use case:

|`sap.m.Page`|`sap.m.Popover`, `sap.m.Dialog`|`sap.m.Wizard`|
|------------|-------------------------------|--------------|
| `sapUiResponsivePadding—header` `sapUiResponsivePadding—subHeader` `sapUiResponsivePadding—content` `sapUiResponsivePadding—footer` `sapUiResponsivePadding—floatingFooter` | `sapUiResponsivePadding—header` `sapUiResponsivePadding—subHeader` `sapUiResponsivePadding—content` `sapUiResponsivePadding—footer` | `sapUiResponsivePadding—header` `sapUiResponsivePadding—content` |

***

```
<Page class="sapUiResponsivePadding--header sapUiResponsivePadding--subHeader sapUiResponsivePadding--content sapUiResponsivePadding--footer sapUiResponsivePadding--floatingFooter">
```

For a detailed example, see the [Samples for `sap.m.Page`](https://openui5.hana.ondemand.com/#/entity/sap.m.Page). 

