<!-- loio7cdee404cac441888539ed7bfe076e57 -->

| loio |
| -----|
| 7cdee404cac441888539ed7bfe076e57 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/7cdee404cac441888539ed7bfe076e57) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/7cdee404cac441888539ed7bfe076e57)</div>

## Testing

OpenUI5 provides several testing options, like to unit and integration tests and the OData V2 mock server.

Before you start implementing your first test, you should think about how to test the different aspects of your application. The image below shows some examples of testing tools along the agile testing pyramid.

   
  
<a name="loio7cdee404cac441888539ed7bfe076e57__fig_u2g_t2y_2t"/>Testing Pyramid

 ![](loio88758c3b4ad94e9ca6508d106fe66972_LowRes.png "Testing Pyramid") 

You can use a local test runner, such as Selenium or Karma, that automatically executes all tests whenever a file in the app project has been changed.

***

<a name="loio7cdee404cac441888539ed7bfe076e57__section_ojr_rzb_qnb"/>

### Recommended Tools

***

#### OPA5

We recommend OPA5 for integration tests. OPA5 is part of OpenUI5. It is built on top of QUnit and provides good integration with OpenUI5.

***

#### UIVeri5

We recommend UIVeri5 for system and end-to-end tests. UIVeri5 is an end-to-end testing framework inspired by Protractor.

UIVeri5 is built exclusively for OpenUI5 apps. It uses WebDriverJS to drive a real browser and interact with your app the same was a real user would.

**Related Information**  


[Tutorial: Testing](Testing_291c912.md)

[Continuous Integration: Ensure Code Quality](Continuous_Integration_Ensure_Code_Quality_fe7a158.md)

[Integration Testing with One Page Acceptance Tests \(OPA5\)](Integration_Testing_with_One_Page_Acceptance_Tests_(OPA5)_2696ab5.md)

[Tutorial: Mock Server](OData_V2_Mock_Server_3a9728e.md)

[UIVeri5 Home Page](https://www.npmjs.com/package/@ui5/uiveri5)

[Selenium Home Page](http://docs.seleniumhq.org/)

[Karma Home Page](https://www.npmjs.com/package/karma)

[Mock Server](Mock_Server_69d3cbd.md)

