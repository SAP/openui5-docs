<!-- loio3cff5d0fa6754c0d9fdacd80653b81fb -->

| loio |
| -----|
| 3cff5d0fa6754c0d9fdacd80653b81fb |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/3cff5d0fa6754c0d9fdacd80653b81fb) | [demo kit latest release](https://sdk.openui5.org/topic/3cff5d0fa6754c0d9fdacd80653b81fb)</div>

## Programmatically Instantiating JS Fragments

For each fragment type, OpenUI5 provides a method that can be used to programmatically instantiate a fragment.

***

To give an example of a programmatic instantiation of a JS fragment, you first have to define one. The following code presents an example definition:

```js
// fragment is located in a file named: "my/useful/UiPartX.fragment.js"
sap.ui.define(["sap/m/Button"], function(Button) {
	return {
		createContent: function(oController) {
			var oButton  = new Button({
				text: "Hello World" ,
				press: oController.doSomething
			});
			return oButton;
		}
	};
});
```

This fragment can be instantiated from a controller as follows:

```js

const oMyButton = await this.loadFragment({
	name: "my.useful.UiPartX",
	type: "JS"
});
// oMyButton is now usable
```

This button can now be used as if it had been created in a standard way.

> ### Note:  
> The `await` operator can only be used inside an `async` function. Please be aware that there are certain limitations in OpenUI5 when using `async` functions as event handlers. For more information, see [ECMAScript Support](ECMAScript_Support_0cb44d7.md).

For fragments that are used several times, an ID for the fragment can be given optionally, see [Unique IDs](Unique_IDs_5da591c.md):

```js

const oMyButton = await this.loadFragment({
	name: "my.useful.UiPartX",
	id: "someId",
	type: "JS"
});
// oMyButton is now usable
```

JS Fragments are capable of asynchronously creating their content. To do so, the `createContent()` function must return a Promise instead of just regular controls. This Promise then must resolve with the actual content controls.

```js
// fragment is located in a file named: "reuse/SampleFragment.fragment.js"
sap.ui.define(["sap/ui/core/Fragment", "sap/m/Button", "heavy/work/SomeModule"], function(Fragment, Button, SomeModule) {
	return {
		createContent: async() => {
			return await SomeModule.doStuffAsync();
		}
	};
});
```

