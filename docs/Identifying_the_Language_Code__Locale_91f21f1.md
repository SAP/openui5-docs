<!-- loio91f21f176f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f21f176f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f21f176f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f21f176f4d1014b6dd926db0e91070)</div>

## Identifying the Language Code / Locale

For the identification of languages, the framework uses a language code of type `string`.

The language can be set, for example, by using the following options:

-   URL parameter `sap-ui-language` and configuration parameter `language`

-   Script tag attribute `data-sap-ui-language`

-   Global configuration variable `window["sap-ui-config"].language`

-   URL parameter `sap-language`


These OpenUI5 configuration options accept the following formats:

-   Language codes according to the de facto standard BCP-47, which are used by most browsers for language identification

    As of JDK 1.7 they are also supported by the Java locale class. Examples are `de`, `en-US`, `zh-Hans-CN`.

-   Java locale syntax that combines a lower case ISO 639 alpha-2 or alpha-3 language code with an ISO 3166 alpha-2 country code

    Both codes are combined with an underscore. An arbitrary sequence of variant identifiers \(also separated by underscores\) can be appended as a third component. Examples are `de`, `en_US`, `zh_TW_Traditional` 

-   SAP proprietary language codes \(only supported by URL parameter `sap-language`\)

    OpenUI5 applications are often used to connect to ABAP-based SAP application servers. These servers use SAP proprietary language codes for compatibility reasons. These language codes often match an ISO 639 alpha-2 language code, but not in all cases. If the language code for an OpenUI5 application is specified with the URL parameter `sap-language`, OpenUI5 assumes that it is an SAP proprietary language code and converts it to a BCP-47 language tag as follows:

    |SAP Language Code|BCP47 Language Tag|Description|
    |-----------------|------------------|-----------|
    |`ZH`|`zh-Hans`|`ZH` is the SAP language code for Simplified Chinese. The most generic representation in BCP47 is `zh-Hans`. `zh-CN` \(Chinese, China\) is another representation, but SAPUI5 decided to use `zh-Hans`.|
    |`ZF`|`zh-Hant`|`ZF` is the SAP language code for Traditional Chinese. The most generic representation in BCP47 is `zh-Hant`. `zh-TW` \(Chinese, Taiwan\) is another representation, but SAPUI5 decided to use `zh-Hant`.|
    |`1Q`|`en-US-x-saptrc`|`1Q` is a technical SAP language code used in support scenarios, for example for translation issues. When you select this language code, the technical keys are display instead of the actual data. As no ISO639 code for this exists, the information has been added as a BCP47 private extension to the `en-US` language tag: "trc" stands for "trace" or "traceability".|
    |`2Q`|`en-US-x-sappsd`|`2Q` is also used as a technical SAP language code in support scenarios and displays a pseudo translation \("psd" in the private extensions name\).|

    > Note:
    > Only these SAP-proprietary language codes are understood by OpenUI5. Other SAP-proprietary language codes are not automatically transformed. If you develop your app to run in the SAP Fiori launchpad, all other SAP-proprietary language codes are handled by the SAP Fiori launchpad.
    > 
    > If you don't make use of the SAP Fiori launchpad, you may have to explicitly implement the language handling. You can use the `sap.ui.getCore().setLanguage()` method to provide both settings, a BCP47 language code and the corresponding SAP-proprietary language\) in one call. OpenUI5 will then use one of the two codes where appropriate \(e.g. BCP47 for the retrieval of translated texts or in HTTP Accept Headers, but the proprietary SAP language code when propagating the `sap-language` URL parameter to an OData service\).
    > 
    > 


***

<a name="loio91f21f176f4d1014b6dd926db0e91070__section_6CAF7D95C27C487CB201CE83345AC370"/>

### Current Language Code / Locale

OpenUI5 has the notion of a current language. It is determined during the OpenUI5 bootstrap from the following sources of information. The sources are ordered increasingly by priority and the last available user language/locale wins:

1.  Hard-coded OpenUI5 default locale `en`

2.  Potentially configured browser language \(`window.navigator.browserLanguage`\); for Internet Explorer this is the language of the operating system

3.  Potentially configured user language \(`window.navigator.userLanguage`\); for Internet Explorer this is the language in the region settings

4.  General language information from the browser \(`window.navigator.language`\)

5.  Android: Language contained in the user agent string \(`window.navigator.userAgent`\)

6.  First language from the list of the user’s preferred languages \(`window.navigator.languages[0]`\) \(For more information, see [https://developer.mozilla.org](https://developer.mozilla.org/en/docs/Web/API/NavigatorLanguage/languages).\)

7.  Locale configured in the application coding \(For more information, see [API Reference: `sap.ui.core.Configuration`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.core.Configuration.html). \)

8.  Locale configured via URL parameters


After the bootstrap, the language can be changed by calling `sap.ui.getCore().setLanguage(…)`. A call to this method does not guarantee that all already existing translatable texts will be adapted. You use the configuration API to retrieve the resulting current language as follows:

``` js

var sCurrentLocale = sap.ui.getCore().getConfiguration().getLanguage();
```

For more information, see [API Reference: `sap.ui.core.Configuration.setLanguage`](https://openui5.hana.ondemand.com/#/api/sap.ui.core.Configuration/methods/setLanguage).

> Note:
> The syntax of the returned value depends on the syntax used for configuration. If the information source is one of the browser language properties, the returned language most likely is in BCP-47 format. If it is configured as a URL parameter, the user might have choosen the JDK Locale syntax.
> 
> 

> Note:
> None of the `window.navigator.*` properties in Internet Explorer \(IE\) reflect the settings of the **Language Preference** dialog. Instead, IE returns the language of the Operating System installation as `browserLanguage` and the language from the Operating System regional settings as `userLanguage`. As a result, the settings in the **Language Preference** dialog **cannot** be used for the current language of OpenUI5. This is often confusing for developers and a known shortcoming in IE. To circumvent this, an additional server request could be used where IE provides the corresponding setting in the`Accept-Language` header. This server request, however, requires a backend component. OpenUI5 must be able to run without a server component and, thus, the server request is not implemented.
> 
> 

