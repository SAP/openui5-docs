<!-- loioeba8d25a31ef416ead876e091e67824e -->

| loio |
| -----|
| eba8d25a31ef416ead876e091e67824e |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/eba8d25a31ef416ead876e091e67824e) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/eba8d25a31ef416ead876e091e67824e)</div>

## Terminologies

By defining terminologies together with additional resource bundles, an application can easily be switched from one scenario or industry to another.

This chapter describes a concept for dynamically adapting applications for different scenarios and industries. We will first look at how you can define terminologies for your application via the `manifest.json`. Afterwards we will describe how you can dynamically activate the defined terminologies during startup of your application component.

***

<a name="loioeba8d25a31ef416ead876e091e67824e__section_ConfigTerminology"/>

### Configuration of Terminologies

A terminology, such as "Travel" or "Sports", is a set of resource bundles / .properties files for an application-specific scenario that the developer can activate by configuring it as described below.

The following table shows the configuration options that can be specified in the `manifest.json` descriptor file of your application or component. The configuration can be placed under either the `sap.app/i18n` or the `sap.ui5/models` section for models of type `sap.ui.model.resource.ResourceModel`.

<a name="loioeba8d25a31ef416ead876e091e67824e__table_ConfigOptions"/>Configuration Options for Terminologies


<table>
<tr>
<th valign="top">

Property



</th>
<th valign="top">

Type



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

 `bundleName` 



</td>
<td valign="top">

 `String` 



</td>
<td valign="top">

 OpenUI5 module name in dot notation referring to the main `.properties` file.



</td>
</tr>
<tr>
<td valign="top">

 `bundleUrl` 



</td>
<td valign="top">

 `String` 



</td>
<td valign="top">

URL pointing to the `.properties` file of the main bundle.



</td>
</tr>
<tr>
<td valign="top">

 `bundleUrlRelativeTo` 



</td>
<td valign="top">

 `String` 



</td>
<td valign="top">

The bundle URL can be resolved relative to either `manifest` \(default\) or `component`.



</td>
</tr>
<tr>
<td valign="top">

 `supportedLocales` 



</td>
<td valign="top">

 `String[]` 



</td>
<td valign="top">

An array containing a list of supported locales, for example `en_GB`, `en-GB`, or `en`. It is recommended to make use of this option in order to optimize the **loading performance** of resource bundles. It controls the language fallback chain and prevents unnecessary and potentially failing requests, as the available language-specific resource bundles are already known.



</td>
</tr>
<tr>
<td valign="top">

 `fallbackLocale` 



</td>
<td valign="top">

 `String` 



</td>
<td valign="top">

The fallback locale in case the user's locale is not present in the list of supported locales or the required text can't be found in any other resource bundle. Furthermore, the given fallback locale must be listed in the `supportedLocales`.



</td>
</tr>
<tr>
<td valign="top">

 `terminologies` 



</td>
<td valign="top">

 `Object` 



</td>
<td valign="top">

A key-value map in which the name of a terminology is specified as a key and a configuration object as a value. The configuration object must be specified with either `bundleName` or `bundleUrl`. Additionally, `bundleUrlRelativeTo` and `supportedLocales` can be specified. See the example below.



</td>
</tr>
<tr>
<td valign="top">

 `enhanceWith` 



</td>
<td valign="top">

 `Object[]` 



</td>
<td valign="top">

List of additional resource bundle configurations to enhance the main bundle. Each entry can have the same properties as described in this table, **except another `enhanceWith`**.



</td>
</tr>
</table>

> ### Note:  
> In case the properties `bundleName` and `bundleUrl` have both been specified, `bundleName` will be preferred.

> ### Note:  
> Certain ABAP systems implement their own language fallback mechanism, which might lead to unwanted results if you're using terminologies. For example, a request of a French resource bundle file \(such as `../i18n_fr.properties`\) might be answered with English content in case there is no available French version in the back end.
> 
> To prevent this behavior, you need to explicitly set the `supportedLocales` option to the actual valid set of supported languages for the back end.

**Example:**

The following JSON excerpt is valid for models of type `sap.ui.model.resource.ResourceModel` inside the `manifest.json` in both the `sap.app/i18n` and the `sap.ui5/models` sections. For other models, the configuration must be placed in the `settings` property. For more information, see [Descriptor for Applications, Components, and Libraries \(manifest.json\)](Descriptor_for_Applications_Components_and_Libraries_manifest_json_be0cf40.md).

The code block given below shows a sample configuration from the [Shop Administration Tool](https://openui5.hana.ondemand.com/test-resources/sap/tnt/demokit/toolpageapp/webapp/index.html)*Shop Administration Tool* demo app in the OpenUI5 Demo Kit. It has the main resource bundle `i18n/i18n.properties` and the defined terminologies `sports`, `travel`, and `services`. The main bundle is enhanced with the additional resource bundles `reuse/appvar1/i18n/i18n.properties` and `reuse/appvar2/i18n/i18n.properties`. These enhancements also provide terminologies \(`appvar1`: "sports-soccer" and "travel-vehicles"; `appvar2`: "travel-bicycles"\).

The second bundle with the bundleUrl `reuse/appvar2/i18n/i18n.properties` does not derive directly from the main resource bundle as you might think, but from the first enhancement. The list of resource bundle configurations provided with the `enhanceWith` attribute can be seen as an incremental list of derivations for resource bundles that starts from the main bundle. If there was a third enhancing bundle, it would derive from the second bundle, which in turn derives from the first enhancement, and so on:

``` json

{
    "bundleUrl": "i18n/i18n.properties",
    "bundleUrlRelativeTo": "manifest",
    "supportedLocales": ["en", "de"],
    "fallbackLocale": "en",
    "terminologies": {
        "sports": {
            "bundleUrl": "i18n/terminologies/sports/i18n.terminologies.sports.properties",
            "bundleUrlRelativeTo": "manifest",
            "supportedLocales": ["en", "de"]
        },
        "travel": {
            "bundleUrl": "i18n/terminologies/travel/i18n.terminologies.travel.properties",
            "bundleUrlRelativeTo": "manifest",
            "supportedLocales": ["en", "de"]
        },
        "services": {
            "bundleUrl": "i18n/terminologies/services/i18n.terminologies.services.properties",
            "bundleUrlRelativeTo": "manifest",
            "supportedLocales": ["en", "de"]
        }
    },
    "enhanceWith": [
        {
            "bundleUrl": "reuse/appvar1/i18n/i18n.properties",
            "bundleUrlRelativeTo": "manifest",
            "supportedLocales": ["en", "de"],
            "fallbackLocale": "en",
            "terminologies": {
                "sports": {
                    "bundleUrl": "reuse/appvar1/i18n/i18n.terminologies.soccer.properties",
                    "bundleUrlRelativeTo": "manifest",
                    "supportedLocales": ["en", "de"]
                },
                "travel": {
                    "bundleUrl": "reuse/appvar1/i18n/i18n.terminologies.vehicles.properties",
                    "bundleUrlRelativeTo": "manifest",
                    "supportedLocales": ["en", "de"]
                }
            }
        },
        {
            "bundleUrl": "reuse/appvar2/i18n/i18n.properties",
            "bundleUrlRelativeTo": "manifest",
            "supportedLocales": ["en", "de"],
            "fallbackLocale": "en",
            "terminologies": {
                "travel": {
                    "bundleUrl": "reuse/appvar2/i18n/i18n.terminologies.bicycles.properties",
                    "bundleUrlRelativeTo": "manifest",
                    "supportedLocales": ["en", "de"]
                }
            }
        }
    ]
}
...
```

***

<a name="loioeba8d25a31ef416ead876e091e67824e__section_ActivTerminologies"/>

### Activation of Terminologies

There are three ways to specify which terminologies should be activated in your application. A list of active terminologies must be provided in each case. Attention must be paid to the order in which the active terminologies are given. The terminology with the highest priority comes first.

The list of active terminologies can be any subset of the terminologies defined in the `manifest.json`. For example, only `travel` could be activated from the available terminologies `sports`, `travel`, and `services` that are defined in the manifest. In case terminologies are provided for which no content is available, nothing will happen.

In the examples below, the terminology `travel` has the highest priority as it is given as the first argument in this list \[ `travel`, `services`\]. According to this list and the configuration above, the `appvar2` bundle \("travel-bicycles"\) overrides/enhances the content of the `appvar1` bundle \("travel-vehicles"\), the `i18n.terminologies.travel.properties` file, and the main resource bundle including the `services` bundle.

***

#### Activate Terminologies via the API

The most relevant option is to pass the list of active terminologies as an array of strings to the factory functions of the `sap.ui.core.Component`. In case of nested components, the active terminologies will be inherited from the owner component.

 For more information and additional usage instructions, see the [API Reference: `sap.ui.core.Component.create`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Component%23methods/sap.ui.core.Component.create). 

``` js

sap.ui.require(["sap/ui/core/Component"], function(Component) {
    return Component.create({
        name: "my.sample.app",
        manifest: true,
        activeTerminologies: ["travel", "services"]
    }).then(function(oComponent) {
        // Component and resource bundles are loaded
        return oComponent.createComponent("myReuseComponent").then(function(oReuseComponent) {
            // oReuseComponent inherits from owner component
            oReuseComponent.getActiveTerminologies(); // returns ["travel", "services"]
        });
    });
});
```

***

#### Activate Terminologies via URL Parameter

> ### Note:  
> The activation of terminologies via URL parameter is mainly intended for testing purposes.

Another option is to attach the URL parameter `sap-ui-activeTerminologies` with a comma-separated list of terminologies to the URL:

``` html
?sap-ui-activeTerminologies=travel,services

```

***

#### Activate Terminologies via the Bootstrap Configuration

> ### Note:  
> The activation of terminologies via the bootstrap configuration is mainly intended for testing purposes.

A third option is to provide the list of active terminologies \(also comma-separated\) in the bootstrap configuration via the `data-sap-ui-activeTerminologies` attribute:

``` html
<script id="sap-ui-bootstrap"
     type="text/javascript"
     src="resources/sap-ui-core.js"
     data-sap-ui-activeTerminologies="travel,services">
</script>
```

**Related Information**  


[API Reference: sap/ui/model/resource/ResourceModel](https://openui5.hana.ondemand.com/#/api/sap.ui.model.resource.ResourceModel)

[API Reference: sap/base/i18n/ResourceBundle](https://openui5.hana.ondemand.com/#/api/module:sap/base/i18n/ResourceBundle)

[Shop Administration Tool demo app](https://openui5.hana.ondemand.com/test-resources/sap/tnt/demokit/toolpageapp/webapp/index.html)

