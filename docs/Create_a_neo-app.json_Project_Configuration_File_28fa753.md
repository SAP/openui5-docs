<!-- loio28fa7538c67e4280a0b7708de2951278 -->

| loio |
| -----|
| 28fa7538c67e4280a0b7708de2951278 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/28fa7538c67e4280a0b7708de2951278) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/28fa7538c67e4280a0b7708de2951278)</div>

## Create a neo-app.json Project Configuration File

The `neo-app.json` file contains all project settings for SAP Web IDE and is created in the root folder of your project. It is a JSON format file consisting of multiple configuration keys. The most important setting for you to configure is the path where the OpenUI5 runtime is located when starting the app.

***

You do this using the “routes” key and defining an array of resource objects. For running an OpenUI5 tutorial, you only need two entries - one that configures OpenUI5 to be available with the path `/resources`, and another one that configures the test resources needed for the SAP Fiori launchpad integration with the path `/test-resources`.

Create two configuration objects that contain a `path`, a `target`, and a `description` attribute with more configuration settings. The `path` and the `entryPath` values will point to the location on the server where the OpenUI5 resources will be stored.

SAP Web IDE reads these settings automatically when running the app. You can see the whole configuration file in the code block below. Optionally, you can add the key `welcomeFile` to configure the entry point to your app. In web applications, this is typically the `index.html` file.

> Note:
> Depending on which SAP Web IDE version you are using, you might have to configure the project to run against the "snapshot" version of OpenUI5, otherwise the application will be launched with the OpenUI5 release that is delivered with SAP Web IDE. This is usually the latest version that is released publicly to customers.
> 
> You can check which version of OpenUI5 is loaded by opening the OpenUI5 debugging tools with * CTRL SHIFT ALT P *. If the version is too old for certain features of the tutorial, you have to add the `version` attribute to the target configuration entry and set the value to `snapshot`.
> 
> 

***

### Procedure

1.  Select the *New File* icon and enter `neo-app.json` as the file name.
2.  Open the newly created file from the tree structure on the left side of the screen.
3.  Paste the following code in the `neo-app.json` and select *Save*:

    ```
    {
      "welcomeFile": "index.html",
      "routes": [
        {
          "path": "/resources",
          "target": {
            "type": "service",
            "name": "sapui5",
            "version": "snapshot",
            "entryPath": "/resources"
          },
          "description": "SAPUI5 Resources"
        },
        {
          "path": "/test-resources",
          "target": {
            "type": "service",
            "name": "sapui5",
            "entryPath": "/test-resources"
          },
          "description": "SAPUI5 Test Resources"
        }
      ]
    }
    ```


