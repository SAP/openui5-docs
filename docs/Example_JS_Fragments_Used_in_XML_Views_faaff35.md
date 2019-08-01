<!-- loiofaaff35246414793b061f0244fb67338 -->

| loio |
| -----|
| faaff35246414793b061f0244fb67338 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/faaff35246414793b061f0244fb67338) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/faaff35246414793b061f0244fb67338)</div>

## Example: JS Fragments Used in XML Views

Example of a JS fragment used in an XML view

The example uses different combinations. Make sure that the `sap-ui-core.js` script location points to an existing OpenUI5 installation.

``` html
<!DOCTYPE html>
<html>
	<head>
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta content="charset=utf-8">
	
	<title>JSFragment used in XmlView</title>
	
	<!-- Load UI5, select theme and the "sap.m" control library -->
	<script id='sap-ui-bootstrap' type='text/javascript'
			src='/sapui5/resources/sap-ui-core.js'
			data-sap-ui-theme='sap_belize'
			data-sap-ui-libs='sap.m,sap.ui.layout'></script>
	
	
	<!-- DEFINE RE-USE COMPONENTS - NORMALLY DONE IN SEPARATE FILES -->
	
	<!-- define a JS Fragment - normally done in a separate file -->
	<script>
		// define a new (simple) View type
		// ...alternatively this can be done in an XML file without JavaScript!
		sap.ui.jsfragment("my.own.frag", {
			
			// defines the UI of this View
			createContent: function() {
				// button text is bound to Model, "press" action is bound to Controller's event handler
				return [ 
					new sap.m.Button({text:'my Fragment Button'}),
					new sap.m.Button(this.createId("btn2"), {text:'my second Fragment Button'}) 
				]
			}
		});
	</script>
	
	
	<!-- define an XMLView - normally done in a separate file -->
	<script id="view1" type="sapui5/xmlview">
		<mvc:View xmlns:core="sap.ui.core" xmlns:layout="sap.ui.layout" xmlns:mvc="sap.ui.core.mvc" xmlns="sap.m"
				controllerName="my.own.controller" xmlns:html="http://www.w3.org/1999/xhtml">
			<layout:VerticalLayout id="vl">
				<Button text="Find controls by ID" press="findControls"></Button>
				<Text text="Fragment referenced inline, no Fragment ID:" />
				<core:Fragment fragmentName='my.own.frag' type='JS' />
				<Text text="Fragment referenced inline, with Fragment ID 'myFrag':" />
				<core:Fragment id="myFrag" fragmentName='my.own.frag' type='JS' />
			</layout:VerticalLayout>
		</mvc:View> 
	</script>
	
	
	<script>
		// define a new (simple) Controller type
		sap.ui.controller("my.own.controller", {
			
			// implement an event handler in the Controller
			findControls: function() {
				// Fragment is instantiated within an XMLView => all GIVEN IDs are prefixed with the 
				// View ID and View.byId() needs to be used to find the controls
				var b1 = null; // ID is generated: "__button1"
				var b2 = this.byId("btn2"); // Button ID is given, Fragment has no ID: "myView--btn2"
				var b3 = null // Fragment has an ID, but Control ID is generated and hence not prefixed: "__button2"
				var b4 = this.byId(sap.ui.core.Fragment.createId("myFrag", "btn2")); // Button and Fragment ID are given, let the Fragment construct the prefixed ID and then let the View search the again prefixed ID
				alert("Controls in Fragment:\nButton 1: has no given ID, cannot be found\nButton 2: " + b2 + "\nButton 3: has no given ID, cannot be found\nButton 4: " + b4);
			}
		});
		
		
		
		/*** THIS IS THE "APPLICATION" CODE ***/
		
		// instantiate the View
		var myView = sap.ui.xmlview("myView", {viewContent:jQuery('#view1').html()}); // accessing the HTML inside the script tag above
		
		// put the View onto the screen
		myView.placeAt('content');
		
		
	</script>
	
	</head>
	<body class='sapUiBody'>
		<div id='content'></div>
	</body>
</html>
```

