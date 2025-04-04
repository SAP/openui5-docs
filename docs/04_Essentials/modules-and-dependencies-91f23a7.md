<!-- loio91f23a736f4d1014b6dd926db0e91070 -->

## Modules and Dependencies

The OpenUI5 framework has built-in support for modularizing comprehensive JavaScript applications. That means, instead of defining and loading one large bundle of JavaScript code, an application can be split into smaller parts which then can be loaded at runtime at the time when they are needed. These smaller individual files are called modules.

A module is a JavaScript file that can be loaded and executed in a browser. There are no rules or definitions what code belongs to a module, and what code does **not**. The content bundled in a module is up to the developer, but typically the content has a common topic, such as forming a JavaScript class or namespace or the contained functions address a specific topic, for example client to server communication or mathematical functions.

Modules have no predefined syntax or structure, but module developers can use the following features:

-   **Name**

    The name indentifies the module in connection with the `sap.ui.define` and `sap.ui.require` syntax. A module defined under a certain name can be required using the same name.

-   **Definition**

    Modules have a predefined structure based on the function `sap.ui.define`.

    The `sap.ui.define` syntax for defining modules helps to ensure an asynchronous loading of resources.

    For more information, see the [API Reference: `sap.ui.define`](https://ui5.sap.com/#/api/sap.ui/methods/sap.ui.define). 

-   **Dependencies**

    Every module defines a list of dependencies that have to be resolved before the callback function for the module is executed.

    The dependency declarations can be evaluated at runtime, but can also be analyzed at build time or at deploy time on the server.




## Example

The following code snippet shows a typical module that uses all of features listed above. The name of the module is `someClass`:

```js
  sap.ui.define("SomeClass", ['sap/mylib/Helper', 'sap/m/Bar'], function(Helper, Bar) {
 
    // create a new class
    var SomeClass = function () {};
 
    // add methods to its prototype
    SomeClass.prototype.foo = function () {
 
        // use a function from the dependency 'Helper' in the same package (e.g. 'sap/mylib/Helper' )
        var mSettings = Helper.foo();
 
        // create and return an sap.m.Bar (using its local name 'Bar')
        return new Bar(mSettings);
    };
    // return the class as module value
    return SomeClass;
 
  });
 
 
// later requiring the previously defined module
sap.ui.require(['SomeClass'], function(SomeClass) {
    var oInstance = new SomeClass();
});
```



<a name="loio91f23a736f4d1014b6dd926db0e91070__section_ntl_h3h_yy"/>

### Static and Dynamic Dependencies

Adding each and every dependency to the `sap.ui.define` call can lead to many modules that have to be loaded before your module can be executed. Often, dependencies are not needed initially when the module is started. For rarely or not immediately used references, it might be overhead to load them in advance before executing your module.

Therefore, you have to decide whether you want to use static or dynamic dependencies:

-   **Static** dependencies are loaded in the dependency declaration array of the `sap.ui.define` call. These dependencies are always loaded in advance before executing the defined module:

    ```js
    sap.ui.define(['sap/m/Input'], function(Input) {
     
        // callback is executed once all dependencies are loaded
        ...
    });
    ```

-   **Dynamic** dependencies are resolved on demand after the initial module execution as they're not needed for the initialisation of the module and are often tied to a conditional or a user interaction.

    Dynamic dependencies should always be loaded asynchronously via `sap.ui.require`. The use of `jQuery.sap.require` is synchronous and considered bad practice because the synchronous `XMLHttpRequest` has been deprecated by the Web Hypertext Application Technology Working Group \(WHATWG\).

    When dynamically requiring modules, the callback function will be called once all referenced modules \(and their dependencies\) are fully loaded:

    ```js
    sap.ui.define(['sap/m/Input'], function(Input) {
     
        var MyControl = ...;
     
        MyControl.prototype.onSavePress = function () {
            // dynamically load a dialog once it is needed
            sap.ui.require(['sap/m/Dialog'], function(Dialog) {
                var oDialog = new Dialog(...);
                oDialog.open(...);
            });
        };
         
        return MyControl;
    });
    ```


> ### Note:  
> Many code samples in the OpenUI5 documentation use the `sap.ui.require` syntax even though we could also have used `sap.ui.define`.



<a name="loio91f23a736f4d1014b6dd926db0e91070__section_sjt_2x3_12c"/>

### JavaScript Namespaces

OpenUI5 modules such as classes, components, and controls, should use a consistent qualified naming scheme. Each module should reside in a unique namespace.

A namespace should be lowercase, and each word should be separated by a dot \(`.`\), like for the Java package notation. The class name should be upper camel case \(i.e., starting with a capital letter\).

The namespace gets attached to the [global window object](https://developer.mozilla.org/en-US/docs/Web/API/Window). Therefore, its first segment must not match any global properties, such as "name", "location", "top", "self", ...

In the following example, `my.app` is the general namespace, and `my.app.MyControl` is the fully qualified class name.

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
> To avoid conflicts with other frameworks or developments, the `sap` namespace is reserved for SAP. Therefore, any non-OpenUI5 content, such as application code or custom controls, must **not** use namespaces starting with the `sap` prefix.

