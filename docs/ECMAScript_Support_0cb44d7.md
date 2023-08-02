<!-- loio0cb44d7a147640a0890cefa5fd7c7f8e -->

| loio |
| -----|
| 0cb44d7a147640a0890cefa5fd7c7f8e |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/0cb44d7a147640a0890cefa5fd7c7f8e) | [demo kit latest release](https://sdk.openui5.org/topic/0cb44d7a147640a0890cefa5fd7c7f8e)</div>

## ECMAScript Support

With OpenUI5 1.116, the framework starts leveraging features of modern ECMAScript, up to and including [ES2022](https://262.ecma-international.org/13.0/). You have to consider certain restrictions when using modern ECMAScript with your UI5 project.

> ### Caution:  
> The restrictions described here apply to the usage of modern ECMAScript features in projects that are written in native JavaScript. If your project is written, for instance, in TypeScript, you have to make sure that the listed constraints are met by the transpiled code.

***

<a name="loio0cb44d7a147640a0890cefa5fd7c7f8e__section_w1y_s25_hyb"/>

### Defining and Loading UI5 Modules

UI5 implements an AMD-like way of [defining and loading modules](Modules_and_Dependencies_91f23a7.md). As Asynchronous Module Definition \(AMD\) is not fully compatible with ECMAScript modules, the use of ECMAScript modules is currently **not** supported.

***

#### ECMAScript Modules

UI5 provides `sap.ui.define` and `sap.ui.require` as the established ways to define and load modules. Using the `import` and `export` statements for loading and defining UI5 modules is currently NOT supported.

Please continue to use the regular UI5 APIs `sap.ui.define` and `sap.ui.require`.

> ### Example:  
> **Supported usage** 
> 
> ```
> // Best practice of loading a module delivered by UI5
> sap.ui.define([
>     "sap/ui/core/mvc/Controller"
> ], (Controller) =>
>     return Controller.extend("my.app.controller.App", {});
> );
> ```

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use ECMAScript import and export statements when loading/defining UI5 modules
> import Controller from "sap/ui/core/mvc/Controller";
> export class MyController extends Controller {};
> ```

***

#### Asynchronous Factory Function

Please do **not** use an `async` factory function when loading or defining UI5 modules. The UI5 Loader will not wait for a returned Promise.

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use the ECMAScript async/await statements when loading/defining modules
> sap.ui.define([
>     "sap/ui/core/mvc/Controller"
> ], async (Controller) =>
>     return Controller.extend("my.app.controller.App", {});
> );
> ```

Please do **not** return a Promise when loading or defining UI5 modules.

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT return a Promise when loading/defining modules
> sap.ui.define([
>     "sap/ui/core/mvc/Controller"
> ], (Controller) => Promise.resolve(Controller.extend("my.app.controller.App", {}));
> );
> ```

***

#### Expressions as Dependencies

Please use only literals but **not** expressions for the dependencies in the context of the `sap.ui.define` and `sap.ui.require` calls.

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use an expression in the list of dependencies
> // in an sap.ui.define or sap.ui.require call.
> const sController = "sap/ui/core/mvc/Controller";
> sap.ui.define([
>   sController
> ], (Controller) => {
> });
> ```

***

#### Spread Elements as Dependencies

Please do **not** use a spread element as a parameter in the context of the `sap.ui.define` and `sap.ui.require` calls.

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use a spread element as a parameter
> // in an sap.ui.define or sap.ui.require call.
> const dependencies = ["sap/ui/core/mvc/Controller", "sap/ui/mode/Filter", "sap/ui/model/FilterOperator", "sap/ui/model/json/JSONModel"];
> sap.ui.define([
>   ...dependencies
> ], (Controller, Filter, FilterOperator, JSONModel) => {
> });
> ```

***

#### Template Literals as Dependencies

The usage of template literals with one or more expressions in the context of the `sap.ui.define` and `sap.ui.require` calls is **not** supported.

> ### Example:  
> **Supported usage** 
> 
> ```
> // Using template literals without any expressions inside
> // an sap.ui.define or sap.ui.require call is supported
> sap.ui.define([
>   `sap/ui/core/mvc/Controller`
> ], (Controller) => {
> });
> ```

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use template literals with one or more
> // expressions inside an sap.ui.define or sap.ui.require call.
> const sLibName = `ui/core`
>  
> sap.ui.define([
>   `sap/{sLibName}/mvc/Controller`
> ], (Controller) => {
> });
> ```

***

<a name="loio0cb44d7a147640a0890cefa5fd7c7f8e__section_cgv_2l5_hyb"/>

### UI5 Inheritance

UI5 implements an own functionality to extend classes \(via the `sap.ui.core.ManagedObject#extend` method\). Using an ECMAScript class to extend a UI5 class is currently **not** supported.

***

#### ECMAScript Classes

UI5 uses its own way of defining classes and extending them. Please stick to the current best practice and do **not** use ECMAScript classes when extending a delivered UI5 class. For more information, see [Details on ECMAScript Support in OpenUI5](Details_on_ECMAScript_Support_in_OpenUI5_d6c0a5d.md).

> ### Example:  
> **Supported usage** 
> 
> ```
> // Best practice of extending an existing class delivered by UI5
> sap.ui.define(["sap/ui/core/Control"], (Control) =>
>   return Control.extend("my.lib.MyControl", {});
> );
> ```

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do not use ECMAScript classes when extending a delivered UI5 class
> sap.ui.define(["sap/ui/core/Control"], (Control) =>
>     return class MyControl extends Control {};
> );
> ```

***

#### Expressions as Class Name

Please do **not** use an expression, only a literal, in the class name parameter inside the `extend` call.

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use an expression in the class name parameter inside the extend call
> const sLibName = "my.lib";
> sap.ui.define([
>     "sap/ui/core/Control"
> ], (Control) => 
>     return Control.extend(sLibName + "MyControl", {});
> );
> ```

***

#### Variable Usage as Class Name

Please do **not** use a variable as the class name parameter inside the `extend` call.

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use a variable as a parameter inside the extend call
> const sControl = "sap/ui/core/Control";
> sap.ui.define([
>     "sap/ui/core/Control"
> ], (Control) => 
>     return Control.extend(sControl, {});
> );
> ```

***

#### Template Literal as Class Name

The usage of template literals with one or more expressions as the class name parameter inside the `extend` call is **not** supported.

> ### Example:  
> **Supported usage** 
> 
> ```
> // Using template literals without any expressions inside the extend call
> sap.ui.define([
>     "sap/ui/core/Control"
> ], (Control) => 
>     return Control.extend(`my.lib.MyControl`, {});
> );
> ```

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use template literals with one or more
> // expressions inside the extend call
> const sLibName = "my.lib";
> sap.ui.define([
>     "sap/ui/core/Control"
> ], (Control) => 
>     return Control.extend(`{sLibName}.MyControl`, {});
> );
> ```

***

<a name="loio0cb44d7a147640a0890cefa5fd7c7f8e__section_trk_cw5_hyb"/>

### Library Initialization

A UI5 library is typically initialized via an accompanying `library.js`. Within that file, the object which is supplied to the `sap/ui/core/Core#initLibrary` / `sap.ui.getCore().initLibrary` method must consider the following restrictions:

> ### Example:  
> **Supported usage** 
> 
> ```
> // Best practice to initialize a library in the library.js file
> sap.ui.define([
>     "sap/ui/core/Core"
> ], (Core) => {
>      const thisLib = Core.initLibrary(({
>          name: "my.lib",
>          version: "${version}",
>          designtime: "my/lib/designtime/library.designtime",
>          types: [
>              "my.lib.MyType"
>          ],
>          interfaces: [
>              "my.lib.MyInterface"
>          ],
>          controls: [
>              "my.lib.MyType"
>          ],
>          elements: [
>              "my.lib.MyElement"
>          ],
>          extensions: {}
>     });
> });
> ```

***

#### Expression as Parameter

Please do **not** use an expression for the library name when initializing a library.

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use an expression for the library name when initializing a library
> const libraryName = "lib";
> sap.ui.define([
>     "sap/ui/core/Core"
> ], (Core) => {
>     const thisLib = Core.initLibrary({
>          name: "my." + libraryName
>     });
> });
> ```

***

#### Variable Usage as Parameter

Please do **not** use a variable for the library name when initializing a library.

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use a variable for the library name when initializing a library
> const key = "name";
> sap.ui.define([
>     "sap/ui/core/Core"
> ], (Core) => {
>     const thisLib = Core.initLibrary({
>         [key]: "my.lib"
>     });
> });
> ```

***

#### Spread Element as Parameter

Please do **not** use a spread element for the library name when initializing a library.

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use a spread element for the library name when initializing a library
> const mylib = {
>     name: "my.lib"
> };
> sap.ui.define([
>     "sap/ui/core/Core"
> ], (Core) => {
>      const thisLib = Core.initLibrary({
>          ...mylib
>      });
> });
> ```

***

#### Template Literal as Parameter

Please do **not** use a template literal with one or more expressions for the library name when initializing a library.

> ### Example:  
> **Not supported** 
> 
> ```
> // Please do NOT use a template literal with one or more expressions for the library name when initializing a library
> const libraryName = "lib";
> sap.ui.define([
>     "sap/ui/core/Core"
> ], (Core) => {
>     const thisLib = Core.initLibrary({
>          name: `my.{libraryName}`
>     });
> });
> ```

-   **[Details on ECMAScript Support in OpenUI5](Details_on_ECMAScript_Support_in_OpenUI5_d6c0a5d.md " With OpenUI5 version 1.117, UI5 supports the usage of ECMAScript 2022
		language features and syntax, allowing you to make your code more modern and readable. There are a few restrictions imposed by UI5 which have
		to be considered, however.")**  
 With OpenUI5 version 1.117, UI5 supports the usage of ECMAScript 2022 language features and syntax, allowing you to make your code more modern and readable. There are a few restrictions imposed by UI5 which have to be considered, however.

