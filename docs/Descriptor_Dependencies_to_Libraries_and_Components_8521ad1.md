<!-- loio8521ad1955f340f9a6207d615c88d7fd -->

| loio |
| -----|
| 8521ad1955f340f9a6207d615c88d7fd |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/8521ad1955f340f9a6207d615c88d7fd) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/8521ad1955f340f9a6207d615c88d7fd)</div>

## Descriptor Dependencies to Libraries and Components

Description of the performance-relevant attributes that are available for the descriptor for applications, components and libraries

The performance-relevant attributes have been introduced with the version 3 of the descriptor for applications, components, and libraries.

***

### Dependencies to Libraries

The following dependencies to libraries can be implemented:

-   To benefit from the asynchronous library preload, add the mandatory libraries to `sap.ui5/dependencies/libs`.

-   To expose the necessary dependencies for offline packages for mobile devices, add optional libraries to `sap.ui5/dependencies/libs` and flag them as `lazy`.


For **applications and components**, modify the `manifest.json` as follows:

```
"sap.ui5": {
    ...
    "dependencies": {
      ...
      "libs": {
        "sap.m": {},
        "sap.suite.ui.commons": {
          "lazy": true
        }
      }
      ...
    },
    ...

```

For **libraries**, modify the `.library` file as shown in the follown code sample. This file is available because the `manifest.json` for libraries is generated based on this metadata.

```
<dependencies>
    <dependency>
       <libraryName>sap.m</libraryName>
    </dependency>
    <dependency>
       <libraryName>sap.suite.ui.commons</libraryName>
       <lazy>true</lazy>
    </dependency>
    ...
```

In a second step, modify the `library.js` file as follows:

```
sap.ui.getCore().initLibrary({
   ...
   dependencies : ["sap.ui.core","sap.m"], // lazy libs are not declared here
```

> Note:
> In all cases, the lazy libraries need to be loaded manually in the application or library via the `loadLibrary` API:
> 
> ```
> // lazy lib loaded synchronously (avoid if possible!)
> sap.ui.getCore().loadLibrary("sap.suite.ui.commons");
> 
> // lazy lib loaded asynchronously (the preferred way!)
> sap.ui.getCore().loadLibrary("sap.suite.ui.commons", { async: true }).then(...);
> ```
> 
> 

> Note:
> Execute the `loadLibrary` before any resource of the library is required to preload the complete library instead of loading each resource individually.
> 
> Always use the async API as this is the preferred and performant way. Only use the sync API as an exception if your coding relies on synchronous loading.
> 
> 

***

### Dependencies to Components

**Scenario 1:** UI library contains multiple components

In this scenario, the library is the leading container and **no** component preload is available. This means, that you maintain the library dependency as described above. This is true for all kinds of component dependencies, also for `sap.ui5/extends/component`. If the extended component originates in a library, do **not** use `sap.ui5.extends/component`, but only declare the library dependency. Otherwise, the component dependency causes a 404 request.

For loading lazy components inside a library, proceed with the library mechanisms as described above:

```
// lazy lib loaded synchronously (avoid if possible!)
sap.ui.getCore().loadLibrary("sap.suite.ui.commons");

// lazy lib loaded asynchronously (the preferred way!!!)
sap.ui.getCore().loadLibrary("sap.suite.ui.commons", { async: true }).then(...);
```

**Scenario 2:** Standalone component

In this scenario, you only maintain a dependency to the component. The component preload is available for this scenario:

-   To benefit from the asynchronous components preload, add the mandatory components to `sap.ui5/dependencies/components`

-   Add the **optional** components to `sap.ui5/dependencies/components` and flag them as `lazy`.


For applications and components, modify the `manifest.json` as follows:

```
"sap.ui5": {
    ...
    "dependencies": {
      ...
      "libs": {
        ...
      },
      "components": {
        "samples.components.sample": {},
        "samples.components.samplelazy": {
          "lazy": true
        }
        ...
      }
    },
    ...

```

For loading/instantiating the lazy standalone components, use the component factory functions:

```
// "Component" required from module "sap/ui/core/Component"

// Asynchronously loads a component class without instantiating it.
Component.load({
  name: "..."
}).then(function(ComponentClass) {
  ...
});

// Asynchronously creates a new component instance from the given configuration.
// If necessary the component class is loaded.
Component.create({
  name: "..."
}).then(function(oComponentInstance) {
  ...
});
```

**Related information**  


[loadLibrary](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Core/methods/loadLibrary.html)

[Component](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Component/overview.html)

