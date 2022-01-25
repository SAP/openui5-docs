<!-- loio9bf4dce43b7943d0909cd6c58a933589 -->

| loio |
| -----|
| 9bf4dce43b7943d0909cd6c58a933589 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9bf4dce43b7943d0909cd6c58a933589) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9bf4dce43b7943d0909cd6c58a933589)</div>

## Step 29: Integration Test with OPA

If we want to test interaction patterns or more visual features of our app, we can also write an integration test.

We haven’t thought about testing our interaction with the app yet, so in this step we will check if the dialog actually opens when we click the “Say Hello with Dialog” button. We can easily do this with OPA5, a feature of OpenUI5 that is easy to set up and is based on JavaScript and QUnit. Using integration and unit tests and running them consistently in a continuous integration \(CI\) environment, we can make sure that we don’t accidentally break our app or introduce logical errors in existing code.

> ### Note:  
> In this tutorial, we focus on a simple use case for the test implementation. If you want to learn more about OPA tests, have a look at our [Testing](Testing_291c912.md) tutorial, especially [Step 6: A First OPA Test](Step_6_A_First_OPA_Test_1b47457.md).

***

### Preview

   
  
<a name="loio9bf4dce43b7943d0909cd6c58a933589__fig_r1j_pst_mr"/>An OPA test opens the "Hello" dialog from step 16

 ![](loio108eccbd79ad4cc1b4091be62be59991_HiRes.png "An OPA test opens the "Hello" dialog from step 16") 

***

### Coding

You can view and download all files at [Walkthrough - Step 29](https://openui5.hana.ondemand.com/explored.html#/sample/sap.m.tutorial.walkthrough.29/preview).

   
  
<a name="loio9bf4dce43b7943d0909cd6c58a933589__fig_rqr_hcp_ns"/>Folder Structure for this Step

 ![](loio72406abd1014466fb961d4c4dd1ade58_HiRes.png "Folder Structure for this Step") 

We add a new folder `integration` below the `test` folder, where we put our new test cases. Page objects that help structuring such integration tests are put in the `pages` subfolder that we also create now.

***

### webapp/test/integration/NavigationJourney.js \(New\)

``` js
*HIGHLIGHT START*/*global QUnit, opaTest*/

sap.ui.define([
	"sap/ui/demo/walkthrough/localService/mockserver",
	"sap/ui/test/opaQunit",
	"./pages/App"
], function (mockserver) {
	"use strict";

	QUnit.module("Navigation");

	opaTest("Should open the Hello dialog", function (Given, When, Then) {
		// initialize the mock server
		mockserver.init();

		// Arrangements
		Given.iStartMyUIComponent({
			componentConfig: {
				name: "sap.ui.demo.walkthrough"
			}
		});

		//Actions
		When.onTheAppPage.iPressTheSayHelloWithDialogButton();

		// Assertions
		Then.onTheAppPage.iShouldSeeTheHelloDialog();

		// Cleanup
		Then.iTeardownMyApp();
	});
});
*HIGHLIGHT END*
```

Let’s start with the `journey` first. A `journey` consists of a series of integration tests that belong to the same context such as navigating through the app. Similar to the QUnit test implementation, OPA5 uses QUnit, that's why we first set up a QUnit module `Navigation` that will be displayed on our result page.

The function `opaTest` is the main aspect for defining integration tests with OPA. Its parameters define a test name and a callback function that gets executed with the following OPA5 helper objects to write meaningful tests that read like a user story.

-   `Given`

    On the given object we can call arrangement functions like `iStartMyUIComponent` to load our app component for integration testing.

-   `When`

    Contains custom actions that we can execute to get the application in a state where we can test the expected behavior.

-   `Then`

    Contains custom assertions that check a specific constellation in the application and the teardown function that removes our component again.


In our journey, we create a very simple test that starts the app. Inside the app, we simulate a click on a button and expect that the dialog is opened afterwards. Finally, we shut down the app again.

As you can see, the test case reads like a user story, we actually do not need the implementation of the methods yet to understand the meaning of the test case. This approach is called "Behavior Driven Development" or simply BDD and is popular in "Agile Software Development".

***

### webapp/test/integration/pages/App.js \(New\)

``` js
*HIGHLIGHT START*sap.ui.define([
	"sap/ui/test/Opa5",
	"sap/ui/test/actions/Press"
], function (Opa5, Press) {
	"use strict";

	var sViewName = "sap.ui.demo.walkthrough.view.HelloPanel";

	Opa5.createPageObjects({
		onTheAppPage: {
			actions: {
				iPressTheSayHelloWithDialogButton: function () {
					return this.waitFor({
						id: "helloDialogButton",
						viewName: sViewName,
						actions: new Press(),
						errorMessage: "Did not find the 'Say Hello With Dialog' button on the HelloPanel view"
					});
				}
			},

			assertions: {
				iShouldSeeTheHelloDialog: function () {
					return this.waitFor({
						controlType: "sap.m.Dialog",
						success: function () {
							// we set the view busy, so we need to query the parent of the app
							Opa5.assert.ok(true, "The dialog is open");
						},
						errorMessage: "Did not find the dialog control"
					});
				}
			}
		}
	});
});*HIGHLIGHT END*
```

The implementation of the page object holds the helper functions we just called in our `journey`. We require OPA5 from the `sap.ui.test` namespace and define a page object with the helper function `createPageObjects`. We pass in an object with the key of our page `onTheAppPage` and two sections: `actions` and `assertions`.

In the actions section of the page object we define a function to click the "Hello" dialog button. This is done in OPA5 with a `waitFor` statement, it is basically a loop that checks for the conditions defined as parameters. If the conditions are met, the success callback is executed, if the test fails because the conditions have not been met, the text in the `errorMessage` property is displayed on the result page.

We define a `waitFor` statement that checks for controls of type `sap.m.Button`. As soon as a button is found on the app page the success handler is executed and we use jQuery to trigger a `tap` event on the first button that we found. This should open the `HelloDialog` similar to clicking on the button manually.

In the assertions section we define another `waitFor` statement that checks if a `sap.m.Dialog` control is existing in the DOM of the app. When the dialog has been found, the test is successful and we can immediately confirm by calling an `ok` statement with a meaningful message.

***

<a name="loio9bf4dce43b7943d0909cd6c58a933589__section_srf_xpc_yfb"/>

### webapp/test/integration/opaTests.qunit.html \(New\)

``` html
*HIGHLIGHT START*<!DOCTYPE html>
<html>
<head>
	<title>Integration tests for SAPUI5 Walkthrough</title>
	<meta charset="utf-8">

	<script
		id="sap-ui-bootstrap"
		src="https://openui5.hana.ondemand.com/resources/sap-ui-core.js"
		data-sap-ui-theme="sap_belize"
		data-sap-ui-resourceroots='{
			"sap.ui.demo.walkthrough": "../../"
		}'
		data-sap-ui-animation="false"
		data-sap-ui-compatVersion="edge"
		data-sap-ui-async="true">
	</script>

	<link rel="stylesheet" type="text/css" href="https://openui5.hana.ondemand.com/resources/sap/ui/thirdparty/qunit-2.css">

	<script src="https://openui5.hana.ondemand.com/resources/sap/ui/thirdparty/qunit-2.js"></script>
	<script src="https://openui5.hana.ondemand.com/resources/sap/ui/qunit/qunit-junit.js"></script>

	<script src="opaTests.qunit.js"></script>
</head>
<body>
	<div id="qunit"></div>
	<div id="qunit-fixture"></div>
</body>
</html>
*HIGHLIGHT END*
```

This file contains our test suite for all OPA tests of the app. We use the same namespace as for our application.

Then we load the basic QUnit functionality via script tags from OpenUI5 so that we can execute the test journey. The `NavigationJourney` we defined above will be loaded via a script called `opaTests.qunit.js`:

***

<a name="loio9bf4dce43b7943d0909cd6c58a933589__section_trf_xpc_yfb"/>

### webapp/test/integration/opaTests.qunit.js \(New\)

``` js
/* global QUnit */

QUnit.config.autostart = false;

sap.ui.getCore().attachInit(function () {
	"use strict";

	sap.ui.require([
		"sap/ui/demo/walkthrough/test/integration/NavigationJourney"
	], function () {
		QUnit.start();
	});
});

```

This script loads the `NavigationJourney`, and the test functions inside are immediately executed. When you call the `webapp/test/integration/opaTests.qunit.html` page of your project on the server, you should see the QUnit layout and a test “Should see the Hello dialog” is executed immediately. It will load the app component on the right side of the page. There you can see what operations the test is performing on the app, if everything works correctly the button click is triggered, then a dialog is shown and the test case is green.

***

### Conventions

-   OPA tests are located in the `webapp/test/integration` folder of the application.

-   Use `page` objects and `journeys` for structuring OPA tests.


**Related Information**  


[Integration Testing with One Page Acceptance Tests \(OPA5\)](Integration_Testing_with_One_Page_Acceptance_Tests_(OPA5)_2696ab5.md "OPA5 is an API for OpenUI5 controls. It hides asynchronicity and eases access to OpenUI5 elements. This makes OPA especially helpful for testing user interactions, integration with OpenUI5, navigation, and data binding.")

[Samples: `sap.ui.test.Opa5` ](https://openui5.hana.ondemand.com/explored.html#/entity/sap.ui.test.Opa5/samples)

[Testing](Testing_291c912.md "In this tutorial we will test application functionality with the testing tools that are delivered with OpenUI5. At different steps of this tutorial you will write tests using QUnit, OPA5, and the OData V2 mock server. Additionally, you will learn about testing strategies, Test Driven Development (TDD), and much more.")

