<!-- copyae1e1520cf714cd99d966bacf5d6e6b2 -->

| loio |
| -----|
| ae1e1520cf714cd99d966bacf5d6e6b2 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ae1e1520cf714cd99d966bacf5d6e6b2) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ae1e1520cf714cd99d966bacf5d6e6b2)</div>

## App or Control Looks Odd

You find yourself in a situation that your app or a control looks different than you expected.

***

<a name="copyae1e1520cf714cd99d966bacf5d6e6b2__section_ivz_vfh_r1b"/>

### Root Cause

This can happen for one of the following reasons:

-   An HTML file is missing the `DOCTYPE` specification \(this leads, for example, to exceptionally high table headers\)

-   Custom styles aren't working properly

-   The theme you are using does not support the used libraries


***

<a name="copyae1e1520cf714cd99d966bacf5d6e6b2__section_u1p_wfh_r1b"/>

### Resolution

To solve the issue, you have the following options:

-   Check whether the `<!DOCTYPE html>` tag is placed at the beginning of each HTML file, before the `<html>` tag.

-   Check if you have used a custom CSS in your app.

    If you have used a custom CSS, it is probably interfering with the styling in the standard OpenUI5 theming libraries.

    Use the developer tools of your browser to inspect the element that has the wrong styling. In the HTML tab, you can usually see which styles are applied to a DOM element. If you have styles in the list that are added by your app, disable these styles in the debugger to see whether this solves the problem.

    > ### Note:  
    > OpenUI5-specific CSS classes and IDs all have an `sapUi` prefix, for example, `sapUiButton`.

    If this does not solve the issue, check for inline styles that are applied to the element in the HTML code. You can also try to isolate the control from the app to see whether there is an issue with the control instead of a collision of styles.

-   Check whether the theme you that you are using is supported in combination with the libraries that you are using in your app. For more information, see [Supported Combinations of Themes and Libraries](Supported_Combinations_of_Themes_and_Libraries_38ff8c2.md) and [Deprecated Themes and Libraries](Deprecated_Themes_and_Libraries_a87ca84.md).


