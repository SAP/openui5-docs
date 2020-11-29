<!-- loioc71f6df62dae47ca8284310a6f5fc80a -->

| loio |
| -----|
| c71f6df62dae47ca8284310a6f5fc80a |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/c71f6df62dae47ca8284310a6f5fc80a) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/c71f6df62dae47ca8284310a6f5fc80a)</div>

## Using Container Content Padding CSS Classes

For many container controls in OpenUI5, such as a Dialog or a Page, you can define whether the container should have a padding within the content area. A padding clears the area between the container layout and the controls that are displayed in the content area.

You can either choose to have no padding, a small padding, or a responsive padding that is based on the user’s screen size.

The following CSS classes for content padding are provided by OpenUI5:

  2.  **sapUiNoContentPadding**
 4.  **sapUiContentPadding**
 6.  **sapUiResponsiveContentPadding**
  

The effects of these paddings will be different depending on the container that is being used:

-   If the container is defining a padding on its content area by default, then setting **sapUiNoContentPadding** in the application code will remove the padding and thus not display any space between the container layout and the content controls.
-   If the container is defining no padding on its content by default, then setting **sapUiContentPadding** will add 1rem \(16px\) of padding around the content area to layout the content controls.
-   Setting **sapUiResponsiveContentPadding** on the container control will add a padding based on the user’s screen size. On small screen devices such as smartphones, or when the browser window is resized to a small size, no padding is displayed. On medium screen sizes or applications that are using a `SplitApp`, the control will get 1rem \(16px\) of padding.. Finally, on large screen sizes in full-screen mode, the container control will get 2rem \(32px\) of padding to the left and right and 1rem \(16px\) of padding at the top and bottom.

The following list shows examples of controls that support container content padding CSS classes:

  2.  **sap.f.DynamicPage**
 4.  **sap.f.GridList**
 6.  **sap.f.semantic.SemanticPage**
 8.  **sap.m.Carousel**
 10. **sap.m.Dialog**
 12. **sap.m.IconTabBar**
 14. **sap.m.FlexBox** using `FlexItemData` with `styleClass` property for each item
 16. **sap.m.IconTabBar**
 18. **sap.m.List**
 20. **sap.m.Page**
 22. **sap.m.Panel**
 24. **sap.m.Popover**
 26. **sap.m.ScrollContainer**
 28. **sap.m.TabContainer**
 30. **sap.m.Table**
 32. **sap.ui.layout.BlockLayoutCell**
 34. **sap.ui.layout.DynamicSideContent**
 36. **sap.ui.layout.HorizontalLayout**
 38. **sap.ui.layout.VerticalLayout**
  

***

``` xml

<Page class="sapUiResponsiveContentPadding">
```

***

### Example

You can check how our container padding classes work in the following sample [Samples for `sap.ui.core.ContainerPadding`](https://openui5.hana.ondemand.com/#/entity/sap.ui.core.ContainerPadding).

If you have to apply responsive paddings over separate parts of the control according to the control width, see [Enabling Responsive Paddings According to the Control Width](Enabling_Responsive_Paddings_According_to_the_Control_Width_3b718b5.md)

