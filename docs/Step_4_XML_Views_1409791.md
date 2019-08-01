<!-- loio1409791afe4747319a3b23a1e2fc7064 -->

| loio |
| -----|
| 1409791afe4747319a3b23a1e2fc7064 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/1409791afe4747319a3b23a1e2fc7064) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/1409791afe4747319a3b23a1e2fc7064)</div>

## Step 4: XML Views

Putting all our UI into the `index.html` file will very soon result in a messy setup and there is quite a bit of work ahead of us. So let’s do a first modularization by putting the `sap.m.Text` control into a dedicated `view`.

OpenUI5 supports multiple view types \(XML, HTML, JavaScript\). We choose XML as this produces the most readable code and will force us to separate the view declaration from the controller logic. Yet the look of our UI will not change.

***

### Preview

   
  
The "Hello World" text is now displayed by a OpenUI5 control \(No visual changes to last step\)<a name="loio1409791afe4747319a3b23a1e2fc7064__fig_r1j_pst_mr"/>

 ![](loioc1d7d89b92c14f7ea88af6771d962f72_HiRes.png "The "Hello World" text is now displayed by a OpenUI5 control (No
					visual changes to last step)") 

***

### Coding

You can view and download all files at [Walkthrough - Step 4](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.04/preview).

``` xml
<mvc:View
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
</mvc:View>
```

We create a new `view` folder in our app and a new file for our XML view inside the `app` folder. The root node of the XML structure is the `view`. Here, we reference the default namespace `sap.m` where the majority of our UI assets are located. We define an additional `sap.ui.core.mvc` namespace with alias `mvc`, where the OpenUI5 views and all other Model-View-Controller \(MVC\) assets are located.

> Note:
> The namespace identifies all resources of the project and has to be unique. If you develop your own application code or controls, you cannot use the namespace prefix `sap`, because this namespace is reserved for SAP resources. Instead, simply define your own unique namespace \(for example, `myCompany.myApp`\).
> 
> 

***

### webapp/view/App.view.xml

``` xml
<mvc:View
   xmlns="sap.m"
   xmlns:mvc="sap.ui.core.mvc">
   *HIGHLIGHT START*<Text text="Hello World"/>*HIGHLIGHT END*
</mvc:View>

```

Inside the `view` tag, we add the declarative definition of our `text` control with the same properties as in the previous step. The XML tags are mapped to controls and the attributes are mapped to the properties of the control.

***

<a name="loio1409791afe4747319a3b23a1e2fc7064__section_nlq_g1w_xfb"/>

### webapp/index.js

``` js
sap.ui.define([
*HIGHLIGHT START*	"sap/ui/core/mvc/XMLView"*HIGHLIGHT END*
], function (*HIGHLIGHT START*XMLView*HIGHLIGHT END*) {
	"use strict";

*HIGHLIGHT START*	XMLView.create({
		viewName: "sap.ui.demo.walkthrough.view.App"
	}).then(function (oView) {
		oView.placeAt("content");
	});
*HIGHLIGHT END*
});

```

We replace the instantiation of the `sap.m.Text` control by our new `App` XML view. The view is created by a factory function of OpenUI5 which makes sure that the view is correctly configured and can be extended by customers. The name is prefixed with the namespace `sap.ui.demo.walkthrough.view` in order to uniquely identify this resource.

> Note:
> From this step onwards, it is necessary to run the app on a Web server. We structure the app with multiple files that are loaded from the local file system. Without a Web server, this is prevented by the browser due to security reasons. If the error message "sap is not defined" appears in the developer tools of the browser, you need to check the `resource` path in the bootstrap.
> 
> You can find more information about how to install a Web server for your particular environment at [Development Environment](Development_Environment_7bb04e0.md).
> 
> 

***

### Conventions

-   View names are capitalized

-   All views are stored in the `view` folder

-   Names of XML views always end with `*.view.xml`

-   The default XML namespace is `sap.m`

-   Other XML namespaces use the last part of the SAP namespace as alias \(for example, `mvc` for `sap.ui.core.mvc`\)


**Related information**  


[Model View Controller \(MVC\)](Model_View_Controller_(MVC)_91f2334.md)

[Views](Views_91f27e3.md)

[XML View](XML_View_91f2928.md)

