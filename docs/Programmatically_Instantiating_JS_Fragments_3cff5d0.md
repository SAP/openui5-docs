<!-- loio3cff5d0fa6754c0d9fdacd80653b81fb -->

| loio |
| -----|
| 3cff5d0fa6754c0d9fdacd80653b81fb |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3cff5d0fa6754c0d9fdacd80653b81fb) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3cff5d0fa6754c0d9fdacd80653b81fb)</div>

## Programmatically Instantiating JS Fragments

For each fragment type, OpenUI5 provides a method that can be used to programmatically instantiate a fragment.

***

To give an example of a programmatic instantiation of a JS fragment, you first have to define one. The following code presents an example definition:

``` js
sap.ui.jsfragment ( "my.useful.UiPartX",{ 
	createContent: function (oController ) {
        var oButton  = new sap.m.Button({ 
			text: "Hello World" , 
			press:oController.doSomething 
		}); 
		return oButton; 
	} 
});
```

This fragment can be instantiated from a controller as follows:

``` js

var myButton = sap.ui.jsfragment("my.useful.UiPartX",this); // assuming "this" is the controller
```

This button can now be used as if it had been created in a standard way. Note how a controller instance is passed as second parameter. This is required because that particular fragment tries to bind the button press handler to the method **doSomething** in the given controller. With no controller given, this would cause an error.

For fragments that are used several times, an ID for the fragment can be given optionally, see [Unique IDs](Unique_IDs_5da591c.md):

``` js

var myButton = sap.ui.jsfragment("someId", "my.useful.UiPartX", this); // assuming "this" is the Controller
```

Within a JS view's **createContent\(\)** method the fragment content could be included like this:

``` js
... 
	createContent: function (oController ) {
		var hLayout = new sap.m.HBox (); 
		...
		var myFragment = sap.ui.jsfragment( "my.useful.UiPartX" , oController ); 
		// here the fragment is instantiated       
		hLayout.addContent (myFragment ); 
		... 
		return hLayout ; 
	} 
...
```

The fragment content \(= the button\) would be added to the layout which is the content of this JSView. Other fragments not requiring a controller can of course be instantiated without passing a controller. But it also does not hurt to pass the controller - it is only used for setting up the event handlers \(or within the **createContent\(\)** method, in case of JS fragments\).

