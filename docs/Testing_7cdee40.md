<!-- loio7cdee404cac441888539ed7bfe076e57 -->

| loio |
| -----|
| 7cdee404cac441888539ed7bfe076e57 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/7cdee404cac441888539ed7bfe076e57) | [demo kit latest release](https://sdk.openui5.org/topic/7cdee404cac441888539ed7bfe076e57)</div>

## Testing

OpenUI5 provides several testing options, like to unit and integration tests and the OData V2 mock server.

Before you start implementing your first test, you should think about how to test the different aspects of your application. The image below shows some examples of testing tools along the agile testing pyramid.

   
  
<a name="loio7cdee404cac441888539ed7bfe076e57__fig_u2g_t2y_2t"/>Testing Pyramid

 ![](images/loio88758c3b4ad94e9ca6508d106fe66972_LowRes.png "Testing Pyramid") 

You can use a local test runner, such as Selenium or Karma, that automatically executes all tests whenever a file in the app project has been changed.

***

<a name="loio7cdee404cac441888539ed7bfe076e57__section_ojr_rzb_qnb"/>

### Recommended Tools

***

#### OPA5

We recommend OPA5 for integration tests. OPA5 is part of OpenUI5. It is built on top of QUnit and provides good integration with OpenUI5.

***

#### wdi5

WebdriverIO \(WDIO\) is a hugely popular end-to-end testing framework. It can work with any web app but lacks the awareness of the web framework that the application uses. wdi5, which is a WDIO plugin, bridges this gap and provides two key benefits, namely control locators and synchronization with the web framework. wdi5 uses a real browser and interacts with your app the same way a real user would.

-   **[Unit Testing with QUnit](Unit_Testing_with_QUnit_09d145c.md "QUnit is a powerful, easy-to-use JavaScript unit testing framework. It is used by the
		jQuery, jQuery UI and jQuery Mobile projects and is capable of testing any generic
		JavaScript code. It supports asynchronous tests out-of-the-box.")**  
QUnit is a powerful, easy-to-use JavaScript unit testing framework. It is used by the jQuery, jQuery UI and jQuery Mobile projects and is capable of testing any generic JavaScript code. It supports asynchronous tests out-of-the-box.
-   **[Integration Testing with One Page Acceptance Tests \(OPA5\)](Integration_Testing_with_One_Page_Acceptance_Tests_OPA5_2696ab5.md "OPA5 is an API for OpenUI5
		controls. It hides asynchronicity and eases access to OpenUI5 elements. This makes OPA
		especially helpful for testing user interactions, integration with OpenUI5, navigation, and data
		binding.")**  
OPA5 is an API for OpenUI5 controls. It hides asynchronicity and eases access to OpenUI5 elements. This makes OPA especially helpful for testing user interactions, integration with OpenUI5, navigation, and data binding.
-   **[Mock Server](Mock_Server_69d3cbd.md "A mock server mimics one or more back-end services. It is used to simplify integration testing and to decouple UI development from service
		development. By using a mock server you can develop and test the UI even if the service in the back end is incomplete or unstable.")**  
A mock server mimics one or more back-end services. It is used to simplify integration testing and to decouple UI development from service development. By using a mock server you can develop and test the UI even if the service in the back end is incomplete or unstable.
-   **[Test Automation](Test_Automation_ae44824.md#loioae448243822448d8ba04b4784f4b09a0 "To make sure that the code is always tested thoroughly before it is included in a
		productive app, you should use a test runner that automates tests. The test runner can be
		included in your project setup so that it is called whenever code changes are
		submitted.")**  
To make sure that the code is always tested thoroughly before it is included in a productive app, you should use a test runner that automates tests. The test runner can be included in your project setup so that it is called whenever code changes are submitted.
-   **[Behavior-driven Development with Gherkin](Behavior_driven_Development_with_Gherkin_45ac9f1.md "A software development process driven by app behavior.")**  
A software development process driven by app behavior.
-   **[Test Recorder](Test_Recorder_2535ef9.md "The Test Recorder tool supports app developers who write integration and system
		tests.")**  
The Test Recorder tool supports app developers who write integration and system tests.

**Related Information**  


[Tutorial: Testing](Testing_291c912.md "In this tutorial we will test application functionality with the testing tools that are delivered with OpenUI5. At different steps of this tutorial you will write tests using QUnit, OPA5, and the OData V2 mock server. Additionally, you will learn about testing strategies, Test Driven Development (TDD), and much more.")

[Continuous Integration: Ensure Code Quality](Continuous_Integration_Ensure_Code_Quality_fe7a158.md "This section describes the setup of a development project where multiple developers work together on the same code.")

[Integration Testing with One Page Acceptance Tests \(OPA5\)](Integration_Testing_with_One_Page_Acceptance_Tests_OPA5_2696ab5.md "OPA5 is an API for OpenUI5 controls. It hides asynchronicity and eases access to OpenUI5 elements. This makes OPA especially helpful for testing user interactions, integration with OpenUI5, navigation, and data binding.")

[Tutorial: Mock Server](OData_V2_Mock_Server_3a9728e.md "In this tutorial, we will explore some advanced features of the OData V2 mock server.")

[wdi5 Home Page](https://github.com/js-soft/wdi5)

[Selenium Home Page](http://docs.seleniumhq.org/)

[Karma Home Page](https://www.npmjs.com/package/karma)

[Mock Server](Mock_Server_69d3cbd.md "A mock server mimics one or more back-end services. It is used to simplify integration testing and to decouple UI development from service development. By using a mock server you can develop and test the UI even if the service in the back end is incomplete or unstable.")

