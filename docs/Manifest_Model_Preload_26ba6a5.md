<!-- loio26ba6a5c1e5c417f8b21cce1411dba2c -->

| loio |
| -----|
| 26ba6a5c1e5c417f8b21cce1411dba2c |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/26ba6a5c1e5c417f8b21cce1411dba2c) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/26ba6a5c1e5c417f8b21cce1411dba2c)</div>

## Manifest Model Preload

The `preload` flag enables a preload mode for a model, thus improving the startup performance of an app or component.

The `preload` flag is located in `manifest.json` under `sap.ui5/models`:

```
"sap.ui5": {
  ...
  "models": {
      "mymodel": {
          "preload": true,
          ...
```

The flag is not active by default, as there are some prerequisites:

-   `sap.ui.component` is set to `"async=true"` and `manifest` \(API parameter name of `sap.ui.component`\).

-   `Model` implementation class is loaded before `sap.ui.component` is called; otherwise the model will not be created.

-   As model events \(for example `attachMetadataLoaded`\) may be missed because they are fired before the component coding runs, we recommend using the `Promise` API \(e.g. `metadataLoaded`\) instead, depending on the model type.

-   Use the model preload flag for `sap.ui.model.resource.ResourceModel` if one of the following applies:

    -   There is no component preload.

    -   The corresponding resource files are not part of the component preload.


This means: The preload flag only makes sense for models which load their data from other locations than the component itself. Local JSON, XML or resource model does not make sense as it interferes with the component preload which will result in loading the model data twice and should be omitted. But for the V2 OData model, for example, using preload speeds up the performance as the OData metadata can already be loaded in parallel to the component preload.

Before enabling the preload for the V2 ODataModel, make sure that you listen properly to metadata loaded by using the `Promise` API instead of the `Event` API \(`metadataLoaded`\) since the preload could have loaded the metadata already before the application code is executed. The Promise will be executed even if the metadata loaded event has been raised already.

Listen properly to metadata loaded by using the Promise:

```
oModel.metadataLoaded().then(function() {  /* TODO: add the event handling here! */  });
```

