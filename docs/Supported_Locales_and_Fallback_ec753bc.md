<!-- loioec753bc539d748f689e3ac814e129563 -->

| loio |
| -----|
| ec753bc539d748f689e3ac814e129563 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/ec753bc539d748f689e3ac814e129563) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/ec753bc539d748f689e3ac814e129563)</div>

## Supported Locales and Fallback

A list of supported locales can be created to restrict the number of locales for which resource bundles may be requested. These can be configured for a fallback chain, for which a custom fallback locale can be provided.

The localization configuration can be provided in the `manifest.json` file. It can either be configured using the `i18n` property in the `sap.app` section or in the `sap.ui5` section via the `models` configuration.

Sample configuration in `sap.ui5`:

``` json

{
    "sap.ui5": {
        "models": {
            "i18n": {
                "type": "sap.ui.model.resource.ResourceModel",
                "settings": {
                    "bundleName": "myapp.i18n.i18n"
                }
            }
        }
    }
}
...
```

In this example a resource model with identifier `"i18n"` and resource root bundle name `"myapp.i18n.i18n"` has been defined. This `bundleName` then resolves to a resource bundle root URL, e.g. `"myapp/i18n/i18n.properties"`. Depending on the locale fallback chain, locales are applied to the resource bundle root URL in order to load the specific bundles and the requested translation for text keys, e.g. `"myapp/i18n/i18n_de.properties"`.

***

<a name="loioec753bc539d748f689e3ac814e129563__section_FallbackChain"/>

### Locale Fallback Chain

The locales are resolved using a locale fallback chain. Each fallback is checked in the order of resolution. The locale fallback is used for loading resource bundles initially and when resolving texts.

1.  determine the input language, e.g. `"de_CH"`. For more information, see [Identifying the Language Code / Locale](Identifying_the_Language_Code__Locale_91f21f1.md).

2.  remove the region suffix from the locale code, e.g.`"de_CH"` -\> `"de"`

3.  use the `fallbackLocale` configured, e.g. `"en"` \(defaults to `"en"`\)

4.  use the raw bundle, e.g. `""`


-   input locale: `"de_CH"`

    ``` html
    "de_CH" -> "de" -> "en" -> ""
    ```

-   input locale: `"en_GB"`

    ``` html
    "en_GB" -> "en" -> ""
    ```


The fallback chain can be configured using a custom fallback locale and a list of supported locales.

***

<a name="loioec753bc539d748f689e3ac814e129563__section_SupportedLocales"/>

### Supported Locales and Fallback Locale

**Supported Locales** specifies a list of locales for which resource bundles may be requested. If this list is empty or not specified, all locales are supported.

The `supportedLocales` work like a filter. Each locale in the fallback chain is checked against this list and only applied if it is contained there.

The **Fallback Locale** specifies the custom fallback locale in the locale fallback chain. If not specified the `fallbackLocale` defaults to `en`.

Sample configuration in `sap.ui5`:

``` json

{
    "sap.ui5": {
        "models": {
            "i18n": {
                "type": "sap.ui.model.resource.ResourceModel",
                "settings": {
                    "bundleName": "myapp.i18n.i18n",
                    "supportedLocales": ["de", "en"],
                    "fallbackLocale": "de"
                }
            }
        }
    }
}
...
```

In this sample the locales `de` and `en` are supported. This means that the following two resource bundle files must exist:

-   `myapp/i18n/i18n_de.properties`

-   `myapp/i18n/i18n_en.properties`


The fallback locale `de` is applied if the current locale \(e.g. browser locale\) cannot be transformed to one of the `supportedLocales` \( `de` or `en`\) by removing the region postfix from the locale.

-   input locale: `"de_CH"`

    ``` html
    "de_CH" -> "de" (supported)
    ```

-   input locale: `"en_GB"`

    ``` html
    "en_GB" -> "en" (supported)
    ```

-   input locale: `"fr_FR"`

    ``` html
    "fr_FR" -> "fr" -> "de" (supported)
    ```


> ### Note:  
> To skip the custom fallback locale, the empty string `""` can be configured as `fallbackLocale`.
> 
> If specified, the `fallbackLocale` must be present in the list of `supportedLocales`.

