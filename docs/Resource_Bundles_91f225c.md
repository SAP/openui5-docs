<!-- loio91f225ce6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f225ce6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f225ce6f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f225ce6f4d1014b6dd926db0e91070)</div>

## Resource Bundles

A resource bundle file is a Java properties file \(as described in the Javadoc of class `java.util.Properties`\). It contains key-value pairs where the values are the language-dependent texts and the keys are language-independent and used by the application to identify and access the corresponding values.

Resource bundles are a collection of `*.properties` files. All files are named with the same base name \(prefix identifying the resource bundle\), an optional suffix that identifies the language contained in each file, and the fixed `.properties` extension. The language suffixes are formed according to the older JDK locale syntax. By convention, a file without a language suffix should exist and contain the raw untranslated texts in the developer's language. This file is used if no more suitable language can be found.

When a localized text is needed, the application uses the OpenUI5 APIs to load the properties file that matches the current language best. The same applies to any other localized data that can be represented as a string, for example, a date formatter string. To retrieve a text from the properties file, the application uses the \(language-independent\) key. If no text can be found for this key, the next best matching file is loaded and checked for the text. Finally, if no file matches, the raw file is loaded and checked.

> Note:
> The resource bundle `sap.ui.commons.message_bundle` consists of the following individual files:
> 
> -   `sap.ui.commons.message_bundle.properties`: Contains the raw texts form the developer, determines the set of keys
> -   `sap.ui.commons.message_bundle_en.properties`: Contains English texts \(without a specific country\)
> -   `sap.ui.commons.message_bundle_en_US.properties`: Contains texts in American English
> -   `sap.ui.commons.message_bundle_en_UK.properties`: Contains texts in British English
> -   `sap.ui.commons.message_bundle_de.properties`: Contains texts in German
> 
> 

To enable proper translation, you classify the texts with additional information, at least with the text type. Place the additional information in the line directly above the text element, beginning with the number sign \(\#\).

A `properties` file can, for example, look like this

``` prefs
# SAPUI5 TRANSLATION-KEY <GUID>
#XMSG: A message to greet the world
helloWorld=Hello World
#XBUT,10: Save button text
buttonSave=Save
#XFLD,30: Greetings displayed in the upper right corner of the screen
welcome=Welcome {0}

```

> Note:
> If you are using OpenUI5 in SAP HANA, resource bundles files must have the extension `*.hdbtextbundle` instead of `*.properties`.
> 
> To load this bundle, you add the following code to the `createContent` function of your view:
> 
> ``` js
> // "ResourceBundle" required from module "sap/base/i18n/ResourceBundle"
> // load the resource bundle
> var oBundle = ResourceBundle.create({
>   // specify url of the .hdbtextbundle
>   url : "i18n/messagebundle.hdbtextbundle"
> });
> ```
> 
> 

**Related information**  


[Resource Model](Resource_Model_.md#loio91f122a36f4d1014b6dd926db0e91070)

[API Reference: `sap.ui.model.resource.ResourceModel`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.resource.ResourceModel.html)

