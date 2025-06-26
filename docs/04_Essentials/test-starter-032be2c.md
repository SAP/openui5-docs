<!-- loio032be2cb2e1d4115af20862673bedcdb -->

# Test Starter

The test starter is a concept intended to simplify the test setup for OpenUI5 applications and libraries by orchestrating your QUnit and OPA5 tests.

***

<a name="loio032be2cb2e1d4115af20862673bedcdb__section_szb_fxg_vcc"/>

## Goals

Using the test starter concept in your project:

-   reduces the boiler plate code needed to write a QUnit test;
-   ensures the loading of the most commonly used testing frameworks \(for example, QUnit, Sinon.JS, qunit-reporter\);
-   ensures these testing frameworks and your test modules are loaded completely asynchronously and comply with the [Content Security Policy](../05_Developing_Apps/content-security-policy-fe1a6db.md);
-   allows moving the configuration of the testing frameworks out of the test code.

-   **[Concept and Basic Setup](concept-and-basic-setup-22f50c0.md "To apply the test starter concept to your OpenUI5 project, you need to
		create a test suite and a generic test page that allows for the running of one or multiple
		test modules.")**  
To apply the test starter concept to your OpenUI5 project, you need to create a test suite and a generic test page that allows for the running of one or multiple test modules.
-   **[Configuration Options](configuration-options-738ed02.md "The UI5 test suite module contains the configuration for the UI5 test
		suite.")**  
The UI5 test suite module contains the configuration for the UI5 test suite.

