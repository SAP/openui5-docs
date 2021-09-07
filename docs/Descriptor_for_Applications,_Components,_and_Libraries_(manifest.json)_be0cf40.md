<!-- loiobe0cf40f61184b358b5faedaec98b2da -->

| loio |
| -----|
| be0cf40f61184b358b5faedaec98b2da |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/be0cf40f61184b358b5faedaec98b2da) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/be0cf40f61184b358b5faedaec98b2da)</div>

## Descriptor for Applications, Components, and Libraries \(manifest.json\)

The descriptor for applications, components, and libraries \(in short: app descriptor\) is inspired by the WebApplication Manifest concept introduced by the W3C. The descriptor provides a central, machine-readable, and easy-to-access location for storing metadata associated with an application, an application component, or a library.

In general, the app descriptor describes the behavior of an app through attributes. It doesn't directly influence that behavior itself for the most part. When a section in the app descriptor does affect the behavior of an app, this is described in the [API Reference](https://openui5.hana.ondemand.com/#/api/). for the corresponding namespace.

The data of the app descriptor is stored in JSON format in the `manifest.json` file. The developer creates the file with attributes in different namespaces. It contains, for example, the app ID, the version, the data sources used, along with the required components and libraries. The existence of the `manifest.json` file must be declared in the component metadata, which is then delivered as part of the application archive. After delivery, the file is read-only.

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_mkz_dgh_1cb"/>

### General Information

Every new version of OpenUI5 implies a new version of the app descriptor. In the following table, you can see how the OpenUI5 version is related to the descriptor version and the value of `_version.`

<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_lqj_xgh_1cb"/>App Descriptor Release and OpenUI5 Version


<table>
<tr>
<th>

App Descriptor Release



</th>
<th>

 OpenUI5 Version



</th>
<th>

\_version



</th>
</tr>
<tr>
<td>

Version 2



</td>
<td>

\>=1.30



</td>
<td>

1.1.0



</td>
</tr>
<tr>
<td>

Version 3



</td>
<td>

\>=1.32



</td>
<td>

1.2.0



</td>
</tr>
<tr>
<td>

Version 4



</td>
<td>

\>=1.34



</td>
<td>

1.3.0



</td>
</tr>
<tr>
<td>

Version 5



</td>
<td>

\>=1.38



</td>
<td>

1.4.0



</td>
</tr>
<tr>
<td>

Version 6



</td>
<td>

\>=1.42



</td>
<td>

1.5.0



</td>
</tr>
<tr>
<td>

Version 7



</td>
<td>

\>=1.46



</td>
<td>

1.6.0



</td>
</tr>
<tr>
<td>

Version 8



</td>
<td>

\>=1.48



</td>
<td>

1.7.0



</td>
</tr>
<tr>
<td>

Version 9



</td>
<td>

\>=1.50



</td>
<td>

1.8.0



</td>
</tr>
<tr>
<td>

Version 10



</td>
<td>

\>=1.52



</td>
<td>

1.9.0



</td>
</tr>
<tr>
<td>

Version 11



</td>
<td>

\>=1.54



</td>
<td>

1.10.0



</td>
</tr>
<tr>
<td>

Version 12



</td>
<td>

\>=1.56



</td>
<td>

1.11.0



</td>
</tr>
<tr>
<td>

Version 13



</td>
<td>

\>=1.58



</td>
<td>

1.12.0



</td>
</tr>
<tr>
<td>

Version 14



</td>
<td>

\>=1.61



</td>
<td>

1.13.0



</td>
</tr>
<tr>
<td>

Version 15



</td>
<td>

\>=1.62



</td>
<td>

1.14.0



</td>
</tr>
<tr>
<td>

Version 16



</td>
<td>

\>=1.66



</td>
<td>

1.15.0



</td>
</tr>
<tr>
<td>

Version 17



</td>
<td>

\>=1.70



</td>
<td>

1.16.0



</td>
</tr>
<tr>
<td>

Version 18



</td>
<td>

\>=1.71



</td>
<td>

1.17.0



</td>
</tr>
<tr>
<td>

Version 19



</td>
<td>

\>=1.74



</td>
<td>

1.18.0



</td>
</tr>
<tr>
<td>

Version 20



</td>
<td>

\>=1.75



</td>
<td>

1.19.0



</td>
</tr>
<tr>
<td>

Version 21



</td>
<td>

\>=1.76



</td>
<td>

1.20.0



</td>
</tr>
<tr>
<td>

Version 22



</td>
<td>

\>=1.77



</td>
<td>

1.21.0



</td>
</tr>
<tr>
<td>

Version 23



</td>
<td>

\>=1.78



</td>
<td>

1.22.0



</td>
</tr>
<tr>
<td>

Version 24



</td>
<td>

\>=1.79



</td>
<td>

1.23.0



</td>
</tr>
<tr>
<td>

Version 25



</td>
<td>

\>=1.80



</td>
<td>

1.24.0



</td>
</tr>
<tr>
<td>

Version 26



</td>
<td>

\>=1.81



</td>
<td>

1.25.0



</td>
</tr>
<tr>
<td>

Version 27



</td>
<td>

\>=1.82



</td>
<td>

1.26.0



</td>
</tr>
<tr>
<td>

Version 28



</td>
<td>

\>=1.83 \(OpenUI5 1.83 was not released, see [2979657](https://launchpad.support.sap.com/#/notes/2979657)\)



</td>
<td>

1.27.0



</td>
</tr>
<tr>
<td>

Version 29



</td>
<td>

\>=1.84



</td>
<td>

1.28.0



</td>
</tr>
<tr>
<td>

Version 30



</td>
<td>

\>=1.85



</td>
<td>

1.29.0



</td>
</tr>
<tr>
<td>

Version 31



</td>
<td>

\>=1.86



</td>
<td>

1.30.0



</td>
</tr>
<tr>
<td>

Version 32



</td>
<td>

\>=1.87



</td>
<td>

1.31.0



</td>
</tr>
<tr>
<td>

Version 33



</td>
<td>

\>=1.88



</td>
<td>

1.32.0



</td>
</tr>
<tr>
<td>

Version 34



</td>
<td>

\>=1.90



</td>
<td>

1.33.0



</td>
</tr>
<tr>
<td>

Version 35



</td>
<td>

\>=1.92



</td>
<td>

1.34.0



</td>
</tr>
<tr>
<td>

Version 36



</td>
<td>

\>=1.93



</td>
<td>

1.35.0



</td>
</tr>
</table>

For more information on the new fields introduced in each version, check out [Migration Information for Upgrading the Descriptor File](Migration_Information_for_Upgrading_the_Descriptor_File_a110f76.md)

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__manifirst"/>

### Manifest First Function

The component factory function [`Component.create`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Component%23methods/sap.ui.core.Component.create), as introduced with 1.58, loads the `manifest.json` by default before the component instance is created. With this, you can preload the dependencies \(libraries and components\) and, thus, improve the performance for loading the component. The preload is also available for models, which can be flagged for preload during component loading.

The `manifest` option allows you to configure when and from where the descriptor is loaded:

-   Default, equivalent to setting `manifest` to `true`.

    ``` js
    // "Component" required from module "sap/ui/core/Component"
    // load manifest.json from default location and evaluate it before creating an instance of the component 
    Component.create({
      name: "sap.my.component",
    });
    ```

-   Specify an alternative URL as parameter for `manifest` for the component factory function:

    ``` js
    // "Component" required from module "sap/ui/core/Component"
    // load via manifest URL
    Component.create({
      name: "sap.my.component",
      manifest: "any/location/sap/my/component/manifest.json"
    });
    ```

-   There are two possible scenarios for setting the `manifest` flag to `false`:

    1.  The component defines `manifest: "json"` in its [Component Metadata](Component_Metadata_0187ea5.md).

        In this case, the descriptor is loaded and evaluated **after** the Component controller. All dependencies defined in the descriptor will then also be loaded. Afterwards, the Component is instantiated.

    2.  The component does not define `manifest: "json"` in its [Component Metadata](Component_Metadata_0187ea5.md).

        This is typically the case for older legacy Components without a descriptor. In this case, only the Component's class metadata is evaluated. No additional descriptor file will be loaded.

    ``` js
    // "Component" required from module "sap/ui/core/Component"
    // load component without loading a manifest first
    //  - Case 1: the manifest.json is loaded after the Component controller
    //  - Case 2: no manifest.json is loaded (legacy)
    Component.create({
      name: "sap.my.component",
      manifest: false
    });
    ```


> ### Note:  
> When you enable `manifest`, all legacy component metadata needs to be migrated into the descriptor for applications/components. Only those entries in the descriptor for components will be respected by the component and all other entries will be ignored.

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_rmc_3xj_mmb"/>

### Special `ui5://` URLs

Inside the app descriptor, you can use special URLs prefixed with `ui5://`. These URLs will be resolved automatically during component startup before any models are created.

The `ui5://` URLs have the following properties:

-   only absolute URLs are allowed, e.g. `ui5://my/path/to/sample`, but not `ui5:my/app/path`,
-   all URL prefixes to be used inside a `ui5://` URL must be registered on the UI5 loader beforehand \(see the example below\),
-   `sap.ui5/resourceRoots` can be part of a `ui5://` URL,
-   the component factory [`Component.create`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Component%23methods/sap.ui.core.Component.create) takes care of defining the resource roots before any `ui5://` URLs are resolved.

***

#### Example

One common use case is the resolution of local annotation files. By default the local annotation files are resolved relative to the manifest. When using a `ui5://` URL, you can enforce a different resolution, e.g. to a server-absolute URL.

In this sample, we make sure that the component location is registered as a path on the UI5 loader. Additionally, we assume that the host system is`http://localhost:8080` :

``` js
sap.ui.loader.config({
    paths: {
        "my/url/prefix": "this/url/is/reachable"
    }
})
```

The following snippet shows a sample annotation file configuration in the `sap.app/dataSources` section of the app descriptor:

``` json
{
    ...
    "sap.app": {
         "dataSources": {
             "OData": {
                "uri": "/path/to/odata/service",
                "type": "OData",
                "settings": {
                    "odataVersion": "2.0",
                    "annotations": ["annotations"]
                    ...
                }
            },
            ...
            "annotations": {
                "uri": "ui5://my/url/prefix/annotations.xml",
                "type": "ODataAnnotation"
            }
            ...
         }
    }
    ...
}
```

During startup of the respective component the resolution of the `ui5://` URL for the sample annotation will look like this:

``` html
ui5://my/url/prefix/annotations.xml
```

is resolved to:

``` html
http://localhost:8080/this/url/is/reachable/annotations.xml
```

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_mhs_vdp_znb"/>

### Descriptor Content

> ### Note:  
> You can find an example `manifest.json` file with sample code for the descriptor content [here](Descriptor_for_Applications,_Components,_and_Libraries_(manifest.json)_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__section_example).

The content for the descriptor is contained in the following namespaces: `without`, `sap.app`, `sap.ui`, and `sap.ui5` . The following tables show the application-specific attributes provided by the respective namespaces:

[No Namespace](Descriptor_for_Applications,_Components,_and_Libraries_(manifest.json)_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__section_nonamespace)

[`sap.app`](Descriptor_for_Applications,_Components,_and_Libraries_(manifest.json)_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__section_sap_app)

[`sap.ui`](Descriptor_for_Applications,_Components,_and_Libraries_(manifest.json)_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__section_sap_ui)

[`sap.ui5`](Descriptor_for_Applications,_Components,_and_Libraries_(manifest.json)_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__section_sap_ui5)

[`sap.card`](Descriptor_for_Applications,_Components,_and_Libraries_(manifest.json)_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__section_sap_card)

[`_version`](Descriptor_for_Applications,_Components,_and_Libraries_(manifest.json)_be0cf40.md#loiobe0cf40f61184b358b5faedaec98b2da__section_version)

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_nonamespace"/>

### No Namespace

<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_crz_g5r_tr"/>Attributes in the `without` namespace


<table>
<tr>
<th>

Attribute



</th>
<th>

Description



</th>
</tr>
<tr>
<td>

 `start_url` 



</td>
<td>

Start page of your app, if available



</td>
</tr>
</table>

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_sap_app"/>

### `sap.app`

<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_rvq_4fj_qr"/>Attributes in the mandatory `sap.app` namespace


<table>
<tr>
<th>

Attribute



</th>
<th>

Description



</th>
</tr>
<tr>
<td>

 `id` 



</td>
<td>

A mandatory attribute that has to be provided in dot notation and specifies an ID for the project that must be unique in the system. It must match the namespace provided in the corresponding `Component.js`.

If, for example, a module is instantiated there as follows:

``` js
   return UIComponent.extend("sap.ui.demo.walkthrough.Component", {

      metadata : {
         manifest: "json"
      },
   ...

```

then its `id` would be `sap.ui.demo.walkthrough`

It's used as a reference point for most operations involving the app descriptor. If the project is the app variant of an existing application, `sap.app/id` is the ID of this app variant. The ID of the underlying application is then provided in `sap.ui5/componentName`.

> ### Note:  
> The ID must not exceed 70 characters. It must be unique.
> 
> In case of `sap.app/type=application`, the `sap.app/id` corresponds to the `id` of the UI5 component.



</td>
</tr>
<tr>
<td>

 `type` 



</td>
<td>

Possible values:

-   `application`: use if your `manifest.json` describes a **UI5 application**. For an example how to use a `manifest.json` for UI5 applications, see [Step 10: Descriptor for Applications](Step_10_Descriptor_for_Applications_8f93bf2.md)

-   `component`: use if your `manifest.json` describes a **reuse component** that is used in several apps. For further reuse component-specific configuration options, see [Descriptor for Components \(Inside Libraries\)](Descriptor_for_Components_(Inside_Libraries)_7701636.md).

-   `library`: use if your `manifest.json` describes a **UI5 library**. For further library-specific configuration options, see [Descriptor for Libraries](Descriptor_for_Libraries_b229914.md).

-   `card`: use if your `manifest.json` describes a **UI5 card**.For further card-specific configuration options, see [Integration Cards](https://openui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/overview/introduction).




</td>
</tr>
<tr>
<td>

 `i18n` 



</td>
<td>

The i18n property is an **optional** attribute and contains one of the following:

-   A URL string to the properties file that contains the text symbols for the descriptor; the URL is interpreted relative to the `manifest`.

     

-   An object that has been defined as described in [Terminologies](Terminologies_eba8d25.md).

If the manifest contains placeholders in `{{...}}` syntax, but no `i18n` attribute has been provided, the default value `i18n/i18n.properties` is used to request a ResourceBundle.



</td>
</tr>
<tr>
<td>

 `applicationVersion` 



</td>
<td>

Mandatory version of the app \(semantic version with the following format **`major.minor.patch`**\)



</td>
</tr>
<tr>
<td>

 `embeds` 



</td>
<td>

Array of relative paths to the nested `manifest.json` files; attribute is mandatory if a nested `manifest.json` exists



</td>
</tr>
<tr>
<td>

 `embeddedBy` 



</td>
<td>

Relative path back to the `manifest.json` file of an embedding component or library; attribute is mandatory for a nested `manifest.json` 



</td>
</tr>
<tr>
<td>

 `title` 



</td>
<td>

Mandatory attribute; to make this property language dependent \(recommended\), use a key in double curly brackets: `{{key}}` 



</td>
</tr>
<tr>
<td>

 `subTitle` 



</td>
<td>

Subtitle; to make this property language dependent \(recommended\), use a key in double curly brackets: `{{key}}` 



</td>
</tr>
<tr>
<td>

 `shortTitle` 



</td>
<td>

Short version of the title; to make this property language dependent \(recommended\), use a key in double curly brackets: `{{key}}` 



</td>
</tr>
<tr>
<td>

 `info` 



</td>
<td>

Needed for CDM \(Common Data Model\) conversion of tiles; to make this property language dependent \(recommended\), use a key in double curly brackets: `{{key}}` 



</td>
</tr>
<tr>
<td>

 `description` 



</td>
<td>

Description; to make this property language dependent \(recommended\), use a key in double curly brackets: `{{key}}` 



</td>
</tr>
<tr>
<td>

 `tags` 



</td>
<td>

Contains the following:

-   An array of **`keywords`**; either text or a language-dependent entry to be specified via `{{…}}` syntax, for example `"keywords": ["{{keyWord1}}","{{keyWord2}}"]`.

-   An array of **`technicalAttributes`** \(general technical attributes, for example, technical catalog, upper case and language-independent attributes\).




</td>
</tr>
<tr>
<td>

 `dataSources` 



</td>
<td>

Unique key/alias for specifying the used data sources; contains the following information:

-   `uri`: Mandatory relative URL in the component; takes `embeddedBy` into account, if filled, or the server absolute of the data source, for example `"/sap/opu/odata/snce/PO_S_SRV;v=2/"`. `uri` should always be given in lower case.
-   `type`: Supported types:
    -   `OData` \(default\)
    -   `ODataAnnotation`
    -   `INA`
    -   `XML`
    -   `JSON`
    -   `FHIR`
    -   `http`
    -   `WebSocket`
-   `customType` \(As of 1.77\): `true`/`false`; if `true`, there is no validation on the `type` attribute
-   `settings`: Data source type-specific attributes \(key, value pairs\), which are:
    -   `odataVersion`: 2.0 \(default\), 4.0
    -   `localUri`: Relative URL to local metadata document or annotation URI
    -   `annotations`: Array of annotations which references an existing data source of type `ODataAnnotation` under `sap.app/dataSources`

    -   `maxAge`: Indicates the number of seconds the client is willing to accept with regard to the age of the data that is requested

    -   `objects`: Dictionary of \(catalog\) objects offered by the INA datasource \(as of 1.92\) consisting of:
        -   `objectName`: Mandatory CDS view name / analytical query name
        -   `objectType` - mandatory type of object \(`2C<DDICNAME>` or `CDSViewName`\); values: `query`, `cdsprojectionview`, `view`, `inamodel`
        -   `packageName`: Name of the package
        -   `schemaName`: Name of the schema



</td>
</tr>
<tr>
<td>

 `cdsViews` 



</td>
<td>

Array of directly used CDS views

This attribute is optional and only added if used via INA protocol directly, not if used via OData service.



</td>
</tr>
<tr>
<td>

 `offline` 



</td>
<td>

Indicates whether the app is running offline; default is `false` \(online\)



</td>
</tr>
<tr>
<td>

 `sourceTemplate` 



</td>
<td>

If an app has been generated from a template, this attribute is filled automatically by the generation tool \(SAP Web IDE\):

-   `id`: Mandatory ID of the template from which the app was generated

-   `version`: Mandatory version of the template from which the app was generated




</td>
</tr>
<tr>
<td>

 `openSourceComponents` 



</td>
<td>

Array of directly used open source libraries for documentation purposes; not used when open source libraries are used via OpenUI5 capsulation

-   `name`: Mandatory name of the open source component

-   `version`: Required if the open source component is part of the app; not required if the open source component is part of the OpenUI5 dist layer

-   `packagedWithMySelf`: Indicates if the open source component is part of the app \(`true`\) or not \(`false`\)




</td>
</tr>
<tr>
<td>

 `resources` 



</td>
<td>

Relative URL as a reference to a file \(naming convention is `resources.json`\) that contains a list of all resources needed by the app \(all resources inside the app\); the file is generated in an SAP Web IDE build step.

For a description of `resources.json`, see [The resources.json File](The_resources.json_File_adcbcf8.md).



</td>
</tr>
</table>

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_sap_ui"/>

### `sap.ui`

<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_qw2_yhj_qr"/>Attributes in the mandatory `sap.ui` namespace


<table>
<tr>
<th>

Attribute



</th>
<th>

Description



</th>
</tr>
<tr>
<td>

 `technology` 



</td>
<td>

Specifies the UI technology; value is `UI5` 



</td>
</tr>
<tr>
<td>

 `icons` 



</td>
<td>

Contains object with app-specific icons, which are:

-   `icon`: Icon of the app, can be chosen from [Icon Explorer](https://openui5.hana.ondemand.com/test-resources/sap/m/demokit/iconExplorer/webapp/index.html) .
-   `favIcon`: ICO file to be used inside the browser and for desktop shortcuts

    > ### Note:  
    > `favIcon` is not set automatically by the framework. The icons can be set manually using the `sap/ui/util/Mobile` module and the `setIcons` function.

-   `phone`: 57x57 pixel version for non-retina iPhones
-   `phone@2`: 114x114 pixel version for retina iPhones
-   `tablet`: 72x72 pixel version for non-retina iPads
-   `tablet@2`: 144x144 pixel version for retina iPads



</td>
</tr>
<tr>
<td>

 `deviceTypes` 



</td>
<td>

Mandatory; contains objects with device types on which the app is running, such as:

-   `desktop`: Indicator for whether desktop devices are supported, `true` \(default\), `false`
-   `tablet`: Indicator for whether tablet devices are supported, `true` \(default\),`false`
-   `phone`: Indicator for whether phone devices are supported, `true` \(default\),`false`



</td>
</tr>
<tr>
<td>

 `fullWidth` 



</td>
<td>

Indicates whether an app shall run in full screen mode \(`true`\), or not \(`false`\)



</td>
</tr>
</table>

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_sap_ui5"/>

### `sap.ui5`

The `sap.ui5` namespace is aligned with the former concept of component metadata and contributes the following OpenUI5-specific attributes for the application descriptor, see [Migrating from Component Metadata to Descriptor](Migrating_from_Component_Metadata_to_Descriptor_e282db2.md) for more details.

<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_c32_chk_qr"/>Attributes in the `sap.ui5` namespace


<table>
<tr>
<th>

Attribute



</th>
<th>

Description



</th>
</tr>
<tr>
<td>

 `resources` 



</td>
<td>

Specifies additional `css` and `js` resources of the Component.

CSS files are added to the head of the HTML page as a link tag. JavaScript files are loaded by the `require` mechanism.

Two settings can be defined per resource:

-   `uri` \(mandatory\): URLs are resolved relative to the Component, taking the `embeddedBy` setting into account \(if filled\).

-   `id` \(optional\): Only for `css` resources; the id for a CSS file's `<link>` element.


> ### Note:  
> The usage of `js` resources is deprecated. Please use regular `dependencies` instead.



</td>
</tr>
<tr>
<td>

 `dependencies` 



</td>
<td>

Mandatory; specifies the external dependencies that are loaded by the OpenUI5 core during the initialization phase of the component and used afterwards. These are the following libraries or components:

-   `minUI5Version`: Mandatory; Minimum version of OpenUI5 that your component requires; this information ensures that the features of the OpenUI5 runtime version of the component are available. As OpenUI5 does not currently enforce use of the correct version, the `minUI5Version` is used for information purposes only. If the minimum OpenUI5 version criteria is not fulfilled, a warning is issued in the console log.

-   `libs`: ID \(namespace\) of the libraries that the OpenUI5 core should load for use in the component. If your app requires a minimum version of the lib, specify the `minVersion` for information purposes. Specify `lazy` to indicate that the lib shall be lazy loaded.

-   `components`: ID \(namespace\) of the components that the OpenUI5 core should load for use in your component. If your app requires a minimum version of the component, specify the `minVersion` for information purposes. Specify `lazy` to indicate that the component shall be lazy loaded.


For more information, see [Descriptor Dependencies to Libraries and Components](Descriptor_Dependencies_to_Libraries_and_Components_8521ad1.md).



</td>
</tr>
<tr>
<td>

 `componentUsages` 



</td>
<td>

Specifies the used components with the a unique key/alias. Contains the following:

-   `name`: Mandatory name of the reuse component

-   `settings`: Settings of the component

-   `componentData`: Component data of the component

-   `lazy`: Indicates whether the component usage should be lazily loaded. Default value: `true`


For more information see:[Using and Nesting Components](Using_and_Nesting_Components_346599f.md)



</td>
</tr>
<tr>
<td>

 `models` 



</td>
<td>

Defines models that should be created or destroyed along the component's lifecycle. The key represents the model name. Use an empty string \(""\) for the default model.

-   `type`: Model class name
-   `uri`: Relative URL in the component, taking `embeddedBy` into account if filled, or server for absolute model
-   `settings`: Object that is passed to the model constructor.

    > ### Example:  
    > You can overwrite the default binding mode with the `defaultBindingMode` attribute \(enumeration of type `sap.ui.model.BindingMode`, with values. `Default`, `OneTime`, `OneWay`, `TwoWay`\). For OData models constructor see the following:
    > 
    > -   [sap.ui.model.odata.ODataModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.ODataModel/constructor)
    > 
    > -   [sap.ui.model.odata.v2.ODataModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v2.ODataModel/constructor)
    > 
    > -   [sap.ui.model.odata.v4.ODataModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/constructor)
    > 
    > For ResourceModel constructor see:
    > 
    > -   [sap.ui.model.resource.ResourceModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.resource.ResourceModel/constructor)
    > 
    > The attribute `enhanceWith` can be specified with `bundleUrl`, `bundleUrlRelativeTo` \(either `component` \(default\) or `manifest`\) or `bundleName` to provide a list of additional resource bundle configurations to enhance the `ResourceModel` with. Additional attributes can be found in [Terminologies](Terminologies_eba8d25.md).

-   `dataSource`: String of key or alias from `sap.app dataSources` to reference an existing data source; the `type`, `uri` and `settings` properties are set according to the data source's `type`, `uri` and `settings` \(if not already defined\). If the type under `sap.app dataSources` is `OData`, an OData Model V2 is created automatically. If you need an OData Model V1, specify the `type` as well.
-   `preload`: Optional; Boolean with `true`, `false` \(default\)

    Defines whether or not the model is initialized \(preloaded\) before the component instance is created and while loading the component preload and its dependencies.

    For more information, see [Manifest Model Preload](Manifest_Model_Preload_26ba6a5.md).




</td>
</tr>
<tr>
<td>

 `rootView` 



</td>
<td>

Specifies the root view that shall be opened; can be the view name as a string for XML views, or the view configuration object with `viewName` for the view name as a string \(see [sap.ui.core.mvc.View.create](https://openui5.hana.ondemand.com/#/api/sap.ui.core.mvc.View/methods/sap.ui.core.mvc.View.create)\) and `type` for the type \(enumeration of [sap.ui.core.mvc.ViewType](https://openui5.hana.ondemand.com/#/api/sap.ui.core.mvc.ViewType)\), **id**, **async**, and other properties of `sap.ui.core.mvc.view`.



</td>
</tr>
<tr>
<td>

 `autoPrefixId` 



</td>
<td>

true, false \(default\), Enables the auto prefixing for the UIComponent for IDs of ManagedObjects \(controls or elements\) which are created in the context of the `createContent` function, or any other invocation of the `Component.prototype.runAsOwner()` function \(for example a component’s router uses this method when creating new views\).

In former OpenUI5 releases this prefixing of the ID needed to be done with `oComponent.createId` by overwriting the method `getAutoPrefixId`. The same can now be achieved declaratively by setting `autoPrefixId` to true.



</td>
</tr>
<tr>
<td>

 `handleValidation` 



</td>
<td>

Possible values: `true` or `false` \(default\); used to enable or disable validation handling by the message manager for this component, see [Error, Warning, and Info Messages](Error,_Warning,_and_Info_Messages_62b1481.md) 



</td>
</tr>
<tr>
<td>

 `config` 



</td>
<td>

Static configuration; specify the name-value pairs that you need in your component.



</td>
</tr>
<tr>
<td>

 `routing` 



</td>
<td>

Provides configuration parameters for route and router, see [Routing and Navigation](Routing_and_Navigation_3d18f20.md) 



</td>
</tr>
<tr>
<td>

 `extends` 



</td>
<td>

Used to extend another component.

-   `component`: ID \(namespace\) of the component being extended

-   `minVersion`: Specifies the minimum version of the component being extended, for information purposes if your app requires a minimum version of the component

-   `extensions`: Component or view extensions, which enable you to replace and extend views and controllers and also to modify the views, see [Extending Apps](Extending_Apps_a264a9a.md)




</td>
</tr>
<tr>
<td>

 `contentDensities` 



</td>
<td>

Mandatory; contains an object with the content density modes that the app supports, see [Content Densities](Content_Densities_e54f729.md)

-   `compact`: Mandatory; indicates whether compact mode is supported \(`true`, `false`\)

-   `cozy`: Mandatory; indicates whether cozy mode is supported \(`true`, `false`\)




</td>
</tr>
<tr>
<td>

 `resourceRoots` 



</td>
<td>

Map of URL locations keyed by a resource name prefix; only relative paths inside the component are allowed and no ".." characters

This attribute is intended for actual sub-packages of the component only, meaning that it must not be used for the component namespace itself.

> ### Note:  
> When loading with *manifest first*\(by using the property `manifest`\), the `resourceRoots` are evaluated before the component controller is loaded. Otherwise, the defined resource roots will be registered after the component controller is loaded and do not affect the modules being declared as dependencies in the component controller.



</td>
</tr>
<tr>
<td>

 `componentName` 



</td>
<td>

An optional attribute that only has to be provided if your project is a variant of an existing application. In this case the `componentName` has to contain the `sap.app/id` of the existing application which is the basis of your variant.



</td>
</tr>
<tr>
<td>

 `i18n` 



</td>
<td>

Determines if the library contains an i18n resource or not. If using a string instead of a boolean value, an alternative name for the i18n resource can be defined.

> ### Note:  
> This attribute is beneficial if the name of the main resource bundle \(properties file\) used by your UI5 library differs from the default name `messagebundle.properties`



</td>
</tr>
<tr>
<td>

 `commands` 



</td>
<td>

Specifies provided commands with a unique key/alias. Contains:

-   `shortcut`: String that describes a key combination. When the user presses the key combination, the command is triggered.




</td>
</tr>
</table>

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_sap_card"/>

### `sap.card`

<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_fly_cmt_ngb"/>Attributes in the `sap.card` namespace


<table>
<tr>
<th>

Attribute



</th>
<th>

Description



</th>
</tr>
<tr>
<td>

 `type` 



</td>
<td>

Describes the card type; possible values are `list` and `analytical` 



</td>
</tr>
<tr>
<td>

 `header` 



</td>
<td>

Specifies the card’s header area



</td>
</tr>
<tr>
<td>

 `content` 



</td>
<td>

Specifies the type-dependent card content



</td>
</tr>
</table>

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_version"/>

### `_version`

-   On root level \(no namespace\): Describes the descriptor format version \(mandatory\). Needs to be updated when migrating to a new descriptor format version, see [Migrating from Component Metadata to Descriptor](Migrating_from_Component_Metadata_to_Descriptor_e282db2.md)

-   Inside namespace: Describes the namespace format version \(optional from version 1.38 on\)


***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_descriptor_schema"/>

### Descriptor Schema

The newest flattened JSON schema is available on the SAP Open Source GitHub at [https://github.com/sap/ui5-manifest/](https://github.com/sap/ui5-manifest/) under Apache-2.0 License. It can be used to enable schema validation, code completion, and documentation.

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_example"/>

### Example

Current version of the `manifest.json`

``` { .collapsible .expanded}

{
    "_version": "1.35.0",
 
    "start_url": "index.html",
 
    "sap.app": {
        "id": "sap.fiori.appName",
        "type": "application",
        "i18n": "",
        "applicationVersion": {
            "version": "1.2.2"
        },
        "embeds": ["mycomponent1", "subpath/mycomponent2"],
        "embeddedBy": "../../",
        "title": "{{title}}",
        "subTitle": "{{subtitle}}",
        "shortTitle": "{{shorttitle}}",
        "description": "{{description}}",
        "info": "{{info}}",
        "tags": {
            "keywords": ["{{keyWord1}}", "{{keyWord2}}"],
            "technicalAttributes": ["ATTRIBUTE1", "ATTRIBUTE2"]
        },
        "dataSources": {
            "equipment": {
                "uri": "/sap/opu/odata/snce/po_s_srv;v=2/",
                "type": "OData",
                "settings": {
                    "odataVersion": "2.0",
                    "annotations": ["equipmentanno"],
                    "localUri": "model/metadata.xml",
                    "maxAge": 360
                }
            },
            "equipmentanno": {
                "uri": "/sap/bc/bsp/sap/nscbn_anf_eam/bscbn_equipment_srv.anno.xml",
                "type": "ODataAnnotation",
                "settings": {
                    "localUri": "model/annotations.xml"
                }
            }
        },
        "cdsViews": [
            "VIEW1", "VIEW2"
        ],
        "resources": "resources.json",
        "offline": true,
        "sourceTemplate": {
            "id": "sap.ui.ui5-template-plugin.1worklist",
            "version": "1.0.0"
        },
        "destination": {
            "name": "SAP_ERP_FIN"
        },
        "openSourceComponents": [{
            "name": "D3.js",
            "packagedWithMySelf": false
        }],
        }
        }
    },
 
    "sap.ui": {
        "technology": "UI5",
        "icons": {
            "icon": "sap-icon://add-contact",
            "favIcon": "icon/F1373_Approve_Purchase_Orders.ico",
            "phone": "icon/launchicon/57_iPhone_Desktop_Launch.png",
            "phone@2": "icon/launchicon/114_iPhone-Retina_Web_Clip.png",
            "tablet": "icon/launchicon/72_iPad_Desktop_Launch.png",
            "tablet@2": "icon/launchicon/144_iPad_Retina_Web_Clip.png"
        },
        "deviceTypes": {
            "desktop": true,
            "tablet": true,
            "phone": false
        },
        "fullWidth": true
    },
 
    "sap.ui5": {
        "resources": {
            "js": [{
                "uri": "component.js"
            }],
            "css": [{
                "uri": "component.css",
                "id": "componentcss"
            }]
        },
        "dependencies": {
            "minUI5Version": "1.93.0",
            "libs": {
                "sap.m": {
                    "minVersion": "1.34.0"
                },
                "sap.ui.commons": {
                    "minVersion": "1.34.0",
                    "lazy": true
                }
            },
            "components": {
                "sap.ui.app.other": {
                    "minVersion": "1.1.0",
                    "lazy": true
                }
            }
        },
        "componentUsages": {
            "myusage": {
                "name": "my.used",
                "lazy": false,
                "settings": {},
                "componentData": {}
            }
        },
        "models": {
            "i18n": {
                "type": "sap.ui.model.resource.ResourceModel",
                "uri": "i18n/i18n.properties",
                "settings": {
                    "enhanceWith": [{
                        "bundleUrl": "i18n/i18n.properties",
                        "bundleUrlRelativeTo": "manifest"
                    }]
                }
            },
            "equipment": {
                "preload": true,
                "dataSource": "equipment",
                "settings": {}
            }
        },
        "rootView": {
            "viewName": "sap.ui.test.view.Main",
            "id" : "rootView",
            "async": true,
            "type": "XML"
        },
        "handleValidation": true,
        "config": {
 
        },
        "routing": {
 
        },
        "extends": {
            "component": "sap.fiori.otherApp",
            "minVersion": "0.8.15",
            "extensions": {}
        },
        "contentDensities": {
            "compact": true,
            "cozy": false
        },
        "resourceRoots": {
            ".myname": "./myname"
        },
        "componentName": "sap.fiori.appName",
        "library": {
            "i18n": true
        },
        "commands": {
            "Save": {
                "shortcut": "Ctrl+S"
            }
        }
	    },
 
 
    "sap.fe": {},
    "sap.card": {}
}
```

For the following namespaces, the indicated teams are responsible:

-   sap.fe - in SAP Fiori elements responsibility

-   sap.card - in SAPUI5 responsibility


***

### Declaration in Component Metadata

The component declares the existence of the application descriptor by specifying `manifest: "json"` in the component metadata. Setting this flag makes the component load the `manifest.json` file and read the relevant entries for OpenUI5. This metadata is used to define the dependencies that need to be loaded in order to start the component. The following code snippet shows how to add the manifest link:

``` js
sap.ui.define(['sap/ui/core/UIComponent'], function(UIComponent) {
	
	return UIComponent.extend("sap.samples.Component", {
		metadata  : { 
			manifest: "json"
		}
	});

});
```

***

### OpenUI5 API

At runtime, the `manifest.json` content can be accessed from the component via the component metadata:

``` js
// get the component class
sap.ui.require(['sap/samples/Component'], function(SampleComponent) {

	// getting complete manifest from component metadata
	SampleComponent.getMetadata().getManifest();
	//or getting a namespace
	SampleComponent.getMetadata().getManifestEntry("sap.app");
	
});
```

[sap.ui.core.UIComponent](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.UIComponent.html)

[Component Metadata](Component_Metadata_0187ea5.md "The component class provides specific metadata for components by extending the ManagedObject class. The UIComponent class provides additional metadata for the configuration of user interfaces or the navigation between views.")

