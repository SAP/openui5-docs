<!-- loio91f2d03b6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f2d03b6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f2d03b6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f2d03b6f4d1014b6dd926db0e91070)</div>

## Configuration Options and URL Parameters

The complete list of configuration options available in OpenUI5 can be found in the *API Reference* under `sap.ui.core.Configuration`. The following table shows a subset of the available configuration options.

> Note:
> A subset of these configuration parameters can also be used as URL parameter \("URL: Yes"\). The URL parameter name is composed of the name of the configuration option and the `sap-ui-` prefix, for example like `sap-ui-debug=true`.
> 
> 

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Option</th>
			<th>Type</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>`accessibility`</td>
			<td>Type: `boolean` Default value: `true` URL: Yes Modifiable at runtime: No If set to `true`, the OpenUI5 controls are rendered for or running in accessibility mode.</td>
		</tr>
		<tr>
			<td>`animationMode`</td>
			<td>Type: `string` Default value: `full` URL: Yes Modifiable at runtime: Yes The following animation modes are available:
 -   `full`: all animations are shown

 -   `basic`: a reduced, more light-weight set of animations

 -   `minimal`: no animations are shown, except animations of fundamental functionality

 -   `none`: deactivates the animation completely


 This parameter replaces the deprecated Boolean `animation` parameter. For all controls that implement the `animation` parameter, the `animationMode` is set as follows:

 -   If `animation` is set to `true`, this is interpreted as `animationMode` `full`

 -   If `animation` is set to `false`, this is interpreted as `animationMode` `minimal`
			</td>
		</tr>
		<tr>
			<td>`appCacheBuster`</td>
			<td>Type: `true </td>
			<td> string[]` Default value: \[\] URL: Yes Modifiable at runtime: Yes, with **AppCacheBuster** API \(see [Application Cache Buster: Enhanced Concept](Application_Cache_Buster_Enhanced_Concept_94e0c33.md)\) If set to a non empty list of URLs, the **AppCacheBuster** will be activated and will load component version info files from the configured set of URLs \(see [Application Cache Buster](Application_Cache_Buster_ff7aced.md)\).</td>
		</tr>
		<tr>
			<td>`areas`</td>
			<td>Type: `string[]` Default value: `null` URL: No This configuration parameter defines UI areas that shall be created in advance; use `` to create new UI areas and `sap.ui.getCore().getUIArea(id).destroy()` to delete existing UI areas at runtime.</td>
		</tr>
		<tr>
			<td>`autoAriaBodyRole`</td>
			<td>Type: `boolean` Default value: `true` URL: No Modifiable at runtime: No Determines whether the framework automatically adds the ARIA role `application` to the HTML body.</td>
		</tr>
		<tr>
			<td>`bindingSyntax`</td>
			<td>Type: `string` Default value:
 -   As of OpenUI5 1.28, in combination with `data-sap-ui-compatVersion="edge"`: `complex`

 -   `default`

The meaning of the default value `'default'` depends on the compatibility version `sapCoreBindingSyntax`. If the compatibility version is at least 1.28, the 'complex' binding syntax is assumed, otherwise the 'simple' binding type. In other words: applications that configured a general compatibility version of 1.28 \(or higher or 'edge'\), will automatically run with the 'complex' binding syntax.


 URL: No Modifiable at runtime: No This configuration parameter defines whether the simple or the complex binding syntax is used. The parameter only affects bindings that are defined as strings, for example in the constructor of a control, or when specifying a binding in a declarative view, such as XML view or HTML view.</td>
		</tr>
		<tr>
			<td>`calendarType`</td>
			<td>Type: `gregorian </td>
			<td> islamic </td>
			<td> japanese </td>
			<td> persian` \(case-sentitive\) Default value: If there is no value defined, the actual value is determined from the locale data for the configured locale. URL: Yes Modifiable at runtime: See [API Reference: `sap.ui.core.Configuration.setCalendarType`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Configuration/methods/setCalendarType). Defines the calendar type that is used for locale-dependent, date-related features \(for example, formatting or parsing date and time\).</td>
		</tr>
		<tr>
			<td>`debug`</td>
			<td>Type: `boolean` or `string` Default value: `false` URL: Yes Modifiable at runtime: No If set to `true`, the debug sources are loaded; if the bootstrap code is loaded from an optimized source, the bootstrap will be aborted and start anew from a debug source. You can also specify a comma-separated list as `string` that contains all modules that should be loaded as debug source. Example: `index.html?sap-ui-debug=sap/ui/model/odata/v2/` will load all debug sources for all modules of the OData V2 model. All others modules will be taken from the preload \(if preload is active\). You can use the following patterns:
 -   A trailing slash \(`/`\) means that the complete package should be included \(shortcut for `/**/*`\)

Example: `sap/ui/model/odata/v2/` loads everything from the `sap/ui/model/odata/v2/` package as debug source \(also nested packages `sap/ui/model/odata/v2/**/*`\).

 -   `**/` matches any package or sequence of packages

Example: `**/v2/` loads any package named `v2` as debug sources like `odata/v2`, `json/v2/` etc.

 -   `*` matches any part of a simple name

Example: `sap/ui/model/*` matches all files directly contained in the model package, but not in nested packages \(for example, not `v2` or `v4`\)


 > Note:
 > You can also select the debug sources in the technical information dialog. For more information, see [Technical Information Dialog](Technical_Information_Dialog_.md#loio616a3ef07f554e20a3adf749c11f64e9).
			</td>
		</tr>
		<tr>
			<td>`formatLocale`</td>
			<td>Type: `string` Default value: `undefined` URL: Yes Modifiable at runtime: No This configuration parameter defines the locale used for formatting purposes; the default values for the locale are derived from the language.</td>
		</tr>
		<tr>
			<td> `frameOptions` </td>
			<td>Type: `string` Default value: `default` URL: No Modifiable at runtime: No Frame options mode; for more information, see [Frame Options](Frame_Options_62d9c4d.md) </td>
		</tr>
		<tr>
			<td> `frameOptionsConfig` </td>
			<td>Type: `object` Default value: undefined URL: No Modifiable at runtime: No Advanced frame options configuration; for more information, see [Frame Options](Frame_Options_62d9c4d.md) </td>
		</tr>
		<tr>
			<td>`ignoreUrlParams`</td>
			<td>Type: `boolean` Default value: `false` URL: No Modifiable at runtime: No Security-relevant parameter that allows applications to disable configuration modifications via URL parameters.</td>
		</tr>
		<tr>
			<td>`inspect`</td>
			<td>Type: `boolean` Default value: `false` URL: Yes Modifiable at runtime: No If set to `true`, the `sap-ui-debug.js` module is included and provides some supportability features</td>
		</tr>
		<tr>
			<td>`language`</td>
			<td>Type: `string` Default value: `user language` URL: Yes Modifiable at runtime: Yes, with restrictions. This configuration parameter defines the language that shall be used for localized texts, formatting, and so on. For more information, see [API Reference: `sap.ui.core.Configuration.setLanguage`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Configuration/methods/setLanguage) and [Identifying the Language Code / Locale](Identifying_the_Language_Code__Locale_91f21f1.md). </td>
		</tr>
		<tr>
			<td>`libs`</td>
			<td>Type: `string[]` Default value: `[ ]` URL: No Modifiable at runtime: Yes This configuration parameter defines a list of libraries that shall be loaded initially; use the `loadLibrary()` method to load further libraries. For more information, see: [loadLibrary](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Core/methods/loadLibrary) </td>
		</tr>
		<tr>
			<td>`logLevel`</td>
			<td>Type: `0</td>
			<td>1</td>
			<td>2</td>
			<td>3</td>
			<td>4</td>
			<td>5</td>
			<td>6</td>
			<td>NONE</td>
			<td>FATAL</td>
			<td>ERROR</td>
			<td>WARNING</td>
			<td>INFO</td>
			<td>DEBUG</td>
			<td>ALL` Default value: `ERROR` URL: Yes Modifiable at runtime: Yes This configuration parameter sets the log level to the given value; for minified \(productive\) sources, the default level is `ERROR`, for debug sources it is `DEBUG`. At runtime, you can modify the log level by using the `sap/base/Log.setLevel` method.</td>
		</tr>
		<tr>
			<td>`manifestFirst`</td>
			<td>Type: `boolean` Default value: `false` URL: Yes Modifiable at runtime: Yes, by using option with same name in the **sap.ui.component** API If set to `true`, the descriptor for a component is read and evaluated first, before loading the component code \(`Component.js`\).</td>
		</tr>
		<tr>
			<td>`modules`</td>
			<td>Type: `string[]` Default value: `[ ]` URL: No This configuration parameter defines a list of JavaScript modules that shall be loaded after the core has been initialized.</td>
		</tr>
		<tr>
			<td>`noConflict`</td>
			<td>Type: `boolean` Default value: `false` URL: No Modifiable at runtime: No If set to `true`, OpenUI5 forces jQuery into `noConflict` mode.</td>
		</tr>
		<tr>
			<td>`noDuplicateIds`</td>
			<td>Type: `boolean` Default value: `true` URL: Yes Modifiable at runtime: No If set to `true`, this configuration parameter enforces that the same IDs are **not** used for multiple controls; we highly recommend this check as duplicate IDs may cause unforeseeable issues and side effects.</td>
		</tr>
		<tr>
			<td>`onInit`</td>
			<td>Type: `code` or `string` Default value: `undefined` URL: No Modifiable at runtime: No This configuration setting defines code that has to be executed after the initialization. The use of this parameter with string value as \(like `"myinitfunction();"`\) code is no longer recommended as it requires `eval` and therefore might conflict with stronger content security policies. Either use it only in the form `window["sap-ui-config"].onInit = function() { ... }` or use the runtime API **sap.ui.getCore\(\).attachInit\(\)** instead. If you define a `string`, this can be a reference to a function or a name of a module. Functions are resolved from the global namespace \(like `"myapp.initFunction"`\). Modules are indicated by the prefix `module:` \(like `"module:myapp/main/Module").` The module will be loaded and executed after the initialization.</td>
		</tr>
		<tr>
			<td>`originInfo`</td>
			<td>Type: `boolean` Default value: `false` URL: Yes Modifiable at runtime: No If set to `true`, additional information for text resources is provided that allows to determine the origin of a translated text on the UI</td>
		</tr>
		<tr>
			<td>`preload`</td>
			<td>Type: not specified, `auto`, `sync`, or `async` Default value: `auto` URL: No Modifiable at runtime: No This configuration parameter defines the loading behaviour of the so-called preload files. They contain all modules of a library. The contained modules are only loaded, but not executed until they are used by the application. The values are used as follows:

 -   When set to `auto`, OpenUI5 runtime automatically uses `preload=sync` when the `async` bootstrap configuration parameter is set to false \(`async=false`\) or not set at all. The `preload` files are loaded asynchronously in case `async=true` is set. -   When set to `sync`, the preload files for the declared libraries are loaded synchronously.
 -   When set to `async`, the preload files are loaded asynchronously. However, we recommend to use the `async=true` configuration parameter in the bootstrap instead, because it switches more module/related APIs to `async` including the loading behaviour of the preload files.
 -   For any other value \(for example blank\), the preload feature is deactivated and modules are loaded on demand.
			</td>
		</tr>
		<tr>
			<td>`async`</td>
			<td>Type: `boolean` Default value: `false` URL: Yes Modifiable at runtime: No This configuration setting enables the module loader to load both, modules and library-preload files asynchronously. Activating this feature requires intensive testing and cooperation on application side to ensure a stable and fully working application. In case you encounter issues, or if you want to prepare your application in advance, see [Is Your Application Ready for Asynchronous Loading?](Is_Your_Application_Ready_for_Asynchronous_Loading_493a15a.md).</td>
		</tr>
		<tr>
			<td>`preloadLibCss`</td>
			<td>Type: `string[]` Default value: `[]` URL: Yes Modifiable at runtime: No This configuration setting specifies a list of UI libraries using the same syntax as the `libs` property, for which the OpenUI5 core does not include the `library.css` stylesheet in the head of the page. If the list starts with an exclamation mark \(!\), no stylesheet is loaded at all for the specified libs. In this case, it is assumed that the application takes care of loading CSS, for example, a manually merged, single CSS file. Otherwise, the Core instructs the backend to create a merged CSS for the specified libs. In both cases, if the first libraries name is an asterisk \(\*\), it will be expanded to the list of already configured libraries.

 > Note:
 > The `merge` feature is currently only available for Java and only for apps that include the additional backend component `resource-ext`. Without the merge, applications can include their own merged CSS file and suppress the loading of the standard`library.css`.
			</td>
		</tr>
		<tr>
			<td>`resourceRoots`</td>
			<td>Type: `object` Default value: undefined URL: No Modifiable at runtime: With `sap.ui.loader.config({paths: ...})` , a map can be used to define locations for resources, see `sap.ui.loader` in the API reference. To provide a URL location that is **not** overwritten by a component later on, `final` can be set to `true`, for example: `{'url' : '/that/is/the/prefix/', 'final' : true}` For more information, see [jQuery.sap.registerModulePath](https://openui5.hana.ondemand.com/#/api/jQuery.sap/methods/jQuery.sap.registerModulePath) </td>
		</tr>
		<tr>
			<td>`rtl`</td>
			<td>Type: `boolean` Default value: `false` URL: Yes Modifiable at runtime: Yes, with restrictions. For more information, see [API Reference: `sap.ui.core.Configuration.setLanguage`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Configuration/methods/setLanguage) and [API Reference: `sap.ui.core.Configuration.setRTL`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Configuration/methods/setRTL). If set to `true`, all controls are rendered in right-to-left \(RTL\) mode; not yet determined automatically.</td>
		</tr>
		<tr>
			<td>`statistics`</td>
			<td>Type: `boolean` Default value: `false` URL: Yes Modifiable at runtime: No Activates end-to-end traces and measurement of response times For more information, see [Interaction Tracking for Performance Measurement](Interaction_Tracking_for_Performance_Measurement_b2825ea.md) </td>
		</tr>
		<tr>
			<td>`theme`</td>
			<td>Type: `string` Default value: `base` URL: Yes Modifiable at runtime: Yes This configuration parameter defines the theme that shall be used for the current page; you can change the theme at runtime by calling `sap.ui.getCore().applyTheme()`. **Theme Root:** When the theme string contains an at-sign \(`@`\), anything before the `@` is assumed to denote the ID of the theme while anything after the `@` is assumed to represent the URL location of the theme. To defend against XSS attacks, only tthe server-relative part of the URL is used, any host or port prefix will be ignored.</td>
		</tr>
		<tr>
			<td>`themeRoots`</td>
			<td>Type: `object` Default value: undefined URL: No Modifiable at runtime: `sap.ui.getCore().setThemeRoot()` This configuration parameter defines the location of themes.</td>
		</tr>
		<tr>
			<td>`trace`</td>
			<td>Type: `boolean` Default value: `false` URL: No Modifiable at runtime: No If set to `true`, this configuration parameter activates an overlay div that contains a trace.</td>
		</tr>
		<tr>
			<td>`uidPrefix`</td>
			<td>Type: `string` Default value: '--' URL: No Modifiable at runtime: No Prefix to be used for automatically generated control IDs; must be choosen carefully to avoid conflicts with IDs defined by the application or DOM IDs.</td>
		</tr>
		<tr>
			<td>`versionedLibCss`</td>
			<td>Type: `boolean` Default value: `false` URL: Yes Modifiable at runtime: No If set to `true`, the version parameters are included in requests to the library theme resource \(for example, the parameter `library.css?version=1.0.1&sap-ui-dist-version=1.0.2` is added. `version` contains the library version and `sap-ui-dist-version` the version of the OpenUI5 distribution . This applies to the following resources:
 -   `library(-RTL).css` \(or any other variation\)

 -   `library-parameters.json` 


URLs within the CSS or parameters are not modified.
			</td>
		</tr>
		<tr>
			<td>`weinreId`</td>
			<td>Type: `string` Default value: URL: Yes Modifiable at runtime: No</td>
		</tr>
		<tr>
			<td>`weinreServer`</td>
			<td>Type: `string` Default value: URL: No Modifiable at runtime: No URL to a WEINRE server to be used for debugging purposes; if set, OpenUI5 automatically includes the WEINRE target modules.</td>
		</tr>
		<tr>
			<td> `whitelistService` </td>
			<td>Type: `string` Default value: URL: No Modifiable at runtime: No URL to a whitelist service; see [Whitelist Service](Whitelist_Service_d04a6d4.md) </td>
		</tr>
	</tbody>
</table>

***

### Experimental Options

The options listed in the table below are 'experimental'. They may be removed in future versions, or their definition or behavior may change in an incompatible way. Experimental options are identified by the name prefix `xx-`. Experimental configuration options are used for support scenarios where OpenUI5 development needs the freedom to evolve supportability features over time. Others are related to experimental features where the underlying feature still may change. When an experimental configuration option becomes mature, the `xx-` prefix is removed from the definition. For compatibility reasons, the old name with the `xx-` prefix will still be supported.

|Option|Type|
|------|----|
|`xx-componentPreload`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 Type: `sync | async |off` Default value: same as `preload` URL: Yes Modifiable at runtime: No Allows to suppress the preload of component resources \(`Component-preload.js`\). By default, the component resources are automatically preloaded when preloads are active in general \(e.g. when running against the optimized OpenUI5 runtime and not running in debug mode\). With this parameter, the preload can be switched off without affecting the library preload. `sync` or `async` has no meaning, both are accepted to be compatible with the library preload, but the code that creates a component decides whether this happens synchronously or asynchronously. .|
|`xx-debugModuleLoading`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 Type: `boolean` Default value: `false` URL: Yes Modifiable at runtime: No When set to `true`, the SAPUI5 module loading feature produces `DEBUG` output for every required, executed, or required but already loaded module. This can help to analyse issues with dependency order, and so on.|
|`xx-debugRendering`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 Type: `boolean` Default value: `false` URL: Yes Modifiable at runtime: No When set to `true`, some components of the OpenUI5 rendering system \(`RenderManager`, `UIArea`\) create a far more verbose debug output for rendering steps, for example: -   Which controls have to be rendered?

-   Who invalidated the control? \(stacktrace\)

-   Was one rendering run sufficient, or have there been multiple runs?


 |
|`xx-libraryPreloadFiles`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 Type: `string[]` Default value: `both` URL: Yes Modifiable at runtime: No Allows to enforce the use of a specific preload file type:

-   for all libraries: `?sap-ui-xx-libraryPreloadFiles=json`

-   for individual libraries \(might be a comma separated list\): `?sap-ui-xx-libraryPreloadFiles=sap.m:none,sap.ui.layout:json`

-   for a combination of both: `?sap-ui-xx-libraryPreloadFiles=both,sap.m:none,sap.ui.layout:js` 


Possible values for the file types are

-   `none` \(no preload at all\)

-   `json` \(only try to load `library-preload.json`\)

-   `js` \(only try to load `library-preload.js`\)

-   `both` \(first try `js`, then `json`\).


Any other value will be ignored. The default is `both` for all libraries.

 |
|`xx-noless`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 Type: `boolean` Default value: `false` URL: Yes \(only!\) Modifiable at runtime: No Only useful at development time: when set to `true`, the browser-based compilation of LESS theming files is suppressed, only the CSS that is created at built-time will be loaded.|
|`xx-nosync`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 Type: `boolean` | `warn` Default value: `false` URL: Yes Modifiable at runtime: No When set to `warn`, any use of synchronous XHRs will be reported with a warning in the console. When set to `true`, such calls will cause an error.|
|`xx-showLoadErrors`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 When executing a loaded module synchronously, some browsers do not provide a proper error location. By setting this configuration parameter to `true`, OpenUI5 can be advised to load a failed script a second time, but asynchronously with a script tag. This usually results in an easier to understand syntax error message and a code location.|
|`xx-supportedLanguages`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 Type: `string[]` Default value: `[]` URL: Yes Modifiable at runtime: No With this option the client can be instructed to limit its backend requests for translatable texts to the configured set of languages. An empty value or the value `*` allows any language, the value `default` limits the requests to the set of languages that are delivered with OpenUI5.|
|`xx-test-mobile`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 Type: `boolean` Default value: `false` Modifiable at runtime: No This configuration parameter activates support for mobile device-specific events, such as touch events. This enables you to test standard OpenUI5 controls on mobile devices.|
|`xx-viewCache`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 Type: `boolean` Default value: `true` URL: Yes Modifiable at runtime: No Allows to disable the view caching, for example, during development. \(See [XML View Cache](XML_View_Cache_3d85d5e.md).\)|
|`xx-waitForTheme`| > Note:
> This is an experimental feature and may be modified or removed in future versions.
> 
> 

 Type: `boolean` Default value: `false` URL: Yes Modifiable at runtime: No If set to `true`, the first \(initial\) rendering of the application will be delayed until the theme has been loaded and applied \(until `Core.isThemeApplied()`\). Helps to avoid FOUC \(flash of unstyled content\).|

