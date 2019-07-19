<!-- loio91f08de06f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f08de06f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f08de06f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f08de06f4d1014b6dd926db0e91070)</div>

## Configuration of the OpenUI5 Runtime

OpenUI5 provides several options for the configuration of the OpenUI5 runtime, such as runtime default values and script tag attributes.

When the OpenUI5 bootstrap script is included in a page, the OpenUI5 runtime will automatically be initialized as soon as the script is loaded and executed by the browser. For simple use cases and for a default OpenUI5 installation, this should already be sufficient to build and run UIs. The only additional information that usually is specified, is the set of libraries and the theme that is used.

So a typical bootstrap script looks like this:

``` html
<script id="sap-ui-bootstrap"
            type="text/javascript"
            src="resources/sap-ui-core.js"
            data-sap-ui-theme="sap_belize"
            data-sap-ui-libs="sap.m"
            data-sap-ui-compatVersion="edge">
</script>
```

For more information see [Bootstrapping: Loading and Initializing](Bootstrapping_Loading_and_Initializing__a04b0d1.md).

You can use the following ways to provide configuration information.

***

### Default Values

The easiest way to specify a configuration value is **not to specify** it. The OpenUI5 runtime contains a default value for each configuration option. As long as you don't have to change the value, you don't specify it.

***

### Individual Script Tag Attributes

For each configuration option, you can have one attribute in the bootstrap script tag.

The attributes have to provide the following information:

-   Attribute name

    The attribute name is composed of the name of the configuration option and the `data-sap-ui-` prefix. The first part of the prefix \(`data-`\) is necessary to comply with the W3C recommendations for custom attributes in HTML. The second part \(`-sap-ui-`\) separates OpenUI5 attributes from custom attributes defined by any other framework.

    > Note:
    > Attribute names in HTML are case-insensitive and this also applies to the configuration attribute names. However, OpenUI5 has defined some configuration options names in camel case, for example `originInfo`. OpenUI5 converts these names automatically to lower case when accessing the configuration.
    > 
    > 

-   Value

    Element attributes in HTML have a `string` value by definition. For configuration options of type `string`, the attribute value is equivalent to the value of the option.

    > Note:
    > If the value contains specific HTML characters, such as '<' or '\>', or if the value contains the same quote character that is used to wrap the attribute value, the usual HTML escape mechanisms must be used: Use entities for the specific HTML characters, for example `&lt;` instead of `<`, and switch the type of quotes from single to double or vice versa.
    > 
    > 

    For configuration options that are **not** of type `string`, the format of the allowed values has to be defined as follows:

    |Type|Notation/Values|
    |----|---------------|
    |`string`|String; escaped according to the HTML conventions|
    |`boolean`|`true` and `x` are both accepted as true values \(case-insensitive\), all others are false. We recommend to use `false` for false values|
    |`int`|Any integer value|
    |`string array`|Comma-separated list of values; comma is not supported in the values \(no escaping\)|
    |map from string to string|JavaScript object literal \(preferably JSON syntax\)|


***

### Single and Complex Configuration Attributes

The attribute `data-sap-ui-config` makes it possible to provide a single attribute with the configuration information for the OpenUI5 runtime.

You can use this attribute instead of attaching individual options with individual configuration attributes to the script tag. Its content is similar to the global configuration object, but without the enclosing parenthesis: It is a comma separated list of key-value pairs.

> Note:
> The usual HTML escape mechanisms must be used if the value contains specific HTML characters \(<, \>, &\) or the quote character that is used to enclose the attribute value.
> 
> 

``` html
<script id="sap-ui-bootstrap"
	type="text/javascript"
	src="resources/sap-ui-core.js"
	data-sap-ui-config="theme:'sap_belize',
	libs:'sap.m'"
	>
</script>
```

***

### Global Configuration Objects

The global configuration object is a property in the global `window` object with property name `sap-ui-config`. The property must be a simple object, where each property represents the configuration option of the corresponding name.

To avoid conflicts with typical JavaScript coding, the name of the `window` property is not a valid JavaScript identifier. The name structure is chosen to avoid conflicts with SAP objects. To define the object, quotes must be used. If a configuration option has a name that is not a valid JavaScript identifier or that is a reserved token in JavaScript, the property name in the configuration object must be quoted. Currently, such a configuration option does **not** exist.

As the configuration is evaluated during bootstrap, the configuration object must be created **before** OpenUI5 is bootstrapped. Otherwise, the contained configuration cannot be evaluated. As a consequence, using the global configuration object requires another script tag in front of the bootstrap script tag. It is up to the application whether it uses an inline script tag or a separate JavaScript file, which is loaded via a script tag, for this purpose. If you use a dedicated file, it may require more work initially, but offers the following advantages:

-   Several pages can share the file and, thus, use the same configuration.

-   The Content Security Policy \(CSP\) mechanism as introduced, for example, by Firefox 4.0 and others requires the use of a file.


The following code snippet shows an example for an inline script tag:

``` html
<script type="text/javascript">
            window["sap-ui-config"] = {
			theme : "sap_belize",
			libs : "sap.m",
            };
</script>
<script id="sap-ui-bootstrap" 
            src="resources/sap-ui-core.js"
		>
</script>
```

This option requires an additional script or script tag, but it offers the following advantages:

-   Possibility to share configuration between pages

-   Can be used in environments where the scrip tag cannot be influenced, for example, because it is created out of some configuration, like in some mashup frameworks

-   Allows to provide configuration before the core boots


***

### URL Parameters

Configuration parameters can be added to the URL of an app.

The URL parameter name is composed of the name of the configuration option and the `sap-ui-` prefix, for example like `index.html?sap-ui-debug=true`.

> Note:
> The W3C proposed that the `data-` prefix is not needed and not even allowed here as all URL parameters are kind of custom parameters.
> 
> 

The value of a URL parameter is of type `string` and the same type mapping as for HTML attributes applies. However, URLs require a different encoding than HTML; they use, for example % encoding instead of entity encoding.

For security reasons, only some configuration options can be set via URL parameters. An application can set the `ignoreUrlParameters` option to `true` to disable URL configuration parameters completely.

***

### Runtime Configuration Object

The runtime configuration object enables you to modify a limited set of configuration options at runtime.

The configuration options above are evaluated during the OpenUI5 runtime boots. After that, all changes to these parameters are ignored. To read the final configuration result, you can use the `sap.ui.getCore().getConfiguration()` method.

The same object also provides set methods for a very limited set of configuration options that can be modified at runtime. The runtime and/or the controls can react on these configuration changes. The most prominent \(and so far only\) example for such a configuration option is the theme.

***

### Order of Significance

1.  Attributes of the DOM reference override the system defaults.

2.  URL parameters override the DOM attributes; empty URL parameters reset the parameter to its system default.

3.  If you call setters at runtime, any previous settings calculated during object creation are overwritten with the new value.


