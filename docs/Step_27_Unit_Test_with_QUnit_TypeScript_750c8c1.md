<!-- loio750c8c1e2ec1479ea58a4aaf9ee2ab82 -->

| loio |
| -----|
| 750c8c1e2ec1479ea58a4aaf9ee2ab82 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/750c8c1e2ec1479ea58a4aaf9ee2ab82) | [demo kit latest release](https://sdk.openui5.org/topic/750c8c1e2ec1479ea58a4aaf9ee2ab82)</div>

## Step 27: Unit Test with QUnit \(TypeScript\)

Now that we have a test folder in the app, we can start to increase our test coverage.

Actually, every feature that we added to the app so far, would require a separate test case. We have totally neglected this so far, so let’s add a simple unit test for our custom formatter function from Step 22. We will test if the long text for our status is correct by comparing it with the texts from our resource bundle.

> ### Note:  
> In this tutorial, we focus on a simple use case for the test implementation. If you want to learn more about QUnit tests, have a look at our [Testing Tutorial](Testing_Tutorial_291c912.md) tutorial, especially [Step 2: A First Unit Test](Step_2_A_First_Unit_Test_b81736e.md).

***

### Preview

  
  
**A unit test for our formatters is now available**

![Preview of the unit test](images/loio0d29491d96574cfe8d8158d60a0a32e2_LowRes.png "A unit test for our formatters is now available")

***

### Coding

You can view all files at [OpenUI5 TypeScript Walkthrough - Step 27: Unit Test with QUnit](https://github.com/sap-samples/ui5-typescript-walkthrough/tree/main/steps/27) and [download the solution as a zip file](https://sap-samples.github.io/ui5-typescript-walkthrough/ui5-typescript-walkthrough-step-27.zip).

  
  
**Folder Structure for this Step**

![The graphic has an explanatory text](images/loioeae0f42249494ae7aeda044e83f15097_LowRes.png "Folder Structure for this Step")

We add a new folder `unit` under the `test` folder and a `model` subfolder where we will place our formatter unit test. The folder structure matches the app structure to easily find the corresponding unit tests.

***

### webapp/test/unit/model/formatter.ts \(New\)

We create a new `formatter.ts` file under `webapp/test/unit/model` where the unit test for the custom formatter is implemented. The `formatter` function that we want to test is from the `formatter.ts` file located in the `webapp/model` folder.

The new formatter file just contains one QUnit module for our formatter function and one unit test for the formatter function. In the implementation of the `statusText` function that we created in Step 22, we use the translated texts when calling the formatter. As we do not want to test the OpenUI5 binding functionality, we just use text in the test instead of a `ResourceBundle`.

Finally, we perform our assertions. We check each branch of the formatter logic by invoking the isolated formatter function with the values that we expect in the data model \(`A`, `B`, `C`, and everything else\). We strictly compare the result of the formatter function with the hard-coded strings that we expect from the resource bundle and give a meaningful error message if the test should fail.

```js
import ResourceModel from "sap/ui/model/resource/ResourceModel";
import Controller from "sap/ui/core/mvc/Controller";
import formatter from "../../../model/formatter";

QUnit.module("Formatting function", {});

QUnit.test("Should return the translated texts", (assert) => {
    const resourceModel = new ResourceModel({
        bundleUrl: sap.ui.require.toUrl("ui5/walkthrough/i18n/i18n.properties"),
        supportedLocales: [
            ""
        ],
        fallbackLocale: ""
    });

    const controllerMock = {
        getOwnerComponent() {
            return {
                getModel() {
                    return resourceModel;
                }
            };
        }
    } as any as Controller;

    // System under test
    const fnIsolatedFormatter = formatter.statusText.bind(controllerMock);

    // Assert
    assert.strictEqual(fnIsolatedFormatter("A"), "New", "The long text for status A is correct");
    assert.strictEqual(fnIsolatedFormatter("B"), "In Progress", "The long text for status B is correct");
    assert.strictEqual(fnIsolatedFormatter("C"), "Done", "The long text for status C is correct");
    assert.strictEqual(fnIsolatedFormatter("Foo"), "Foo", "The long text for status Foo is correct");
});
```

***

<a name="loio750c8c1e2ec1479ea58a4aaf9ee2ab82__section_hnt_54c_yfb"/>

### webapp/test/unit/unitTests.qunit.ts \(New\)

We create a new `unitTests.qunit.ts` file under `webapp/test/unit/`. This script loads and executes our formatter.

Before the QUnit test execution can be started, we need to wait until the Core has booted. Therefore, you need to disable the autostart via `QUnit.config.autostart = false;`, require the `sap/ui/core/Core` module, and use `Core.ready()` to wait until the Core has booted. Only then can you start the QUnit tests with `QUnit.start()`.

```js
/* @sapUiRequire */
QUnit.config.autostart = false;

// import all your QUnit tests here
void Promise.all([
	import("sap/ui/core/Core"), // required to wait until Core has booted to start the QUnit tests
	import("ui5/walkthrough/test/unit/model/formatter"),
]).then(([{default: Core}]) => Core.ready()).then(() => {
	QUnit.start();
});
```

> ### Note:  
> The `@sapUiRequire` annotation instructs the OpenUI5 TypeScript transpilation process \(executed by `ui5-tooling-transpile`\) to use `sap.ui.require` instead of `sap.ui.define` for a transpiled module. This allows to load the module via a `<script>` tag, which guarantees that `QUnit.config.autostart` is set to `false` directly after QUnit has been loaded.
> 
> This is important for test suites in order to prevent QUnit from immediately starting the test execution even before the QUnit tests have been imported. Once the QUnit tests have been imported, the tests are executed after `QUnit.start()` has been called.

***

<a name="loio750c8c1e2ec1479ea58a4aaf9ee2ab82__section_gnt_54c_yfb"/>

### webapp/test/unit/unitTests.qunit.html \(New\)

Finally we create a new `unitTests.qunit.html` page under `webapp/test/unit`.

Since we are now in the `webapp/test/unit` folder, we need to go up two levels to get the `webapp` folder again. This namespace can be used inside the tests to load and trigger application functionality.

First, we load some basic QUnit functionality via script tags. The QUnit test suite must be included at the end via a script tag which loads `unitTests.qunit.js`. The file extension `.js` must be used, since this loads the transpiled version of `unitTests.qunit.ts`.

```html
<!DOCTYPE html>
<html>
<head>
	<title>Unit tests for UI5 Walkthrough</title>
	<meta charset="utf-8">

	<script
		id="sap-ui-bootstrap"
		src="../../resources/sap-ui-core.js"
		data-sap-ui-resource-roots='{
			"ui5.walkthrough": "../../"
		}'
		data-sap-ui-async="true">
	</script>

	<link rel="stylesheet" type="text/css" href="../../resources/sap/ui/thirdparty/qunit-2.css">

	<script src="../../resources/sap/ui/thirdparty/qunit-2.js"></script>
	<script src="../../resources/sap/ui/qunit/qunit-junit.js"></script>

	<script src="unitTests.qunit.js"></script>
</head>
<body>
	<div id="qunit"/>
	<div id="qunit-fixture"/>
</body>
</html>
```

The so-called QUnit test suite is an HTML page that triggers all QUnit tests for the application. Most of it is generating the layout of the result page that you can see in the preview and we won’t further explain these parts.

If we now open the `webapp/test/unit/unitTests.qunit.html` file in the browser, we should see our test running and verifying the formatter logic.

***

### Conventions

-   All unit tests are placed in the webapp/test/unit folder of the app.

-   Files in the test suite end with `*.qunit.html`.

-   The `unitTests.qunit.html` file triggers all unit tests of the app.

-   A unit test should be written for formatters, controller logic, and other individual functionality.

-   All dependencies are replaced by stubs to test only the functionality in scope.


**Parent topic:**[Walkthrough Tutorial \(TypeScript\)](Walkthrough_Tutorial_TypeScript_dad1905.md "In this tutorial we'll introduce you to all major development paradigms of OpenUI5. We'll demonstrate the use of TypeScript with OpenUI5 and highlight the specific characteristics of this approach.")

**Next:**[Step 26: Mock Server Configuration \(TypeScript\)](Step_26_Mock_Server_Configuration_TypeScript_3e1c64f.md "We just ran our app against a real service, but for developing and testing our app we do not want to rely on the availability of the “real” service or put additional load on the system where the data service is located.")

**Previous:**[Step 28: Integration Test with OPA \(TypeScript\)](Step_28_Integration_Test_with_OPA_TypeScript_412f0b6.md "If we want to test interaction patterns or more visual features of our app, we can also write an integration test.")

**Related Information**  


[Unit Testing with QUnit](Unit_Testing_with_QUnit_09d145c.md "QUnit is a powerful, easy-to-use JavaScript unit testing framework. It is used by the jQuery, jQuery UI and jQuery Mobile projects and is capable of testing any generic JavaScript code. It supports asynchronous tests out-of-the-box.")

[QUnit Home Page](https://qunitjs.com/)

[Testing Tutorial](Testing_Tutorial_291c912.md "In this tutorial we will test application functionality with the testing tools that are delivered with OpenUI5. At different steps of this tutorial you will write tests using QUnit, OPA5, and the OData V2 mock server. Additionally, you will learn about testing strategies, Test Driven Development (TDD), and much more.")

