<!-- loioc78c07c094e04ccfaab659378a1707c7 -->

| loio |
| -----|
| c78c07c094e04ccfaab659378a1707c7 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/c78c07c094e04ccfaab659378a1707c7) | [demo kit latest release](https://sdk.openui5.org/topic/c78c07c094e04ccfaab659378a1707c7)</div>

## Creating Control and Class Modules

Modules not only require and use functionality from other modules, they can also expose their own functionality.

In asynchronous module definition \(AMD\) syntax, there are several ways to do this. When working with OpenUI5, we recommend using the "module return value".

> ### Note:  
> It is best practice to avoid the usage of global names. For more information, see [Best Practices for Developers](Best_Practices_for_Developers_28fcd55.md).

If you want to export the "module value" of an AMD module under a global name, you can rely on the OpenUI5 methods that already do the exposure as a side effect, such as:

-   Classes created by the `extend` method

-   Renderers that are created with `sap.ui.core.Renderer.extend("…")`


In control and class modules, you should not use global variables at all. When you derive a custom control from an existing superclass via the `extend` method, the resulting subclass is returned.

You can store the return value of the extend function in a local variable, make changes to the prototype and then return this variable as the module's return value.

JSDoc for the class should use the `@alias` tag to make sure that the variable is known under the global name in the generated JSDoc.

The `extend` function makes sure that the respective namespace is created:

```js
sap.ui.define(["sap/ui/base/Object", "sap/ui/model/json/JSONModel"], function (BaseObject, JSONModel) {
  
    var Foo = BaseObject.extend("foo.bar.MyClass", /** @lends foo.bar.MyClass */ {
  
      constructor: function(sId, mProperties) {
        this.mId = sId;
      }
    });
 
    Foo.prototype.ownMethod = function (a) {
        return a * 2;
    };
  
    // return the module value, in this example a class
    return Foo;
});
```

**Related Information**  


[Example for Defining a Class](Example_for_Defining_a_Class_f6fba4c.md "Full example of a class definition, including JSDoc")

