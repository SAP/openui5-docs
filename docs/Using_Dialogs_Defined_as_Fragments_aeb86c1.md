<!-- loioaeb86c181b9742a2bf88049abf9ccb95 -->

| loio |
| -----|
| aeb86c181b9742a2bf88049abf9ccb95 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/aeb86c181b9742a2bf88049abf9ccb95) | [demo kit latest release](https://sdk.openui5.org/topic/aeb86c181b9742a2bf88049abf9ccb95)</div>

## Using Dialogs Defined as Fragments

The fragment instantiation function always returns the fragment's root control, which is a dialog control that can be used like any dialog.

***

In the following example, the dialog is opened immediately:

```js
// "this" has to be the controller instance of a controller extending module "sap/ui/core/mvc/Controller"
this.loadFragment({type: "XML", name: "testdata.fragments.XMLFragmentDialog"}).then(function(oDialog) {
	oDialog.open();
});
```

> ### Note:  
> Any global model and any models set on the controller's view are automatically available for data binding within this dialog. The fragment content is automatically added to the view's `dependents` aggregation. In consequence, the dialog is also automatically destroyed once the view is destroyed.

