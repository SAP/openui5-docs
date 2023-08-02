<!-- loiod6c0a5ddc7694b3da3a4f67391b90b21 -->

| loio |
| -----|
| d6c0a5ddc7694b3da3a4f67391b90b21 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/d6c0a5ddc7694b3da3a4f67391b90b21) | [demo kit latest release](https://sdk.openui5.org/topic/d6c0a5ddc7694b3da3a4f67391b90b21)</div>

## Details on ECMAScript Support in OpenUI5

With OpenUI5 version 1.117, UI5 supports the usage of ECMAScript 2022 language features and syntax, allowing you to make your code more modern and readable. There are a few restrictions imposed by UI5 which have to be considered, however.

> ### Caution:  
> The restrictions described here apply to the usage of ES2022 features in projects that are written in native JavaScript. If your project is written, for instance, in TypeScript, you have to make sure that the listed constraints are met by the transpiled code.

***

<a name="loiod6c0a5ddc7694b3da3a4f67391b90b21__section_n3d_dkv_hyb"/>

### ECMAScript Classes

Classes are at the core of object-oriented programming. With ES2015, the class syntax was introduced into the world of JavaScript, allowing you to structure your code in a much better way. However, since the "classic" UI5 classes are still written as ES5 functions, there are some restrictions or incompatibilities you have to consider when introducing ECMAScript classes into your UI5 project.

The following subsections describe differences between UI5 classes and ECMAScript classes and highlight the limitations when mixing both worlds.

> ### Caution:  
> Extending UI5 classes using ECMAScript classes is currently **not** supported.

***

#### ES6 Subclasses Do Not Support Managed Settings

Extending UI5 classes by using an ES6 class is technically possible, but limited to subclasses that do not introduce new managed settings \(properties, aggregations, associations\). There is currently no way to introduce managed settings other than by using the `sap.ui.base.Object.extend` call. Managed settings in UI5 are required e.g. for enabling data binding and managing the state of an object.

The following sample shows a custom control introducing a new `myCustomValue` property. Here, the regular UI5 `.extend` call is required:

```
sap.ui.define(["sap/ui/core/Control"], function(Control) {
    return Control.extend("my/custom/Control", {
        metadata: {
            properties: {
                myCustomValue: {type : "float", defaultValue : 0}
            }
        }
    });
});
```

***

#### Static Members and Inheritance

In modern JavaScript, classes inherit their static members from their superclass. Yet, as of today, in UI5 \(or when using ES5\) there is no automatic inheritance of static members implemented. However, this becomes a little bit different, again in a mixed scenario, when extending a UI5 class using an ECMAScript class.

To see this in action, let's have a look at UI5 classes only first. In the following sample we look at the `sap/m/Button` class, which extends `sap/ui/core/Element`. The `Element` class has a static function `Element.closestTo`, which is not available to any of its subclasses.

```
// No inheritance of static members in UI5
sap.ui.define([
    "sap/ui/core/Element",
    "sap/m/Button"], function(Element, Button) {
    console.log(typeof Element.closestTo == "function"); // true
    console.log(typeof Button.closestTo == "function"); // false
});
```

***

<a name="loiod6c0a5ddc7694b3da3a4f67391b90b21__section_wjx_jmv_hyb"/>

### Language Features

The following subsections describe restrictions regarding certain language features:

***

#### `async` / `await`

The `async` / `await` syntax allows you to work with Promises in a very comfortable way. Yet, please be aware that UI5 does not account for the resulting asynchronicity \(Promises\) in certain situations, e.g. in the context of the UI5 Loader, or when registering for events.

***

#### UI5 Loader

In the following example, we define a class called `MyCustomControl` and declare the factory function as an async function by using the `async` keyword. Inside this function, there is another async function called `fnAsync` which gets executed with the `await` expression. This makes JavaScript wait until the Promise of that function settles and returns its result. Since an async function is used here as a factory, the module content becomes a Promise.

```
// example of using async / await in UI5 modules
// module file MyCustomControl.js
sap.ui.define(["sap/ui/core/Control"], async function(Control) { // async factory function
    var MyCustomControl = Control.extend("MyCustomControl", {});
    var fnAsync = async function() {
        // do something async... e.g. send a request
    };
    await fnAsync(); // wait for fnAsync...
    return MyCustomControl;
});
```

If we require this module e.g. via `sap.ui.require`, we now need to deal with that Promise. The UI5 Loader does not wait for any Promises \(to be resolved\) that are provided as module content, but passes this Promise directly to the callback. This is in line with specified AMD behavior.

```
sap.ui.require(["MyCustomControl"], function(MyCustomControlPromise) {
 // module content is a Promise
 MyCustomControlPromise.then(function(MyCustomControlClass) {
    new MyCustomControlClass();
 });
});
```

***

#### Event Registration

> ### Caution:  
> If you intend to use async functions as callbacks or hooks, you have to make sure that the respective API doesn't break and that you stay compliant with the API's signature and return value type. For example, an. API which expects no return value should not return a Promise.

When registering to browser or control events and implementing an event handler as an async function \(see the following sample\), UI5 simply calls the event handler function without handling the returned Promise and without considering the execution order.

```
/sap.ui.require(["sap/m/Button"], (Button) => {
    const oButton = new Button({
        text: "Press me",
        press: async (event) => { // async event handler function
            await doSomething() // do something async, e.g. request data and wait for it...
            console.log("Data received!");
        }
    });
});
```

As an alternative, you can wrap your async function, as in the following sample:

```
sap.ui.require(["sap/m/Button"], (Button) => {
    const oButton = new Button({
        text: "Press me",
        press: () => {
            (async () => { // async wrapper
                await doSomething() // do something async, e.g. request data and wait for it...
                console.log("Data received!");
            })()
        }
    });
});
```

***

#### Async `sap.ui.core.UIComponent#createContent` Hook

The following code block shows an example in the context of the asynchronous `sap.ui.core.UIComponent#createContent` hook method, where you can use an async function. Only if the UIComponent implements the `sap.ui.core.IAsyncContentCreation` interface, the return type of this method will be a Promise, which will then be chained into the resulting Promise of the component creation procedure.

```
sap.ui.define(["sap/ui/core/UIComponent", "sap/ui/core/xml/XMLView"], function(UIComponent, XMLView) {
    return UIComponent.extend("my.sample", {
        metadata: {
            // ...
            interfaces: ["sap.ui.core.IAsyncContentCreation"]
        },
        createContent: async () => {
            // Dynamically create a root view
            return XMLView.create({...});
        }
    });
});
```

