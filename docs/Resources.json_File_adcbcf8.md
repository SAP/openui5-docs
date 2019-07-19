<!-- loioadcbcf8b50924556ab3f321fcd9353ea -->

| loio |
| -----|
| adcbcf8b50924556ab3f321fcd9353ea |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/adcbcf8b50924556ab3f321fcd9353ea) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/adcbcf8b50924556ab3f321fcd9353ea)</div>

## Resources.json File

The `Resources.json` file lists all resources in a component or library folder. It resides next to each `manifest.json` in the generated results.

The file is generated during build time and its main purpose is for mobile packaging, as `resources.json` mentions all files inside the application. If an app has a `resources.json` file, it is mentioned in the `manifest.json` under `sap.app/resources`.

> Note:
> This file is used by SAP Tools like the SAP Fiori Client Packager. It will be generated automatically when using SAP WebIDE.
> 
> 

The list of resources is stored in an array in the `resources` property of the top level JSON object. The top level object can also contain the `_version` property, which can be omitted if the value is `1.0.0`. For each resource, the following entries are possible:

|Property|Type|Description|
|--------|----|-----------|
| `name` | `string` |Relative path of the resource as accessible in a server; starts with the first name segment, for example `Component.js` \(mandatory\)|
| `isDebug` | `Boolean` |When set to `true`, the resource is a debug source, the OpenUI5 build derives the flag from the naming convention \(`-dbg(.controller .view .fragment).js`\) \(optional\)|
| `locale` | `string` |Locale of the resource for known i18n resources; the OpenUI5 build derives the locale from the naming convention \(`*_[locale].properties`\) \(optional\)|
| `raw` | `string` |Name of the corresponding resource in the raw \(developer\) language for known i18n resources; for `messagebundle.en.properties`, for example, the corresponding raw file is `messagebundle.properties` \(optional\)|
| `merged` | `boolean` |Indicates whether the resource is a merged resource \(optional\) By default, the OpenUI5 build determines this from naming conventions `(library-preload.json`, `library-all.js`, `Component-preload.js`\), but it also allows to add more merged files by manual configuration of the build step. SAP Web IDE may use other knowledge for this; it knows, for example, that it merges the `Component-preload.js`.|
| `theme` | `string` |Indicates a theme-dependant resource \(optional\) The OpenUI5 build determines this from the naming convention `**themes<theme>/ **` |

***

``` js

{
    "resources":[
        {
            "name": ".library"
        },
        {
            "name": ".theming"
        },
        {
            "name": "DynamicSideContent-dbg.js",
            "isDebug":true
        },
        {
            "name": "DynamicSideContent.js"
        },
        {
            "name": "DynamicSideContentRenderer-dbg.js",
            "isDebug":true
        },
 
        ...
 
        {
            "name": "library-preload.json",
            "merged":true
        },
 
        ...
 
        {
            "name": "messagebundle_de.properties",
            "raw":"messagebundle.properties",
            "locale":"de"
        },
 
        ...
 
        {
            "name": "themes/sap_belize/library.less",
            "theme":"sap_belize"
        }
 
        ...
 
    ]
}
```

