<!-- loioc24ea6d4d2a34792a7ea241128ad8550 -->

| loio |
| -----|
| c24ea6d4d2a34792a7ea241128ad8550 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/c24ea6d4d2a34792a7ea241128ad8550) | [demo kit latest release](https://sdk.openui5.org/topic/c24ea6d4d2a34792a7ea241128ad8550)</div>

## Using Other Objects Instead of Controllers

For the instantiation of fragments, the oController object must not necessarily be a controller. It can also be another object.

***

The oController object given when instantiating a fragment does not need to be an object of type `sap.ui.core.mvc.Controller`. It is entirely up to the fragment what to expect from this object. This object is passed to the `createContent` method of JS fragments. In case of the declarative fragment types, that is XML, or HTML fragments, the event handler methods are searched on this object. This means that in most cases instead of a real controller object any JavaScript object could be given - provided it has the required methods.

The following example of an HTML fragment can be used in an environment where no MVC is used.

```js

var oDummyController = { 
	doSomething: function() { 
		// do whatever should happen when the button in the fragment is pushed...
	} 
};

// this specific fragment needs a controller and gets a dummy controller here. 
sap.ui.require(["sap/ui/core/Fragment"], function(Fragment){
    Fragment.load({
		name: "my.useful.UiPartZ",
        type: "HTML",
        controller: oDummyController
    }).then(function(oButton){
        // ...
    });
});
```

