<!-- loio32b14d88bd484cd7b941aae37180f732 -->

| loio |
| -----|
| 32b14d88bd484cd7b941aae37180f732 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/32b14d88bd484cd7b941aae37180f732) | [demo kit latest release](https://sdk.openui5.org/topic/32b14d88bd484cd7b941aae37180f732)</div>

## Step 2: Bootstrap \(TypeScript\)

Before we can do something with OpenUI5, we need to load and initialize it. This process of loading and initializing OpenUI5 is called **bootstrapping**. Once this bootstrapping is finished, we simply display an alert.

***

### Preview

  
  
**An alert "UI5 is ready" is displayed**

![](images/loio0f6b6b9dc46a474da9287c382c8d3456_LowRes.png "An alert "UI5 is ready" is displayed")

***

### Coding

You can view and download all files at [Walkthrough - Step 2](https://github.com/sap-samples/).

***

<a name="loio32b14d88bd484cd7b941aae37180f732__section_mkm_zwb_syb"/>

### package.json

As we'd like to use TypeScript with our project, we first need to install the TypeScript package. It provides the necessary tools and utilities to compile TypeScript code into JavaScript.

Open a terminal in the app root folder and execute `npm install typescript --save-dev` to install the latest stable version of TypeScript to your project and to add it as development dependency to your `package.json`.

***

<a name="loio32b14d88bd484cd7b941aae37180f732__section_fy4_zjy_kzb"/>

### tsconfig.json \(New\)

Let's create the file `tsconfig.json` in the app root folder to indicate that the folder is the root of a TypeScript project. This file specifies the root files and the compiler options required to compile the project.

Specify them as follows:

```
{
    "compilerOptions": {
      "target": "es2022",
      "module": "es2022",
      "moduleResolution": "node",
      "skipLibCheck": true,
      "allowJs": true,
      "strict": true,
      "strictPropertyInitialization": false,
      "rootDir": "webapp",
      "baseUrl": "./",
      "paths": {
        "ui5/walkthrough/*": ["webapp/*"]
      }
    },
    "include": ["webapp/**/*"]
  }
```

***

<a name="loio32b14d88bd484cd7b941aae37180f732__section_r5p_fky_kzb"/>

### webapp/index.ts \(New\)

Create a new `index.ts` script in the webapp folder and add a native `alert()` method with the message "UI5 is ready" to it. We'll integrate this script to the `index.html` page next.

```js
alert("UI5 is ready");
```

***

### webapp/index.html

In this step, we change the `index.html` page to make it load the OpenUI5 framework from the webserver provided by UI5 Tooling. We initialize the core modules with the following configuration options:

-   The `id` attribute of the `<script>` tag has to be exactly `"sap-ui-bootstrap"` to ensure proper booting of the OpenUI5 runtime.
-   The `src` attribute of the `<script>` tag tells the browser where to find the OpenUI5 core library – it initializes the OpenUI5 runtime and loads additional resources, such as the libraries specified in the `data-sap-ui-libs` attribute.

-   The OpenUI5 controls support different themes. We choose `sap_horizon` as our default theme.

-   To make use of the most recent functionality of OpenUI5 we define the compatibility version as `edge`.

-   We configure the bootstrapping process to run asynchronously. This means that the OpenUI5 resources can be loaded simultaneously in the background for performance reasons.

-   We define the module to be loaded initially in a declarative way. With this, we avoid directly executable JavaScript code in the HTML file. This makes your app more secure. We'll create the script that this refers to further down in this step.
-   We tell OpenUI5 core that resources in the `ui5.walkthrough` namespace are located in the same folder as `index.html`.


```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>UI5 Walkthrough</title>
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
<body>
	<div>Hello World</div>
</body>
</html>
```

***

<a name="loio32b14d88bd484cd7b941aae37180f732__section_ks2_1bv_xfb"/>

### package.json

Now it's time to enhance our tooling setup once again. This time we install some custom middleware for the ui5-server to facilitate the handling of our development project.

Open a terminal in the app root folder. Then execute the following command:

`npm install ui5-middleware-livereload ui5-middleware-serveframework ui5-tooling-transpile --save-dev`

This will install the `ui5-middleware-livereload`, `ui5-middleware-serveframework`, and `ui5-tooling-transpile` tooling extensions and add them as development dependencies to your `package.json`:

-   `ui5-middleware-livereload` is a middleware for ui5-server which triggers a live reload whenever files inside your directory change, e.g. upon *Save*.
-   `ui5-middleware-serveframework` is a middleware for ui5-server which delivers the UI5 framework from a locally built version.
-   `ui5-tooling-transpile` provides a middleware and a task which transpiles TypeScript code to ES5 using the Babel transpiler. The middleware transpiles a matching `.ts` file on the fly. The task transpiles the relevant source files during the UI5 Tooling build process.

***

<a name="loio32b14d88bd484cd7b941aae37180f732__section_hhn_jky_kzb"/>

### ui5.yaml

For our UI5 Tooling setup we require some additional configuration changes:

1.  Open a terminal in the app root folder.

2.  Execute the `ui5 use OpenUI5` command to configure the latest OpenUI5 version in your UI5 Tooling setup.
3.  Execute the `ui5 add sap.ui.core themelib_sap_horizon` command. This will add the `sap.ui.core` and `themelib_sap_horizon` libraries as dependencies to your `ui5.yaml` file.

Next, we have to configure the tooling extensions we installed from npm in our UI5 Tooling setup, so we can use them in our project. To hook a custom task into a certain build phase of a project, it needs to reference another task that will get executed before or after it. The same applies for a custom middleware:

-   For the `ui5-tooling-transpile-task` we specify that this should happen after the`replaceVersion` task.
-   All our custom middleware extensions will be called after the `compression` middleware.

> ### Note:  
> Middleware configurations are applied in the order in which they are defined.

```
framework:
  name: OpenUI5
  version: "1.119.1"
  libraries:
    - name: sap.ui.core
    - name: themelib_sap_horizon
builder:
  customTasks:
  - name: ui5-tooling-transpile-task
    afterTask: replaceVersion
server:
  customMiddleware:
  - name: ui5-tooling-transpile-middleware
    afterMiddleware: compression
  - name: ui5-middleware-serveframework
    afterMiddleware: compression
  - name: ui5-middleware-livereload
    afterMiddleware: compression
```

Now you can benefit from live reload on changes, built framework resources at development time, and make use of TypeScript in UI5!

> ### Note:  
> During its initial run, the `ui5-middleware-serveframework` middleware will build the framework, which can take a while. In all following steps, the build will not happen again and the framework is served from the built resources.

**Related Information**  


[What is a tsconfig.json?](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)

[Compatibility Version Information](Compatibility_Version_Information_9feb96d.md "Compatibility version flags allow applications to react to incompatible changes in OpenUI5.")

[Bootstrapping: Loading and Initializing](Bootstrapping_Loading_and_Initializing_a04b0d1.md "To use OpenUI5 features in your HTML page, you have to load and initialize the SAPUI5 library.")

[Content Security Policy](Content_Security_Policy_fe1a6db.md "Content Security Policy (CSP) adds an additional layer of security that can detect and mitigate certain types of attacks, such as cross-site scripting and data injection.")

[UI5 Tooling: Consuming OpenUI5 Libaries](https://sap.github.io/ui5-tooling/v3/pages/OpenUI5/)

[NPM Package: `ui5-middleware-livereload`](https://www.npmjs.com/package/ui5-middleware-livereload)

[NPM Package: `ui5-middleware-serverframework`](https://www.npmjs.com/package/ui5-middleware-serveframework)

[NPM Package: `ui5-tooling-transpile`](https://www.npmjs.com/package/ui5-tooling-transpile)

[UI5 Tooling: Custom Tasks](https://sap.github.io/ui5-tooling/v3/pages/extensibility/CustomTasks/)

[UI5 Tooling: Custom Server Middleware](https://sap.github.io/ui5-tooling/v3/pages/extensibility/CustomServerMiddleware/)

