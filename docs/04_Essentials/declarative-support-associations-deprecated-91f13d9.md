<!-- loio91f13d9a6f4d1014b6dd926db0e91070 -->

# Declarative Support: Associations \(deprecated\)

An association is defined as a data attribute of the HTML tag. Instead of passing the reference to another control you define the ID of another control.

> ### Caution:  
> Deprecated as of UI5 version 1.120, replaced by [XML View](xml-view-91f2928.md).

The following code gives an example:

```html

<div data-sap-ui-type="sap.m.Label" data-text="Message:" data-label-for="message"></div>
<div data-sap-ui-type="sap.m.Input" id="message"></div>
```

The code snippet defines the link between `Label` and `Input` by using the ID of `Input` as a value for the `data-label-for` attribute of the `Label`.

