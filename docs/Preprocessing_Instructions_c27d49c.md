<!-- loioc27d49caa48e424eb75391ae85da2134 -->

| loio |
| -----|
| c27d49caa48e424eb75391ae85da2134 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/c27d49caa48e424eb75391ae85da2134) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/c27d49caa48e424eb75391ae85da2134)</div>

## Preprocessing Instructions

Preprocessing intructions are processed by the XML preprocessor when it traverses the view's `XML DOM`.

> ### Note:  
> A model name can be seen as a variable with a value that consists of two parts: a model instance and a binding context path.

You can base conditions on the available variables. XML attributes that represent an available binding are replaced automatically.

-   **[with](with_58cf64c.md "The <template:with> instruction can be used to change a variable's
		value or to add a variable with a new name. ")**  
The `<template:with>` instruction can be used to change a variable's value or to add a variable with a new name.
-   **[repeat](repeat_512e545.md "The <template:repeat instruction iterates the
			sap.ui.model.ListBinding given by the list attribute. ")**  
The `<template:repeat` instruction iterates the `sap.ui.model.ListBinding` given by the `list` attribute.
-   **[if](if_fc18595.md "The <template:if> instruction evaluates a condition expressed
		via existing OpenUI5 data
		binding features, such as extended syntax; in the preprocessing it is removed or replaced by
		its child elements based on the value of this condition. ")**  
The `<template:if>` instruction evaluates a condition expressed via existing OpenUI5 data binding features, such as extended syntax; in the preprocessing it is removed or replaced by its child elements based on the value of this condition.
-   **[alias](alias_ac5751f.md "The <template:alias> instruction can be used to define a shortcut
		alias name for a JavaScript value, for example a static helper class, a formatter function,
		or a helper function.")**  
The `<template:alias>` instruction can be used to define a shortcut alias name for a JavaScript value, for example a static helper class, a formatter function, or a helper function.
-   **[require](require_263f6e5.md "The template:require attribute can be used at the root element of an
		XML template view or fragment. You can specify a list of required modules as Unified
		Resource Names, similar to sap.ui.require, and assign aliases to them using
		a JSON-like syntax. The aliases can then be used to access the modules in the same way
			<template:alias> works. (This requires that the view is loaded
		asynchronously.)")**  
The `template:require` attribute can be used at the root element of an XML template view or fragment. You can specify a list of required modules as Unified Resource Names, similar to `sap.ui.require`, and assign aliases to them using a JSON-like syntax. The aliases can then be used to access the modules in the same way `<template:alias>` works. \(This requires that the view is loaded asynchronously.\)
-   **[Replacement of Bindings](Replacement_of_Bindings_604b1eb.md "For attributes, OpenUI5
		binding expressions are used instead of preprocessing instructions. If the value of an XML
		attribute represents a valid OpenUI5 binding which refers to
		currently available model (= variable) names only, the binding is
		evaluated and the result is written back into the XML attribute.")**  
For attributes, OpenUI5 binding expressions are used instead of preprocessing instructions. If the value of an XML attribute represents a valid OpenUI5 binding which refers to currently available model \(= *<variable\>*\) names only, the binding is evaluated and the result is written back into the XML attribute.
-   **[XML Fragments](XML_Fragments_65da02b.md "OpenUI5 fragments of type
		XML are used in the context of XML templating to provide reuse parts for
		templates.")**  
OpenUI5 fragments of type XML are used in the context of XML templating to provide reuse parts for templates.
-   **[Extension Points](Extension_Points_b15e6af.md "Extension points can be used in XML templating to extend the standard with custom
		content.")**  
Extension points can be used in XML templating to extend the standard with custom content.

