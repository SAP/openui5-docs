<!-- loio91f385926f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f385926f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f385926f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f385926f4d1014b6dd926db0e91070)</div>

## Use of Localized Texts in Applications

OpenUI5 provides two options to use localized texts in applications: The `sap/base/i18n/ResourceBundle` module and data binding.

***

<a name="loio91f385926f4d1014b6dd926db0e91070__section_F5967527CABC49C78F6DCD1FC3182CC0"/>

### Using sap/base/i18n/ResourceBundle

You can use the JavaScript module `sap/base/i18n/ResourceBundle` to access localized texts. The module contains APIs to load a resource bundle file from a given URL and for a given locale.

You can then use the `ResourceBundle.create` function to load the resource bundle from the given URL that is the bundle name, and for a provided locale. When no locale is specified, the default locale \(en\) is used. The following code snippet shows the use of the `ResourceBundle.create` function to return a Promise which resolves with a `sap/base/i18n/ResourceBundle`:

``` js
// "ResourceBundle" required from module "sap/base/i18n/ResourceBundle"
ResourceBundle.create({
    url : sUrl, 
    locale: sLocale,
    async: true
}).then(function(oBundle) {
    // code
});
```

For more information, see `ResourceBundle` in the API Reference.

The resource bundle `sap/base/i18n/ResourceBundle` provides access to the localized texts that are contained in the resource bundle. You can use the `getText` method to access the texts in the loaded bundle by means of their key. This is shown in the following code snippet:

``` js
var sText = oBundle.getText(sKey);	
```

***

<a name="loio91f385926f4d1014b6dd926db0e91070__section_23DD4C90FA3C4AE5BCE18C17122444D4"/>

### Localization Test Page

The test suite provides a test page that shows how to use localized texts. This section only provides a short overview how the `sap/base/i18n/ResourceBundle` module is used there.

For a localized Web page you need the .html page itself and the .properties files of the required languages, in this example English and German.

The resource bundle `i18n.properties` is the English fallback version, which is the default version.

``` prefs
welcome=Welcome {0}. Please enter a new contact:
lastname=Last Name:
firstname=First Name:
street=Street:
zip=ZIP:
city=City:
```

The resource bundle `i18n_de.properties` contains the texts in German. The following code snippet shows the content of this file:

``` prefs
welcome=Willkommen {0}. Bitte geben Sie einen neuen Kontakt ein:
lastname=Nachname:
firstname=Vorname:
street=Straße:
zip=PLZ:
city=Ort:
```

The localization test page uses these texts to display a welcome message and a form to enter the address of a person. The coding of the test page looks as follows:

``` js
// "ResourceBundle" required from module "sap/base/i18n/ResourceBundle"
// "MatrixLayout" required from module "sap/ui/commons/layout/MatrixLayout"
// "Label" required from module "sap/ui/commons/Label"
// "TextField" required from module "sap/ui/commons/TextField"
// "TextView" required from module "sap/ui/commons/TextView"
var sLocale = sap.ui.getCore().getConfiguration().getLanguage();
ResourceBundle.create({url : "res/i18n.properties", locale: sLocale}).then(function(oBundle) {
    var oMatrixLayout = new MatrixLayout();
    oMatrixLayout.setLayoutFixed(false);
    oMatrixLayout.createRow(
      new TextView({text: oBundle.getText("welcome", ["Administrator"])}) 
    );
    oMatrixLayout.getRows()[0].getCells()[0].setColSpan(2);
    oMatrixLayout.createRow(
      new Label({text: oBundle.getText("lastname")}), 
      new TextField()
    );
    oMatrixLayout.createRow(
      new Label({text: oBundle.getText("firstname")}), 
      new TextField()
    );
    oMatrixLayout.createRow(
      new Label({text: oBundle.getText("street")}), 
    );
    oMatrixLayout.createRow(
      new Label({text: oBundle.getText("zip")}), 
      new TextField()
    );
    oMatrixLayout.createRow(
      new Label({text: oBundle.getText("city")}), 
      new TextField()
    );
    oMatrixLayout.placeAt("userForm");
});
```

With regard to localization, the code above defines the following procedure:

1.  Require the `sap/base/i18n/ResourceBundle` module
2.  Determine the language
3.  Load the resource bundle
4.  Access the text using the `welcome` key and pass the value for the placeholder \(`{0}`\) via an array
5.  Access the text using the `lastname` key and set it as text for the `Label`

***

<a name="loio91f385926f4d1014b6dd926db0e91070__section_1E0C902502BA455CA0C98A4365A367B3"/>

### Data Binding

You can also use data binding to access localized texts. The `ResourceModel` is a wrapper for resource bundles that exposes the localized texts as a model for data binding. You use the `ResourceModel` to bind texts for control properties to language dependent resource bundle properties. You can instantiate the `ResourceModel` either with `bundleName` \(name of a resource bundle that equals a OpenUI5 module name within the define/require concept\), or a `bundleUrl`, which points to a resource bundle. When you use the bundle name, make sure that the file has a `.properties` suffix. If no `locale` is defined, the current language is used.

> Note:
> ``` js
> // "ResourceModel" required from module "sap/ui/model/resource/ResourceModel"
> // "Button" required from module "sap/ui/commons/Button"
>  var oModel = new ResourceModel({
>    bundleName:"myBundle",
>    bundleLocale:"en",
>    async: true
>  });
>  var oControl = new Button({
>     id : "myButton",
>     text : "{i18n>MY_BUTTON_TEXT}"
> });
> // attach the resource model with the symbolic name "i18n"
> // The texts are resolved via databinding, once the resource bundle file was loaded
> oControl.setModel(oModel, "i18n");
> ```
> 
> 

> Note:
> The current data binding implementation does not allow to pass parameters to your texts in the resource bundle. If you have to pass parameters, you must do this on your own. You can, however, access the resource bundle directly from the model instead of loading it:
> 
> ``` js
> oModel.getResourceBundle().then(function(oBundleInstance) {
>     ...
> });
> ```
> 
> 

After the instance has been created, you have a model containing the resource bundle texts as data.

For a complete overview of available methods and parameters, see [`ResourceModel`](https://openui5.hana.ondemand.com/#docs/api/symbols/sap.ui.model.resource.ResourceModel.html) in the *API Reference* in the Demo Kit

**Related information**  


[Resource Model](Resource_Model_.md#loio91f122a36f4d1014b6dd926db0e91070)

