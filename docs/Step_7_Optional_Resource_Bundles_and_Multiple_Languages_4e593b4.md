<!-- loio4e593b44e78a431e8b21be6b3915fb55 -->

| loio |
| -----|
| 4e593b44e78a431e8b21be6b3915fb55 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/4e593b44e78a431e8b21be6b3915fb55) | [demo kit latest release](https://sdk.openui5.org/topic/4e593b44e78a431e8b21be6b3915fb55)</div>

## Step 7: \(Optional\) Resource Bundles and Multiple Languages

The reason we have resource bundles is to allow an app to run in multiple languages without the need to change any code. To demonstrate this feature, we will create a German version of the app – in fact all we need to do is create a German version of the resource bundle file. In our code, the German locale needs to be activated for the ResourceModel.

***

### Preview

  
  
**German version of our UI**

![](images/loiod96cdf993b9f4344822d61d2a81d11ab_LowRes.png "German version of our UI")

***

### Coding

You can view and download all files in the Demo Kit at [Data Binding - Step 7](https://sdk.openui5.org/entity/sap.ui.core.tutorial.databinding/sample/sap.ui.core.tutorial.databinding.07).

***

<a name="loio4e593b44e78a431e8b21be6b3915fb55__section_stj_zdp_2mb"/>

### webapp/i18n/i18n\_de.properties \(New\)

In the `i18n` folder, make a copy of the file `i18n.properties` and call it <code>i18n<b>_de</b>.properties</code>. Change the English text to the German text shown below. The suffix `de` is the locale for German language. As the locale `de` is already set in the `supportedLocales` configuration of the `manifest.json`, it will be taken into account.

```ini
# Field labels
firstName=Vorname
lastName=Nachname
enabled=Aktiviert

# Screen titles
panelHeaderText=Data Binding Grundlagen
```

To test the outcome, append the `sap-language=DE` URL parameter to the URL in your browser, e.g. `http://localhost:port/index.html?sap-language=DE`. Once you remove this parameter, your app will be displayed in your browser's default language again.

**Parent topic:**[Data Binding Tutorial](Data_Binding_Tutorial_e531093.md "In this tutorial, we will explain the concepts of data binding in OpenUI5.")

**Next:**[Step 6: Resource Models](Step_6_Resource_Models_9790d9a.md "Business applications also require language-specific (translatable) texts used as labels and descriptions on the user interface.")

**Previous:**[Step 8: Binding Paths: Accessing Properties in Hierarchically Structured Models](Step_8_Binding_Paths_Accessing_Properties_in_Hierarchically_Structured_Models_9373793.md "In step 6 , we stated that the fields in a resource model are arranged in a flat structure; in other words, there can be no hierarchy of properties; however, this is true only for resource models. The properties within JSON and OData models almost always are arranged in a hierarchical structure. Therefore, we should take a look at how to reference fields in a hierarchically structured model object.")

**Related Information**  


[Localization](Localization_91f217c.md "The framework concepts for text localization in OpenUI5 are aligned with the general concepts of the Java platform.")

