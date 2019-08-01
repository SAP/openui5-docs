<!-- loio91f25c2d6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f25c2d6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f25c2d6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f25c2d6f4d1014b6dd926db0e91070)</div>

## File Names and Locations \(View and Controller\)

In OpenUI5, controllers and views are defined and instantiated via a name that equals an OpenUI5 module name within the define/require concept.

By default, all files have to be located in a subfolder of the `resources` folder of the Web application. If this location is not appropriate, deviations can be configured as described in the following example:

The following example assumes that your views and controllers are located on your local machine where the OpenUI5 runtime is loaded from another machine. When you instantiate a view or a controller, OpenUI5 runtime loads them in relation to the `resources` folder of the machine where OpenUI5 runtime was loaded. To inform OpenUI5 runtime that your views and controllers are located on your local machine, use the following code:

``` js
sap.ui.loader.config({
  paths: {
    "<moduleNamePrefix>": sUrl
  }
});
```

If your files are located at `http://<localhost:8080>/<myapp>/`, for example, you can use `sap.ui.loader.config` as follows:

``` js
sap.ui.loader.config({
  paths: {
    "my/app": "./myapp"
  }
});
```

All views and controllers with a name starting with `my.app`, for example `my.app.MyView`, will then be loaded from your local machine.

**Related information**  


[Folder Structure: Where to Put Your Files](Folder_Structure_Where_to_Put_Your_Files_003f755.md)

