<!-- loio0feb70c39c5e4074893c294667b3f36b -->

| loio |
| -----|
| 0feb70c39c5e4074893c294667b3f36b |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/0feb70c39c5e4074893c294667b3f36b) | [demo kit latest release](https://sdk.openui5.org/topic/0feb70c39c5e4074893c294667b3f36b)</div>

## Step 3: Controls \(TypeScript\)

Now it is time to build our first little UI by replacing the “Hello World” text in the HTML body by the OpenUI5 control `sap/m/Text`. In the beginning, we will use the TypeScript control API to set up the UI, the control instance is then placed into the HTML body.

***

### Preview

  
  
**The "Hello World" text is now displayed by a OpenUI5 control**

![Hello World](images/loio30a42d381b9e4388bf7fdc0b941e5381_LowRes.png "The "Hello World" text is now displayed by a OpenUI5
					control")

***

<a name="loio0feb70c39c5e4074893c294667b3f36b__section_ccm_jyv_xfb"/>

### Coding

You can view all files at [OpenUI5 TypeScript Walkthrough - Step 3: Controls](https://github.com/sap-samples/ui5-typescript-walkthrough/steps/03/README.md).

***

<a name="loio0feb70c39c5e4074893c294667b3f36b__section_yk4_kyv_xfb"/>

### webapp/package.json

First, we need to install `@types/openui5` to get the type definitions for OpenUI5. Open a terminal in the app root folder and execute the following command:

`npm install @types/openui5 --save-dev`

This will install the type definitions for OpenUI5 and update the `package.json` file with this new development dependency.

***

<a name="loio0feb70c39c5e4074893c294667b3f36b__section_rpg_y4q_nzb"/>

### webapp.index.ts

We then make some changes to our `index.ts` file: We remove the `alert` method and instantiate an OpenUI5 `Text` control instead; its options are passed to the constructor with a TypeScript object. For our control we set the `text` property to the value “Hello World”.

We chain the constructor call of the control to the standard `placeAt` method that is used to place OpenUI5 controls inside a node of the document object model \(DOM\) or any other OpenUI5 control instance. We pass the `content` ID as an argument.

```js
import Text from "sap/m/Text";

new Text({
    text: "Hello World"
}).placeAt("content");
```

Controls are used to define appearance and behavior of parts of the screen.

All controls of OpenUI5 have a fixed set of properties, aggregations, and associations for configuration. You can find their descriptions in the Demo Kit. In addition, each control comes with a set of public functions that you can look up in the API reference.

> ### Note:  
> Only instances of `sap.ui.core.Control` or their subclasses can be rendered stand-alone and have a `placeAt` function. Each control extends `sap.ui.core.Element` that can only be rendered inside controls. Check the API reference to learn more about the inheritance hierarchy of controls. The API documentation of each control refers to the directly known subclasses.

***

<a name="loio0feb70c39c5e4074893c294667b3f36b__section_dcm_jyv_xfb"/>

### webapp/index.html

We replace the `<div>` tags in our `webapp/index.html` file with a `<body>` tag and assign it the ID `content`. The body tag of the HTML document thus becomes the target node for the text control we defined in the `index.ts` script.

We also add the `sapUiBody` class, which provides additional theme-dependent styles.

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>UI5 TypeScript Walkthrough</title>
	<script
		id="sap-ui-bootstrap"
		src="resources/sap-ui-core.js"
		data-sap-ui-theme="sap_horizon"
		data-sap-ui-compatVersion="edge"
		data-sap-ui-async="true"
		data-sap-ui-onInit="module:ui5/walkthrough/index"
		data-sap-ui-resourceroots='{
			"ui5.walkthrough": "./"
		}'>
	</script>
</head>
<body class="sapUiBody" id="content">
</body>
</html>
```

In the example above, the callback of the `init` event is where we now instantiate an OpenUI5 text control.

***

<a name="loio0feb70c39c5e4074893c294667b3f36b__section_anl_htd_lzb"/>

### UI5 Tooling

As we now use the `sap.m` library with our app, we need to update our UI5 Tooling setup with a dependency to this library.

Open a terminal in the app root folder and execute the following command:

`ui5 add sap.m`

This will configure the `sap.m` OpenUI5 library as a dependency in our `ui5.yaml`.

**Parent topic:**[Walkthrough Tutorial \(TypeScript\)](Walkthrough_Tutorial_TypeScript_dad1905.md "In this tutorial we'll introduce you to all major development paradigms of OpenUI5. We'll demonstrate the use of TypeScript with OpenUI5 and highlight the specific characteristics of this approach.")

**Next:**[Step 2: Bootstrap \(TypeScript\)](Step_2_Bootstrap_TypeScript_32b14d8.md "Before we can do something with OpenUI5, we need to load and initialize it. This process of loading and initializing OpenUI5 is called bootstrapping. Once this bootstrapping is finished, we simply display an alert.")

**Previous:**[Step 4: XML Views \(TypeScript\)](Step_4_XML_Views_TypeScript_6c66ed8.md "Putting all our UI into the index.ts file will very soon result in a messy setup, and there is quite a bit of work ahead of us. So let’s do a first modularization by putting the sap/m/Text control into a dedicated view.")

**Related Information**  


[Working with Controls](Working_with_Controls_91f0a22.md "Controls are used to define the appearance and behavior of screen areas.")

[API Reference: `sap.m.Text`](https://sdk.openui5.org/api/sap.m.Text)

[Samples: `sap.m.Text` ](https://sdk.openui5.org/entity/sap.m.Text)

[API Reference: `sap.ui.core.Control`](https://sdk.openui5.org/api/sap.ui.core.Control)

[API Reference: `sap.ui.core.Element`](https://sdk.openui5.org/api/sap.ui.core.Element)

[API Reference: `sap.ui.base.ManagedObject`](https://sdk.openui5.org/api/sap.ui.base.ManagedObject)

[TypeScript Definitions for OpenUI5](https://www.npmjs.com/package/@types/openui5)

