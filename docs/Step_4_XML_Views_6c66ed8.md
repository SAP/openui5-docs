<!-- loio6c66ed843c5e4b18aacf6c5e52246e4d -->

| loio |
| -----|
| 6c66ed843c5e4b18aacf6c5e52246e4d |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/6c66ed843c5e4b18aacf6c5e52246e4d) | [demo kit latest release](https://sdk.openui5.org/topic/6c66ed843c5e4b18aacf6c5e52246e4d)</div>

## Step 4: XML Views

Putting all our UI into the `index.js` file will very soon result in a messy setup, and there is quite a bit of work ahead of us. So let’s do a first modularization by putting the `sap/m/Text` control into a dedicated `view`.

OpenUI5 supports multiple view types \(XML, HTML, JavaScript\). When working with UI5, we recommend the use of XML, as this produces the most readable code and will force us to separate the view declaration from the controller logic. Yet the look of our UI will not change.

***

### Preview

  
  
**The "Hello World" text is now displayed by a OpenUI5 control \(No visual changes to last step\)**

![](images/loio05f6775a39d3409ea673f4acc3812142_LowRes.png "The "Hello World" text is now displayed by a OpenUI5 control (No
					visual changes to last step)")

***

<a name="loio6c66ed843c5e4b18aacf6c5e52246e4d__section_l3f_lgc_syb"/>

### Coding

You can view and download all files at [Walkthrough - Step 4](https://sdk.openui5.org/entity/sap.m.tutorial.walkthrough/sample/sap.m.tutorial.walkthrough.04).

***

<a name="loio6c66ed843c5e4b18aacf6c5e52246e4d__section_m3f_lgc_syb"/>

### webapp/view/App.view.xml \(New\)

```xml
<mvc:View
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
</mvc:View>
```

We create a new `view` folder in our webapp folder and a new file called `App.view.xml` inside this folder. The root node of the XML structure is the `view`. Here, we reference the default namespace `sap.m` where the majority of our UI assets are located. We define an additional `sap.ui.core.mvc` namespace with alias `mvc`, where the OpenUI5 views and all other Model-View-Controller \(MVC\) assets are located.

> ### Note:  
> The namespace identifies all resources of the project and has to be unique. If you develop your own application code or controls, you cannot use the namespace prefix `sap`, because this namespace is reserved for SAP resources. Instead, simply define your own unique namespace \(for example, `myCompany.myApp`\).

***

### webapp/view/App.view.xml

```xml
<mvc:View
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   <Text text="Hello World"/>
</mvc:View>

```

Inside the `View` tag, we add the declarative definition of our `text` control with the same properties as in the previous step. The XML tags are mapped to controls, and the attributes are mapped to control properties.

***

<a name="loio6c66ed843c5e4b18aacf6c5e52246e4d__section_nlq_g1w_xfb"/>

### webapp/index.js

```js
sap.ui.define([
	"sap/ui/core/mvc/XMLView"
], (XMLView) => {
	"use strict";

	XMLView.create({
		viewName: "ui5.walkthrough.view.App"
	}).then((oView) => oView.placeAt("content"));
});

```

We replace the instantiation of the `sap/m/Text` control by our new `App.view.xml` file. The view is created by a factory function of OpenUI5. The name is prefixed with the namespace `ui5.walkthrough.view` in order to uniquely identify this resource.

***

### Conventions

-   View names are capitalized

-   All views are stored in the `view` folder

-   Names of XML views always end with `*.view.xml`

-   The default XML namespace is `sap.m`

-   Other XML namespaces use the last part of the SAP namespace as alias \(for example, `mvc` for `sap.ui.core.mvc`\)


**Related Information**  


[Model View Controller \(MVC\)](Model_View_Controller_MVC_91f2334.md "The Model View Controller (MVC) concept is used in OpenUI5 to separate the representation of information from the user interaction. This separation facilitates development and the changing of parts independently.")

[Views](Views_91f27e3.md "The view in the Model-View-Controller (MVC) concept is responsible for defining and rendering the UI. OpenUI5 supports predefined view types.")

[XML View](XML_View_91f2928.md "The XML view type is defined in an XML file. The file name either ends with .view.xml or as an XML string. The file name and the folder structure together specify the name of the view that equals the OpenUI5 module name.")

