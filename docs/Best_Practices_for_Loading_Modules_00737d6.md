<!-- loio00737d6c1b864dc3ab72ef56611491c4 -->

| loio |
| -----|
| 00737d6c1b864dc3ab72ef56611491c4 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/00737d6c1b864dc3ab72ef56611491c4) | [demo kit latest release](https://sdk.openui5.org/topic/00737d6c1b864dc3ab72ef56611491c4)</div>

## Best Practices for Loading Modules

This section provides best practices for OpenUI5 module loading patterns.

These best practices are especially important when you switch from the synchronous variant of the OpenUI5 module loader to the asynchronous variant. Patterns that may have worked in synchronous module loading may lead to applications that can’t start in asynchronous module loading.

> ### Note:  
> Use the `async` configuration parameter to enable asynchronous module loading via the bootstrap. For more information, see [Standard Variant for Bootstrapping](Standard_Variant_for_Bootstrapping_91f1f45.md).

***

<a name="loio00737d6c1b864dc3ab72ef56611491c4__section_DefineModules"/>

### How to Define Modules

Every OpenUI5 module file must contain exactly one unnamed module definition on the top level: the `sap.ui.define` call. Also, to avoid side-effects, all module-related functions must be defined within the callback function.

**Example**: The following two modules are unnamed. They only contain one top-level `sap.ui.define` and can be addressed with the respective unique module name:

`myLib/MyModuleA.js`

```js
sap.ui.define(function(){
    ...
});
...
```

For troubleshooting information with regard to loading your module, see [Why is my Module Not Loading?](Troubleshooting_for_Loading_Modules_4363b3f.md#loio4363b3fe3561414ca1b030afc8cd30ce__section_moduleloading).

***

<a name="loio00737d6c1b864dc3ab72ef56611491c4__section_AddressModules"/>

### How to Address Modules

A module must always be addressed with the unique module name. The module name is case-sensitive.

`myLib/MyModuleB.js`

```js
sap.ui.define(["myLib/MyModuleA"], function(MyModuleA){  
    ...  
});
```

For troubleshooting information with regard to addressing modules, see [What is wrong with the way I am addressing the modules?](Troubleshooting_for_Loading_Modules_4363b3f.md#loio4363b3fe3561414ca1b030afc8cd30ce__section_moduleaddressing).

***

<a name="loio00737d6c1b864dc3ab72ef56611491c4__section_StructureProject"/>

### How to Structure a Project

The entry point of an OpenUI5 application is often a module that is used to instantiate a OpenUI5 component. This central module is considered as single node of a graph and all dependent modules as well as their dependencies are nodes that must be connected by directed edges: the graph must fulfill the requirements of a directed acyclic graph \(DAG\).

**Example**: All modules are evaluated in a clearly defined order. The evaluation starts with module D, then module C and module B, and ends with module A.

![](images/loioc8a64ac29d0d44598b89d224ff14e9f3_LowRes.png)

For troubleshooting information with regard to the project structure, see [How can I remove project structures with cyclic dependencies?](Troubleshooting_for_Loading_Modules_4363b3f.md#loio4363b3fe3561414ca1b030afc8cd30ce__section_cyclicdependencies).

-   **[Troubleshooting for Loading Modules](Troubleshooting_for_Loading_Modules_4363b3f.md "The following sections give examples that you must avoid because they cause problems
		when loading your module.")**  
The following sections give examples that you must avoid because they cause problems when loading your module.

