<!-- loio2421a2c9fa574b2e937461b5313671f0 -->

| loio |
| -----|
| 2421a2c9fa574b2e937461b5313671f0 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/2421a2c9fa574b2e937461b5313671f0) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/2421a2c9fa574b2e937461b5313671f0)</div>

## Namespaces in XML Views

The names of the OpenUI5 control libraries and the related subpackages are mapped to XML namespaces.

One of the required namespaces can be defined as the default namespace. The control tags for this namespace do not need a prefix.

The `<View>` tag is required and in the example below, the `mvc` namespace is defined in the first line. You can define any alias for the namespace.

A control can be located in a subpackage of a control library, for example `sap.ui.layout.form.Form` is located in the `sap.ui.layout` library, but the full package name is `sap.ui.layout.form`. You have to specify this subpackage as a separate XML namespace, even if `sap.ui.layout` is already defined as namespace.

``` xml
<mvc:View
   controllerName="..."
   xmlns="sap.ui.layout"
   xmlns="sap.ui.layout.form"
   xmlns:mvc="sap.ui.core.mvc">
</mvc:View>
```

