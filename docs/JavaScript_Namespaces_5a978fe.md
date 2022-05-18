<!-- loio5a978fe3504e4dd39f5db0a46438ba64 -->

| loio |
| -----|
| 5a978fe3504e4dd39f5db0a46438ba64 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/5a978fe3504e4dd39f5db0a46438ba64) | [demo kit latest release](https://sdk.openui5.org/topic/5a978fe3504e4dd39f5db0a46438ba64)</div>

## JavaScript Namespaces

OpenUI5 modules such as classes, components, and controls, should use a consistent qualified naming scheme. Each module should reside in a unique namespace.

***

### Naming Conventions

A namespace should be lowercase and each word should be separated by a dot \(`.`\), like the Java package notation. The class name should be camelcase starting with a capital letter.

The namespace gets attached to the [global window object](https://developer.mozilla.org/en-US/docs/Web/API/Window). Therefore, its first segment must not match any global properties, such as "name", "location", "top", "self", ...

In the following example, `my.app` is the general namespace and `my.app.MyControl` is the fully qualified class name.

```js
sap.ui.define(["sap/ui/core/Control"], function(Control) {
    return Control.extend("my.app.MyControl", {});
});
```

For JavaScript global names, module names, and OpenUI5 qualified names \(class names, interface names, DataType names\), use the same naming prefix, only with varying separators. For example, use a slash \(/\) instead of a dot \(.\) when requiring the class from the example above.

```js
sap.ui.define(["my/app/MyControl"], function(MyControl) {
    ...
});
```

> ### Note:  
> To avoid conflicts with other frameworks or developments, the `sap` namespace is reserved for SAP. Therefore, any non-OpenUI5 content, such as application code or custom controls, must **not** use namespaces that start with the `sap` prefix.

