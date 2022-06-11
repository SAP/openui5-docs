<!-- loio2edc3f99883e4a068f040d9e844f14fa -->

| loio |
| -----|
| 2edc3f99883e4a068f040d9e844f14fa |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/2edc3f99883e4a068f040d9e844f14fa) | [demo kit latest release](https://sdk.openui5.org/topic/2edc3f99883e4a068f040d9e844f14fa)</div>

## Localized Texts for Extended Apps

You can add custom localized text files that contain additional texts or texts that overwrite the original texts to the `sap.ui.model.resource.ResourceModel` 

The enhanced resource model tries to resolve the localized texts from the custom resource bundle first. If a text does not exist there, it tries to look up the text in the resource bundle of the original app. Custom resource bundles cannot be added by standard extension configuration, but must be added as part of a controller extension as shown in the following example:

```js

var oModel = new sap.ui.model.resource.ResourceModel({bundleUrl:"./testdata/messages.properties"});
oModel.enhance({bundleUrl:"./testdata/messages_custom.properties"});
```

