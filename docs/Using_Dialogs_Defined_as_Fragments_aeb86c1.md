<!-- loioaeb86c181b9742a2bf88049abf9ccb95 -->

| loio |
| -----|
| aeb86c181b9742a2bf88049abf9ccb95 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/aeb86c181b9742a2bf88049abf9ccb95) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/aeb86c181b9742a2bf88049abf9ccb95)</div>

## Using Dialogs Defined as Fragments

The fragment instantiation function always returns the fragment's root control, which is a dialog control that can be used like any dialog.

***

In the following example, the dialog is opened immediately:

``` js
// "Fragment" required from module "sap/ui/core/Fragment"
Fragment.load({type: "XML", name: "testdata.fragments.XMLFragmentDialog"}).then(function(oDialog) {
	oDialog.open();
});
```

Note that any global model is available for data binding within this dialog. Also any model set on the dialog itself. However, if this dialog is opened from a controller, the model of this controller's view is NOT automatically available within the dialog fragment. The reason for this is that the dialog is not part of the view UI. If the above code for opening the fragment dialog is part of a controller, it could set the view's model on the dialog:

``` js
// "Fragment" required from module "sap/ui/core/Fragment"
Fragment.load({type: "XML", name: "testdata.fragments.XMLFragmentDialog"}).then(function(oDialog) {
	oDialog.setModel(this.getView().getModel());
	oDialog.open();
});
```

Alternatively, the special aggregation `dependents` of `sap.ui.core.Element` can be used to connect the dialog to the lifecycle management and data binding of the view:

``` js
// "Fragment" required from module "sap/ui/core/Fragment"
Fragment.load({type: "XML", name: "testdata.fragments.XMLFragmentDialog"}).then(function(oDialog) {
	this.getView().addDependent(oDialog);
	oDialog.open();
});
```

