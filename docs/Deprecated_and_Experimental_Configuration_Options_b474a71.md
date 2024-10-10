<!-- loiob474a712ca364d40a1b0a804baf2d734 -->

| loio |
| -----|
| b474a712ca364d40a1b0a804baf2d734 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/b474a712ca364d40a1b0a804baf2d734) | [demo kit latest release](https://sdk.openui5.org/topic/b474a712ca364d40a1b0a804baf2d734)</div>

## Deprecated andExperimental Configuration Options

The following tables showdeprecated and experimental configuration options.

> ### Note:  
> In earlier framework versions, the configuration options available in OpenUI5 could be found in the [API Reference via the `sap.ui.core.Configuration`](https://sdk.openui5.org/api/sap.ui.core.Configuration). This legacy module has been deprecated with OpenUI5 1.120 and replaced by a modular, future-proof solution for configuration handling.

> ### Note:  
> The OpenUI5 configuration options now follow a consistent naming scheme based on kebab-case notation. Configuration options in older framework versions or code samples \(especially those from before OpenUI5 1.120\) may follow the former camelCase notation. Typically, you should now use \(or search for\) the newer names, e.g. `log-level` instead of `logLevel`.

***

<a name="loiob474a712ca364d40a1b0a804baf2d734__section_ix3_4bv_fzb"/>

### Deprecated Options

The following configuration options are deprecated and should no longer be used in future-proof coding:


<table>
<tr>
<th valign="top">

Option

</th>
<th valign="top">

Description

</th>
<th valign="top">

by URL parameter

</th>
<th valign="top">

[by API](Configuration_of_the_OpenUI5_Runtime_91f08de.md#loio91f08de06f4d1014b6dd926db0e91070__section_ACO)

</th>
</tr>
<tr>
<td valign="top">

`animation`

\(deprecated\)

</td>
<td valign="top">

Type: `boolean`

Default value: `true`

For all controls that implement the `animation` parameter, the `animation-mode` is set as follows:

-   If `animation` is set to `true`, this is interpreted as `animation-mode` `full`

-   If `animation` is set to `false`, this is interpreted as `animation-mode` `minimal`




</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`areas`

\(deprecated\)

</td>
<td valign="top">

Type: `string[]`

Default value: `null`

This configuration parameter defines UI areas that shall be created in advance.

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`auto-aria-body-role`

\(deprecated\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Determines whether the framework automatically adds the ARIA role `application` to the HTML body.

As of OpenUI5 version 1.78, `autoAriaBodyRole` has a default value `false` in order to conform to the ARIA 1.1 recommendations. Role application on body level is not recommended, as the screen reader would then interpret the entire application as one big custom control.

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`binding-syntax`

\(deprecated\)

</td>
<td valign="top">

Type: `string`

Default value: `complex`

This configuration parameter defines whether the simple or the complex binding syntax is used. The parameter only affects bindings that are defined as strings, for example in the constructor of a control, or when specifying a binding in a declarative view, such as an XML view.

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`format-settings`

\(deprecated\)

</td>
<td valign="top">

Type: `sap.ui.core.Configuration.FormatSettings`

Encapsulates configuration settings that are related to data formatting / parsing. When format configuration settings are modified through this class, UI5 only ensures that formatter objects created after that point in time will honor the modifications. To be on the safe side, applications should do any modifications early in their lifecycle or recreate any model/UI that is locale dependent.

Example usage: `sap.ui.getCore().getConfiguration().getFormatSettings().setCustomUnits(...)`

For more information, see the [API Reference: `sap.ui.core.Configuration.FormatSettings`](https://sdk.openui5.org/api/sap.ui.core.Configuration.FormatSettings)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`manifest-first`

\(deprecated\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Modifiable at runtime by using the `sap.ui.core.Component.create` component factory.

If set to `true`, the descriptor for a component is read and evaluated first, before loading the component code \(`Component.js`\).

For more information, see: [`sap.ui.core.Component.create`](https://sdk.openui5.org/api/sap.ui.core.Component/methods/sap.ui.core.Component.create)

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`no-duplicate-ids`

\(deprecated\)

</td>
<td valign="top">

Type: `boolean`

Default value: `true`

If set to `true`, this configuration parameter enforces that the same IDs are **not** used for multiple controls; we highly recommend this check as duplicate IDs may cause unforeseeable issues and side effects.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`origin-info`

\(deprecated\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

If set to `true`, additional information for text resources is provided that allows to determine the origin of a translated text on the UI.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`preload`

\(deprecated\)

</td>
<td valign="top">

[Type](Configuration_Options_and_URL_Parameters_91f2d03.md#loio91f2d03b6f4d1014b6dd926db0e91070__section_TVT): `string`

Default value: `auto`

Defines the loading behaviour of the so-called preload files. They contain all modules of a library. The contained modules are only loaded, but not executed until they are used by the application.

The values are used as follows:

-   When set to `auto`, the runtime loads preload files asynchronously if the bootstrap configuration parameter `async` is set as `async=true`. We recommend to use the `async=true` configuration parameter in the bootstrap, as it switches many module-related APIs to `async`, including the loading behaviour of the preload files.
-   Preload files for the declared libraries are loaded synchronously when the `async` bootstrap configuration parameter is set to`false` \(`async=false`\) or not set at all. Best practices discourage such behavior.
-   For any other value \(for example blank\), the preload feature is deactivated and modules are loaded on demand.



</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`trace`

\(deprecated\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Defines whether a trace view should be shown.

Has only an effect when the `sap-ui-debug.js` module has been loaded, either explicitly or by setting the `debug` option to `true`.

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
</table>

***

### Experimental Options

The options listed in the table below are 'experimental'. They may be removed in future versions, or their definition or behavior may change in an incompatible way. Experimental options are identified by the name prefix `xx-`. Experimental configuration options are used for support scenarios where OpenUI5 development needs the freedom to evolve supportability features over time. Others are related to experimental features where the underlying feature still may change. When an experimental configuration option becomes mature, the `xx-` prefix is removed from the definition. For compatibility reasons, the old name with the `xx-` prefix will still be supported.

> ### Note:  
> The features listed below are experimental features and may be modified or removed in future versions.


<table>
<tr>
<th valign="top">

Option

</th>
<th valign="top">

Description

</th>
<th valign="top">

by URL parameter

</th>
<th valign="top">

[by API](Configuration_of_the_OpenUI5_Runtime_91f08de.md#loio91f08de06f4d1014b6dd926db0e91070__section_ACO)

</th>
</tr>
<tr>
<td valign="top">

`xx-app-cache-buster-mode`

\(experimental\)

</td>
<td valign="top">

Type: `string`

Default value: `sync`

The loading mode of the AppCacheBuster.

Options: `sync | async | batch`.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-app-cache-buster-hooks`

\(experimental\)

</td>
<td valign="top">

Type: `object`

Default value: `undefined`

Object defining the callback hooks for the AppCacheBuster like e.g. `handleURL`, `onIndexLoad` or `onIndexLoaded`.

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-cache-excluded-keys`

\(experimental\)

</td>
<td valign="top">

Type: `string[]`

Default value: `[]`

A list of all keys that the Cache Manager will ignore when setting or getting values.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-cache-serialization`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Whether the Cache Manager serialization support is switched on.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-cache-use`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `true`

Whether the Cache Manager is switched on.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-component-preload`

\(experimental\)

</td>
<td valign="top">

Type: `string`

Default value: same as `preload`

Allows to suppress the preload of component resources \(`Component-preload.js`\). By default, the component resources are automatically preloaded when preloads are active in general \(e.g. when running against the optimized OpenUI5 runtime and not running in debug mode\). With this parameter, the preload can be switched off without affecting the library preload. `sync` or `async` have no meaning; both are accepted to be compatible with the library preload, but the code that creates a component decides whether this happens synchronously or asynchronously.

Options: `sync | async | off`.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-debug-module-loading`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

When set to `true`, the OpenUI5 module loading feature produces `DEBUG` output for every required, executed, or required but already loaded module. This can help to analyse issues with dependency order, and so on.

By default, the log level is the same as for the standard log, but not higher than `INFO`.

With the experimental config option `xx-debugModuleLoading`, it can be raised to `DEBUG`.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-debug-rendering`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

When set to `true`, some components of the OpenUI5 rendering system \(`RenderManager`, `UIArea`\) create a far more verbose debug output for rendering steps, for example:

-   Which controls have to be rendered?

-   Who invalidated the control? \(stacktrace\)

-   Was one rendering run sufficient, or have there been multiple runs?




</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-dep-cache`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Whether dependency cache info files should be loaded instead of preload files.

This experimental feature is intended for HTTP/2 scenarios.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-design-mode`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Whether the design mode is active or not.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-disable-customizing`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Whether the customizing is disabled or not.

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-future`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Whether to enforce throwing exceptions for fatal warnings and errors. This helps you to detect and resolve critical issues which may prevent projects from running in future framework versions such as UI5 2.x.

For a version-dependent guidance, see *Strict Error Handling* in [Best Practices for Developers](Best_Practices_for_Developers_28fcd55.md).

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-handle-validation`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Whether type validation is handled by the Core.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-hyphenation`

\(experimental\)

</td>
<td valign="top">

Type: `string`

Default value: `''`

Force hyphenation to use only browser-native or only third-party.

Options: `native | thirdparty | disable`.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-lesssupport`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Enable `LessSupport`.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-library-preload-files`

\(experimental\)

</td>
<td valign="top">

Type: `string[]`

Default value: `both`

Allows to enforce the use of a specific preload file type:

-   for all libraries: `?sap-ui-xx-libraryPreloadFiles=json`

-   for individual libraries \(might be a comma separated list\): `?sap-ui-xx-libraryPreloadFiles=sap.m:none,sap.ui.layout:json`

-   for a combination of both: `?sap-ui-xx-libraryPreloadFiles=both,sap.m:none,sap.ui.layout:js` 


Possible values for the file types are

-   `none` \(no preload at all\)

-   `json` \(only try to load `library-preload.json`\)

-   `js` \(only try to load `library-preload.js`\)

-   `both` \(first try `js`, then `json`\).


Any other value will be ignored. The default is `both` for all libraries.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-noless`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Only useful at development time: when set to `true`, the browser-based compilation of LESS theming files is suppressed. Only the CSS that is created at build-time will be loaded.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-nosync`

\(experimental\)

</td>
<td valign="top">

Type: `string`

When set to `warn`, any use of synchronous XHRs will be reported with a warning in the console. When set to `true`, such calls will cause an error.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-supported-languages`

\(experimental\)

</td>
<td valign="top">

Type: `string[]`

Default value: `[]`

With this option the client can be instructed to limit its back-end requests for translatable texts to the configured set of languages. An empty value or the value `*` allows any language. The value `default` limits the requests to the set of languages that are delivered with OpenUI5.

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-self-closing-check`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

Only useful for development / support: Issues a warning if a non-void HTML element is written in self-closing syntax. For more information, see [Upgrading from a Version Below 1.82](Upgrading_from_a_Version_Below_1_82_147eef9.md).

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-suppress-deactivation-of-controller-code`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `false`

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-root-component-node`

\(experimental\)

</td>
<td valign="top">

Type: `string` 

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-view-cache`

\(experimental\)

</td>
<td valign="top">

Type: `boolean`

Default value: `true`

Allows to disable the view caching, for example, during development \(see [XML View Cache](XML_View_Cache_3d85d5e.md)\).

</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
<tr>
<td valign="top">

`xx-wait-for-theme`

\(experimental\)

</td>
<td valign="top">

Type: `string`

Default value: `undefined`

Possible values are:

-   `undefined` \(default\)

    By default neither the initialization of the OpenUI5 Core nor the first rendering wait for the configured theme to be loaded.

-   `rendering`

    The first \(initial\) rendering of the application will be delayed until the theme has been loaded and applied \(until `Core.isThemeApplied()`\). Helps to avoid FOUC \(flash of unstyled content\).

-   `init`

    Same as `rendering`, but additionally delays the `init` event of theOpenUI5 Core until the configured theme has been loaded. Application code that waits for this event can then rely on the theming information to be present, e.g. for calling [`sap.ui.core.theming.Parameters.get`](https://sdk.openui5.org/api/sap.ui.core.theming.Parameters/methods/sap.ui.core.theming.Parameters.get)

    See also:

    -   [`onInit` function/module](Initialization_Process_91f2c90.md#loio91f2c9076f4d1014b6dd926db0e91070)
    -   [`Core.ready`](Initialization_Process_91f2c90.md#loio91f2c9076f4d1014b6dd926db0e91070)




</td>
<td valign="top">

![YES](images/loio3929e469c7824eb0a69206aeac69f257_LowRes.png)

</td>
<td valign="top">

![NO](images/loiodfb38de82f6d46dab60cb1397e3ed8ae_LowRes.png)

</td>
</tr>
</table>

