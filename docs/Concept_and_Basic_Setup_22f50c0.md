<!-- loio22f50c0f0b104bf3ba84620880793d3f -->

| loio |
| -----|
| 22f50c0f0b104bf3ba84620880793d3f |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/22f50c0f0b104bf3ba84620880793d3f) | [demo kit latest release](https://sdk.openui5.org/topic/22f50c0f0b104bf3ba84620880793d3f)</div>

## Concept and Basic Setup

To a apply the Test Starter concept to your OpenUI5 project, you need to create a test suite and a generic test page which allows executing one or multiple test modules.

For OpenUI5 applications the test suite and the generic test page are typically placed in the `webapp/test` folder. The following code samples uses `<NAMESPACE>` as a placeholder for your OpenUI5 project namespace. Please, replace this placeholder with your OpenUI5 project namespace defined in the `sap.app/id` property in the `manifest.json` file by replacing the '.' with '/', for example `my/ui5app`.

***

<a name="loio22f50c0f0b104bf3ba84620880793d3f__section_v1s_4qg_vcc"/>

### The OpenUI5 Test Suite

An Test Suite configures the environment for the tests. A Test Suite consists of a `*.qunit.html` page often named `testsuite.qunit.htm`l and a corresponding `*.qunit.js` module often named`testsuite.qunit.js`.

***

#### The OpenUI5 Test Suite Page

The Test Suite page uses the `sap/ui/test/starter/createSuite.js` script to initialize the test suite in a CSP compliant way, based on the externalized test configuration provided in the Test Suite module.

```
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <base href="../">
    <title>QUnit test suite for NAMESPACE</title>
    <script
        src="resources/sap/ui/test/starter/createSuite.js"
        data-sap-ui-testsuite="test-resources/<NAMESPACE>/testsuite.qunit"
        data-sap-ui-resource-roots='{
            "test-resources.<NAMESPACE>": "./test"
        }'
    ></script>
</head>
<body>
</body>
</html>
```
```

***

***

#### The OpenUI5 Test Suite Module

The OpenUI5 Test Suite module represents the configuration file for the OpenUI5 Test Suite. The module must return a configuration object in the following structure:

```
```js
sap.ui.define(function() {
	"use strict";

	return {
		defaults: {
			page: "test/Test.qunit.html?testsuite={suite}&test={name}",
			qunit: {
				version: 2
			},
			sinon: {
				version: 4
			},
			ui5: {
				language: "EN",
				theme: "sap_horizon"
			},
			coverage: {
				only: "<NAMESPACE>/",
				never: "<NAMESPACE>/test/"
			},
			loader: {
				paths: {
					"<NAMESPACE>": "./"
				}
			}
		},
		tests: {}
	};
});
```

```

The `tests` object is empty for now. For more information on how to add add a defined test module to an existing test suite, see [Creating a QUnit Test](Creating_a_QUnit_Test_7080029.md).

***

<a name="loio22f50c0f0b104bf3ba84620880793d3f__section_gts_ptg_vcc"/>

### The Generic Test Page

The generic test page executes one or multiple test modules. Typically this file is named`test.qunit.html`. The generic test page is configured in the test suite module. It will be called with the test suite and test name in order to run a test.

```
```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<base href="../">
	<script
		src="resources/sap/ui/test/starter/runTest.js"
		data-sap-ui-resource-roots='{
			"test-resources.<NAMESPACE>": "./test"
		}'
	></script>
</head>
<body class="sapUiBody">
	<div id="qunit"></div>
	<div id="qunit-fixture"></div>
</body>
```
```

