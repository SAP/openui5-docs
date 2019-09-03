<!-- loiobe0cf40f61184b358b5faedaec98b2da -->

| loio |
| -----|
| be0cf40f61184b358b5faedaec98b2da |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/be0cf40f61184b358b5faedaec98b2da) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/be0cf40f61184b358b5faedaec98b2da)</div>

## Descriptor for Applications, Components, and Libraries

The descriptor for applications, components, and libraries is inspired by the Web Application Manifest concept introduced by the W3C. The descriptor provides a central, machine-readable and easy-to-access location for storing metadata associated with an application, an application component, or a library.

The data is stored in json format in the `manifest.json` file. The developer creates the file with attributes in different namespaces. It contains, for example, the app ID, the version, the data sources used, along with the required components and libraries. The existence of the `manifest.json` file must be declared in the component metadata, which is then delivered as part of the application archive. After delivery, the file is read-only.

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__section_mkz_dgh_1cb"/>

### General Information

Every new version of OpenUI5 implies a new version of the app descriptor. In the following table you can see how the OpenUI5 version is related to the descriptor version and the value of `_version.`

AppDescriptor Release and OpenUI5 Version<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_lqj_xgh_1cb"/>

|AppDescriptor Release| OpenUI5 Version|\_version|
|---------------------|----------------|---------|
|Version 2|\>=1.30|1.1.0|
|Version 3|\>=1.32|1.2.0|
|Version 4|\>=1.34|1.3.0|
|Version 5|\>=1.38|1.4.0|
|Version 6|\>=1.42|1.5.0|
|Version 7|\>=1.46|1.6.0|
|Version 8|\>=1.48|1.7.0|
|Version 9|\>=1.50|1.8.0|
|Version 10|\>=1.52|1.9.0|
|Version 11|\>=1.54|1.10.0|
|Version 12|\>=1.56|1.11.0|
|Version 13|\>=1.58|1.12.0|
|Version 14|\>=1.61|1.13.0|
|Version 15|\>=1.62|1.14.0|
|Version 16|\>=1.66|1.15.0|

For more information on the new fields introduced in each version, check out [Migration Information for Upgrading the Descriptor File](Migration_Information_for_Upgrading_the_Descriptor_File_a110f76.md)

***

<a name="loiobe0cf40f61184b358b5faedaec98b2da__manifirst"/>

### Manifest First Function

The component factory function [`Component.create`](https://openui5.hana.ondemand.com/1.62.0/#/api/sap.ui.core.Component/methods/sap.ui.core.Component.create), as introduced with 1.58, loads the `manifest.json` by default before the component instance is created. With this, you can preload the dependencies \(libraries and components\) and, thus, improve the performance for loading the component. The preload is also available for models, which can be flagged for preload during component loading.

The `manifest` option allows to configure when and from where the descriptor is loaded:

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

-   Suppress loading the manifest by setting the `manifest` flag to `false`, for example, when a legacy component does not have one:

    ``` js
    // "Component" required from module "sap/ui/core/Component"
    // load component without loading a manifest first
    Component.create({
      name: "sap.my.component",
      manifest: false
    });
    ```


> Note:
> When you enable `manifest`, all legacy component metadata needs to be migrated into the descriptor for applications/components. Only those entries in the descriptor for components will be respected by the component and all other entries will be ignored.
> 
> 

***

### Descriptor Content

The content for the descriptor is contained in the following namespaces: `without`, `sap.app`, `sap.ui`, `sap.ui5`, `sap.platform.abap`, `sap.platform.hcp` and `sap.fiori`. The following tables show the application-specific attributes provided by the respective namespaces:

***

#### No Namespace

Attributes in the `without` namespace<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_crz_g5r_tr"/>

|Attribute|Description|
|---------|-----------|
| `start_url` |Start page of your app, if available|

***

#### `sap.app`

Attributes in the mandatory `sap.app` namespace <a name="loiobe0cf40f61184b358b5faedaec98b2da__table_rvq_4fj_qr"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Attribute</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> `id` </td>
			<td>Mandatory attribute: Unique identifier of the app, which must correspond to the component name

 > Note:
 > The ID must not exceed 70 characters. It must be unique and must correspond to the component name.
			</td>
		</tr>
		<tr>
			<td> `type` </td>
			<td>Possible values:

 -   `application`
 -   `component`

 -   `library`

 -   `card`
			</td>
		</tr>
		<tr>
			<td> `i18n` </td>
			<td>Relative URL to the properties file that contains the text symbols for the descriptor; default: `"i18n/i18n.properties"`

 > Note:
 > The path to the i18n file must not exceed 100 characters.
			</td>
		</tr>
		<tr>
			<td> `applicationVersion` </td>
			<td>Mandatory version of the app \(semantic version with the following format **`major.minor.patch`**\)</td>
		</tr>
		<tr>
			<td> `embeds` </td>
			<td>Array of relative paths to the nested `manifest.json` files; attribute is mandatory if a nested `manifest.json` exists</td>
		</tr>
		<tr>
			<td> `embeddedBy` </td>
			<td>Relative path back to the `manifest.json` file of an embedding component or library; attribute is mandatory for a nested `manifest.json` </td>
		</tr>
		<tr>
			<td> `title` </td>
			<td>Mandatory attribute: The entry is language-dependent and specified via `{{…}}` syntax</td>
		</tr>
		<tr>
			<td> `subTitle` </td>
			<td>Language-dependent entry for a subtitle; specified via `{{...}}` syntax</td>
		</tr>
		<tr>
			<td> `shortTitle` </td>
			<td>Short version of the title. Language-dependent entry has to be specified via `{{...}}` syntax</td>
		</tr>
		<tr>
			<td> `info` </td>
			<td>Needed for CDM \(Common Data Model\) conversion of tiles. Language-dependent entry has to be specified via `{{...}}` syntax</td>
		</tr>
		<tr>
			<td> `description` </td>
			<td>Description; language-dependent entry that is specified via `{{…}}` syntax</td>
		</tr>
		<tr>
			<td> `tags` </td>
			<td>Contains the following:

 -   An array of language-dependent **`keywords`** that are specified via `{{…}}` syntax, for example `"keywords": ["{{keyWord1}}","{{keyWord2}}"]`.
 -   An array of **`technicalAttributes`** \(general technical attributes, for example, technical catalog, upper case and language-independent attributes\).
			</td>
		</tr>
		<tr>
			<td> `ach` </td>
			<td>Application component hierarchy \(SAP's component names for bug reports\); attribute is mandatory for SAP apps, but is not used so far for apps developed outside SAP</td>
		</tr>
		<tr>
			<td> `dataSources` </td>
			<td> Unique key/alias for specifying the used data sources; contains the following information:
 -   `uri`: Mandatory relative URL in the component; takes `embeddedBy` into account, if filled, or the server absolute of the data source, for example `"/sap/opu/odata/snce/PO_S_SRV;v=2/"` 
 -   `type`: OData `(default)or ODataAnnotation or INA or XML or JSON`
 -   `settings`: Data source type-specific attributes \(key, value pairs\), which are:
     -   `odataVersion`: 2.0 \(default\), 4.0
     -   `localUri`: Relative URL to local metadata document or annotation uri
     -   `annotations`: Array of annotations which references an existing data source of type "ODataAnnotation" under **sap.app/dataSources**

     -   `maxAge`: Indicates the number of seconds the client is willing to accept with regard to the age of the data that is requested
			</td>
		</tr>
		<tr>
			<td> `cdsViews` </td>
			<td>Array of directly used CDS views This attribute is optional and only added if used via INA protocol directly, not if used via OData service.</td>
		</tr>
		<tr>
			<td> `offline` </td>
			<td>Indicates whether the app is running offline; default is `false` \(online\)</td>
		</tr>
		<tr>
			<td> `sourceTemplate` </td>
			<td>If an app has been generated from a template, this attribute is filled automatically by the generation tool \(SAP Web IDE\):

 -   `id`: Mandatory ID of the template from which the app was generated
 -   `version`: Mandatory version of the template from which the app was generated
			</td>
		</tr>
		<tr>
			<td> `openSourceComponents` </td>
			<td>Array of directly used open source libraries for documentation purposes; not used when open source libraries are used via SAPUI5 capsulation

 -   `name`: Mandatory name of the open source component
 -   `version`: Required if the open source component is part of the app; not required if the open source component is part of the SAPUI5 dist layer

 -   `packagedWithMySelf`: Indicates if the open source component is part of the app \(`true`\) or not \(`false`\)
			</td>
		</tr>
		<tr>
			<td> `provider` </td>
			<td>Name of the provider that owns the application. Current supported enum value is **sfsf**.</td>
		</tr>
		<tr>
			<td> `crossNavigation` </td>
			<td>Cross-navigation for specifying inbounds and outbounds

 -   `scopes`: Scope of a site
`sapSite`

 -   `inbounds`: Unique key or alias to specify inbounds \(mandatory\); contains:

     -   `semanticObject` \(mandatory\)

     -   `action` \(mandatory\)

     -   `icon`: Used to overwrite `sap.ui/icons/icon`

     -   `title`: Used to overwrite `sap.app/title` \(language-dependent entry to be specified via \{\{...\}\} syntax\)

     -   `subTitle`: Used to overwrite `sap.app/subTitle` \(language-dependent entry to be specified via \{\{...\}\} syntax\)

     -   `shortTitle`: Used to overwrite `sap.app/shortTitle` \(language-dependent entry to be specified via \{\{...\}\} syntax\)

     -   `info`: Language-dependent entry to be specified via \{\{...\}\} syntax

     -   `displayMode`: <`ContentMode` or `HeaderMode`\> Display mode for an inbound which specifies what kind of tile is displayed. A static tile can be displayed in content mode or header mode. The tile in header mode is a text only tile without an icon which allows longer title and subtitle.

     -   `hideLauncher` \(`true`/`false`\): Indicates that an inbound must not be represented as a tile/link

     -   `indicatorDataSource`; specifies the data source; contains:

         -   `dataSource`: reference to `sap.app/dataSources` \(mandatory\)

         -   `path`: Relative path to `sap.app/dataSources uri` \(mandatory\)

         -   `refresh`: Defines the refresh interval

     -   `deviceTypes`: Contains objects with device types on which the app is running; if empty, use the default from `sap.ui/deviceTypes`; the following device types can be defined \(`true`/`false`\):

         -   `desktop`

         -   `tablet`

         -   `phone`

     -   `signature`: Specifies the signature; contains:

         -   `parameters` \(mandatory\): Contains parameter names with the following information:

            -   `required` \(`true`/`false`\)

            -   `filter`: Represents the filter only if the input parameter matches the filter; with a mandatory `value` and `format` attribute \("plain", "regexp", "reference"\)

            -   `defaultValue`: Specifies the default value; has mandatory attributes `value` \(depending on the format this is a verbatim default value\) and `format` \("plain", "reference"\)

            -   `renameTo`: Used for parameter mapping to specify the parameter name in legacy ABAP applications, for example, `RF05L_BUKRS` for the `CompanyCode` parameter

            -   `launcherValue`: Represents a value to be used when creating an tile intent for this inbound with value and format \("plain", "array"\)

         -   `additionalParameters` \(mandatory\): Indicates, how additional parameters to the declared signature are handeled; values can be, for example, "ignored", "notallowed", "allowed"

 -   `outbounds`: Specifies outbounds with a unique key or alias containing:

     -   `semanticObject` \(mandatory\)

     -   `action` \(mandatory\)

     -   `parameters`: Specifies the parameter name

         -   `value`: Represents a value to be used in the outbound; with `value` \(verbatim value for format "plain", or not supplied, or a binding reference for format "binding"\) and `format` \(indicates how value is to be interpreted, "plain", "binding"\)

         -   `required`: Indicator whether paramter is required \(`true`, `false`\)

     -   `additionalParameters`: Indicates whether additional context parameters are to be used:

         -   `ignored`: Parameters are not used

         -   `allowed`: Parameters are passed on to application
			</td>
		</tr>
	</tbody>
</table>

***

#### `sap.ui`

Attributes in the mandatory `sap.ui` namespace <a name="loiobe0cf40f61184b358b5faedaec98b2da__table_qw2_yhj_qr"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Attribute</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> `technology` </td>
			<td>Specifies the UI technology; value is `UI5` </td>
		</tr>
		<tr>
			<td> `icons` </td>
			<td> Contains object with app-specific icons, which are:
 -   `icon`: Icon of the app, can be chosen from [Icon Explorer](https://openui5.hana.ondemand.com/test-resources/sap/m/demokit/iconExplorer/webapp/index.html) .
 -   `favIcon`: ICO file to be used inside the browser and for desktop shortcuts

 > Note:
 > `favIcon` is not set automatically by the framework. The icons can be set manually using the `sap/ui/util/Mobile` module and the `setIcons` function.

 -   `phone`: 57x57 pixel version for non-retina iPhones
 -   `phone@2`: 114x114 pixel version for retina iPhones
 -   `tablet`: 72x72 pixel version for non-retina iPads
 -   `tablet@2`: 144x144 pixel version for retina iPads
			</td>
		</tr>
		<tr>
			<td> `deviceTypes` </td>
			<td> Mandatory; contains objects with device types on which the app is running, such as:
 -   `desktop`: Indicator for whether desktop devices are supported, `true` \(default\), `false`
 -   `tablet`: Indicator for whether tablet devices are supported, `true` \(default\),`false`
 -   `phone`: Indicator for whether phone devices are supported, `true` \(default\),`false`
			</td>
		</tr>
		<tr>
			<td> `supportedThemes` </td>
			<td>Optional; array of supported SAP themes, such as `sap_hcb`, `sap_belize` </td>
		</tr>
		<tr>
			<td> `fullWidth` </td>
			<td>Indicates whether an app shall run in full screen mode \(`true`\), or not \(`false`\)</td>
		</tr>
	</tbody>
</table>

***

#### `sap.ui5`

The `sap.ui5` namespace is aligned with the previous component metadata and contributes the following OpenUI5-specific attributes for the application descriptor, see [Migrating from Component Metadata to Descriptor](Migrating_from_Component_Metadata_to_Descriptor_e282db2.md) for more details.

Attributes in the `sap.ui5` namespace <a name="loiobe0cf40f61184b358b5faedaec98b2da__table_c32_chk_qr"/>

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Attribute</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> `resources` </td>
			<td>Relative URLs in the component, taking `embeddedBy` into account if filled, pointing to `js` \(JavaScript\) and `css` resources that are needed by the app for specifying the mandatory `uri` and an `id` \(optional\) for CSS. The JavaScript files are loaded by the `require` mechanism. The CSS files are added to the head of the HTML page as a link tag. The resources are resolved relative to the location of the `manifest.json` file.</td>
		</tr>
		<tr>
			<td> `dependencies` </td>
			<td> Mandatory; specifies the external dependencies that are loaded by the OpenUI5 core during the initialization phase of the component and used afterwards. These are the following libraries or components:
 -   `minUI5Version`: Mandatory; Minimum version of OpenUI5 that your component requires; this information ensures that the features of the OpenUI5 runtime version of the component are available. As OpenUI5 does not currently enforce use of the correct version, the `minUI5Version` is used for information purposes only. If the minimum SAPUI5 version criteria is not fulfilled, a warning is issued in the console log.

 -   `libs`: ID \(namespace\) of the libraries that the OpenUI5 core should load for use in the component. If your app requires a minimum version of the lib, specify the `minVersion` for information purposes. Specify `lazy` to indicate that the lib shall be lazy loaded.

 -   `components`: ID \(namespace\) of the components that the OpenUI5 core should load for use in your component. If your app requires a minimum version of the component, specify the `minVersion` for information purposes. Specify `lazy` to indicate that the component shall be lazy loaded.


 For more information, see [Descriptor Dependencies to Libraries and Components](Descriptor_Dependencies_to_Libraries_and_Components_8521ad1.md).</td>
		</tr>
		<tr>
			<td> `componentUsages` </td>
			<td>Specifies the used components with the a unique key/alias. Contains the following:

 -   `name`: Mandatory name of the reuse component
 -   `settings`: Settings of the component

 -   `componentData`: Component data of the component

 -   `lazy`: Indicates whether the component usage should be lazily loaded. Default value: `true`


 For more information see:[Using and Nesting Components](Using_and_Nesting_Components_346599f.md) </td>
		</tr>
		<tr>
			<td> `models` </td>
			<td> Defines models that should be created or destroyed along the component's lifecycle. The key represents the model name. Use an empty string \(""\) for the default model.
 -   `type`: Model class name
 -   `uri`: Relative URL in the component, taking `embeddedBy` into account if filled, or server for absolute model
 -   `settings`: Object that is passed to the model constructor.

 > Note:
 > You can overwrite the default binding mode with the `defaultBindingMode` attribute \(enumeration of type `sap.ui.model.BindingMode`, with values. **Default**, **OneTime**, **OneWay**, **TwoWay**\). For OData models constructor see the following:
 > -   [sap.ui.model.odata.ODataModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.ODataModel/constructor)
 > -   [sap.ui.model.odata.v2.ODataModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v2.ODataModel/constructor)
 > -   [sap.ui.model.odata.v4.ODataModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.odata.v4.ODataModel/constructor)
 > For ResourceModel constructor see:
 > -   [sap.ui.model.resource.ResourceModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.resource.ResourceModel/constructor)
 > The attribute `enhanceWith` can be specified with **bundleUrl**, **bundleUrlRelativeTo** \(default: `component` or `manifest`\) or **bundleName** to provide a list of additional resource bundle configurations to enhance the `ResourceModel` with.

 -   `dataSource`: String of key or alias from `sap.app dataSources` to reference an existing data source; the `type`, `uri` and `settings` properties are set according to the data source's `type`, `uri` and `settings` \(if not already defined\). If the type under `sap.app dataSources` is `OData`, an OData Model V2 is created automatically. If you need an OData Model V1, specify the `type` as well.
 -   `preload`: Optional; Boolean with `true`, `false` \(default\)

Defines whether or not the model is initialized \(preloaded\) before the component instance is created and while loading the component preload and its dependencies.

For more information, see [Manifest Model Preload](Manifest_Model_Preload_26ba6a5.md).
			</td>
		</tr>
		<tr>
			<td> `rootView` </td>
			<td>Specifies the root view that shall be opened; can be the view name as a string for XML views, or the view configuration object with `viewName` for the view name as a string and `type` for the type \(enumeration of [sap.ui.core.mvc.ViewType](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.mvc.ViewType.html)\), **id**, **async** and other properties of `sap.ui.core.mvc.view`.</td>
		</tr>
		<tr>
			<td> `autoPrefixId` </td>
			<td>true, false \(default\), Enables the auto prefixing for the UIComponent for IDs of ManagedObjects \(controls or elements\) which are created in the context of the `createContent` function, or any other invocation of the `Component.prototype.runAsOwner()` function \(for example a component’s router uses this method when creating new views\). In former OpenUI5 releases this prefixing of the ID needed to be done with `oComponent.createId` by overwriting the method `getAutoPrefixId`. The same can now be achieved declaratively by setting `autoPrefixId` to true.</td>
		</tr>
		<tr>
			<td> `handleValidation` </td>
			<td>Possible values: `true` or `false` \(default\); used to enable or disable validation handling by the message manager for this component, see [Error, Warning, and Info Messages](Error,_Warning,_and_Info_Messages_62b1481.md) </td>
		</tr>
		<tr>
			<td> `config` </td>
			<td>Static configuration; specify the name-value pairs that you need in your component.</td>
		</tr>
		<tr>
			<td> `routing` </td>
			<td>Provides configuration parameters for route and router, see [Routing and Navigation](Routing_and_Navigation_3d18f20.md) </td>
		</tr>
		<tr>
			<td> `extends` </td>
			<td>Used to extend another component.

 -   `component`: ID \(namespace\) of the component being extended
 -   `minVersion`: Specifies the minimum version of the component being extended, for information purposes if your app requires a minimum version of the component

 -   `extensions`: Component or view extensions, which enable you to replace and extend views and controllers and also to modify the views, see [Extending Apps](Extending_Apps_a264a9a.md)
			</td>
		</tr>
		<tr>
			<td> `contentDensities` </td>
			<td>Mandatory; contains an object with the content density modes that the app supports, see [Content Densities](Content_Densities_e54f729.md)

 -   `compact`: Mandatory; indicates whether compact mode is supported \(`true`, `false`\)
 -   `cozy`: Mandatory; indicates whether cozy mode is supported \(`true`, `false`\)
			</td>
		</tr>
		<tr>
			<td> `resourceRoots` </td>
			<td>Map of URL locations keyed by a resource name prefix; only relative paths inside the component are allowed and no ".." characters This attribute is intended for actual sub-packages of the component only, meaning that it must not be used for the component namespace itself.

 > Note:
 > When loading with *manifest first*\(by using the property `manifest`\), the `resourceRoots` are evaluated before the component controller is loaded. Otherwise, the defined resource roots will be registered after the component controller is loaded and do not affect the modules being declared as dependencies in the component controller.
			</td>
		</tr>
		<tr>
			<td> `componentName` </td>
			<td>Name of the OpenUI5 component</td>
		</tr>
		<tr>
			<td> `appVariantIdHierarchy` </td>
			<td>Needed for an app variant scenario to reference UI flex changes from layers below. An array of `appVariantId` hierarchy with origin layer and version, calculated attribute and filled automatically during variant merge.</td>
		</tr>
		<tr>
			<td> `i18n` </td>
			<td> Determines if the library contains a i18n resource or not. If using a string instead of a boolean value, an alternative name for the i18n resource could be defined.
 > Note:
 > If your SAP Fiori library benefits from the new attribute `sap.ui5/library/i18n`, adoption is recommended. This is only the case if the main resource bundle \(properties file\) used by the SAP Fiori Library is different than the default name **messagebundle.properties**
			</td>
		</tr>
		<tr>
			<td> `flexEnabled` </td>
			<td>Determines whether the app is enabled for adaptation flex enabled \(for example, using stable IDs\); possible values are `true`, `false` or `undefined` \(default\)</td>
		</tr>
		<tr>
			<td> `commands` </td>
			<td>Specifies provided commands with a unique key/alias. Contains:

 -   `shortcut`: String that describes a key combination. When the user presses the key combination, the command is triggered.
			</td>
		</tr>
	</tbody>
</table>

***

#### `sap.platform.abap`

Attributes in the `sap.platform.abap` namespace<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_tdx_sdt_tr"/>

|Attribute|Description|
|---------|-----------|
| `uri` |Specifies the app's URI in the ABAP system, for example `/sap/bc/ui5_ui5/sap/appName`; filled during deployment.|

***

#### `sap.platform.hcp`

Attributes in the `sap.platform.hcp` namespace<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_h5d_c2t_tr"/>

|Attribute|Description|
|---------|-----------|
| `uri` |Specifies the URI inside the SAP Cloud Platform HTML5 application; filled during deployment, default is ""|
| `providerAccount` |Specifies the name of the provider account; filled during deployment|
| `appName` |Specifies the name of the deployed HTML5 application; filled during deployment|
| `appVersion` |Specifies the version of the deployed HTML5 application; filled during deployment|

***

#### `sap.fiori`

Attributes in the `sap.fiori` namespace<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_h31_l2t_tr"/>

|Attribute|Description|
|---------|-----------|
| `registrationIds` |Array of registration IDs, for example, the Fiori IDs for Fiori apps|
| `archeType` |Mandatory arche type of the app, possible values `transactional`, `analytical`, `factsheet`, `reusecomponent`, `fpmwebdynpro`, `designstudio` |

***

#### `sap.card`

Attributes in the `sap.card` namespace<a name="loiobe0cf40f61184b358b5faedaec98b2da__table_fly_cmt_ngb"/>

|Attribute|Description|
|---------|-----------|
| `type` |Describes the card type; possible values are `list` and `analytical` |
| `header` |Specifies the card’s header area|
| `content` |Specifies the type-dependent card content|

***

#### `_version`

-   On root level \(no namespace\) Describes the descriptor format version \(mandatory\). Needs to be updated when migrating to a new descriptor format version, see [Migrating from Component Metadata to Descriptor](Migrating_from_Component_Metadata_to_Descriptor_e282db2.md)

-   Inside namespace: Describes the namespace format version \(optional from version 1.38 on\)


***

### Example

Current version of the `manifest.json`

```collapsible

{
    "_version": "1.16.0",
 
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
        "ach": "PA-FIO",
        "dataSources": {
            "equipment": {
                "uri": "/sap/opu/odata/snce/PO_S_SRV;v=2/",
                "type": "OData",
                "settings": {
                    "odataVersion": "2.0",
                    "annotations": ["equipmentanno"],
                    "localUri": "model/metadata.xml",
                    "maxAge": 360
                }
            },
            "equipmentanno": {
                "uri": "/sap/bc/bsp/sap/BSCBN_ANF_EAM/BSCBN_EQUIPMENT_SRV.anno.XML",
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
        "crossNavigation": {
            "scopes": {
                "sapSite": {
                    "value": "123"
                }
            },
            "inbounds": {
                "contactCreate": {
                    "semanticObject": "Contact",
                    "action": "create",
                    "icon": "sap-icon://add-contact",
                    "title": "{{title}}",
                    "subTitle": "{{subtitle}}",
                    "shortTitle": "{{shorttitle}}",
                    "info": "{{info}}",
                    "displayMode": "HeaderMode",
                    "indicatorDataSource": {
                        "dataSource": "equipment",
                        "path": "TaskListSet/$count",
                        "refresh": 5
                    },
                    "deviceTypes": {
                        "desktop": true,
                        "tablet": true,
                        "phone": false
                    },
                    "signature": {
                        "parameters": {
                            "id": {
                                "required": true
                            },
                            "ContactName": {
                                "defaultValue": {
                                    "value": "anonymous"
                                },
                                "required": false,
                                "renameTo": "NAME2"
                            },
                            "Gender": {
                                "filter": {
                                    "value": "(male)|(female)",
                                    "format": "regexp"
                                },
                                "required": true,
                                "renameTo": "SEX",
                                "launcherValue": {
                                    "value": "female",
                                    "format": "plain"
                                }
                            }
                        },
                        "additionalParameters": "ignored"
                    }
                },
                "contactDisplay": {
                    "semanticObject": "Contact",
                    "action": "display",
                    "signature": {
                        "parameters": {
                            "id": {
                                "required": true
                            },
                            "Language": {
                                "filter": {
                                    "value": "EN"
                                },
                                "required": true
                            },
                            "SomeValue": {
                                "filter": {
                                    "value": "4711"
                                }
                            },
                            "GLAccount": {
                                "defaultValue": {
                                    "value": "1000"
                                },
                                "filter": {
                                    "value": "(1000)|(2000)",
                                    "format": "regexp"
                                }
                            }
                        }
                    }
                },
                "contactDisplayAlt": {
                    "semanticObject": "Contact",
                    "action": "display",
                    "hideLauncher": true,
                    "signature": {
                        "parameters": {
                            "GLAccount": {
                                "defaultValue": {
                                    "value": "UserDefault.GLAccount",
                                    "format": "reference"
                                },
                                "filter": {
                                    "value": "\\d+",
                                    "format": "regexp"
                                },
                                "required": true
                            },
                            "SomePar": {
                                "filter": {
                                    "value": "UserDefault.CostCenter",
                                    "format": "reference"
                                },
                                "required": true
                            }
                        }
                    }
                }
            },
            "outbounds": {
                "addressDisplay": {
                    "semanticObject": "Address",
                    "action": "display",
                    "additionalParameters": "ignored",
                    "parameters": {
                        "CompanyName": {
                            "value": {
                                "value": "companyName",
                                "format": "plain"
                            },
                            "required": true
                        }
                    }
                },
                "companyDisplay": {
                    "semanticObject": "Company",
                    "action": "display",
                    "additionalParameters": "allowed",
                    "parameters": {
                        "CompanyName": {
                            "value": {
                                "value": "companyName",
                                "format": "plain"
                            },
                            "required": true
                        }
                    }
                }
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
            "minUI5Version": "1.66.0",
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
        "autoPrefixId": true,
        "appVariantId": "hcm.leaverequest.oil",
        "appVariantIdHierarchy": [
            {"layer": "VENDOR", "appVariantId": "abc", "version": "1.0.0"}
        ],
        "services": {
            "myLocalServiceAlias": {
                "factoryName": "sap.ushell.LaunchPadService",
                "optional": true
            }
        },
        "library": {
            "i18n": true
        },
                "flexEnabled": true,
        "commands": {
            "Save": {
                "shortcut": "Ctrl+S"
            }
        }
	    },
 
    "sap.platform.abap": {
        "uri": "/sap/bc/ui5_ui5/sap/appName",
        "uriNwbc": ""
    },
 
    "sap.platform.hcp": {
        "uri": "",
        "uriNwbc": "",
        "providerAccount": "fiori",
        "appName": "sapfioriappName",
        "appVersion": "1.0.0",
        "multiVersionApp": true
    },
 
    "sap.fiori": {
        "registrationIds": [
            "F1234"
        ],
        "archeType": "transactional"
    },
 
    "sap.mobile": {},
    "sap.flp": {},
    "sap.ui.generic.app": {},
    "sap.ovp": {},
    "sap.ui.smartbusiness.app": {},
    "sap.wda": {},
    "sap.gui": {},
    "sap.cloud.portal": {},
    "sap.apf": {},
    "sap.platform.cf": {},
    "sap.copilot": {},
    "sap.map": {},
    "sap.fe": {},
    "sap.url": {},
    "sap.platform.sfsf": {},
    "sap.wcf": {},
    "sap.cloud": {},
    "sap.integration": {},
    "sap.card": {},
\}
```

The following namespaces are in responsibility of the corresponding teams:

-   sap.mobile - in Mobile responsibility

-   sap.flp - in SAP Fiori Launchpad responsibility

-   sap.ui.generic.app - in SAP Fiori elements responsibility

-   sap.ovp - in Overview Page responsibility

-   sap.ui.smartbusiness.app - in Smart Business responsibility

-   sap.wda - in Web Dypro ABAP responsibility

-   sap.gui - in SAP GUI responsibility

-   sap.cloud.portal - in SAP Cloud Portal responsibility

-   sap.apf - in analysis path framework responsibility

-   sap.platform.cf - in cloud foundry/xsa responsibility

-   sap.map - in SAP Visual Business responsibility

-   sap.fe - in SAP Fiori Elements responsibility

-   sap.url - in SAP Fiori Launchpad responsibility

-   sap.platform.sfsf - for SAP SuccessFactors specific attributes

-   sap.wcf - for WCF Application specific attributes

-   sap.cloud - for SAP Cloud Platform specific attributes

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

### SAPUI5 API

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

[Component Metadata](Component_Metadata_0187ea5.md)

