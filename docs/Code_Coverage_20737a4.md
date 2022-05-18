<!-- loio20737a4c64f448d2af9b9745fbe5d762 -->

| loio |
| -----|
| 20737a4c64f448d2af9b9745fbe5d762 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/20737a4c64f448d2af9b9745fbe5d762) | [demo kit latest release](https://sdk.openui5.org/topic/20737a4c64f448d2af9b9745fbe5d762)</div>

## Code Coverage

It can be handy to calculate the code coverage of your integration tests, for example, to figure out whether you forgot to test something or to provide statistics on your test quality.

At test execution time, Gherkin offers the option *Enable coverage* at the top left of the test results. Enabling the option reruns the tests and then lists the files that were tested at the bottom of the page.

 ![](images/loio58d6e82cf5184288a2926951d8d12c30_LowRes.png) 

Gherkin calculates code coverage for any JavaScript file that is loaded after the test harness. This may cause some system libraries to appear in the results. You can specify which files to calculate code coverage for by adding code to your HTML bootstrap file \(after loading OpenUI5, but before running your tests\), as follows.

```html
<script
  src="path/to/resources/sap/ui/qunit/qunit-coverage.js"
  data-sap-ui-cover-only="GherkinWithOPA5/"
  data-sap-ui-cover-never="sap/ui/">
</script>
```

For more information, see the documentation for Blanket.js on GitHub. Keep in mind that the attribute name is slightly different in the OpenUI5 implementation \(`data-sap-ui-cover-only` instead of `data-cover-only`\).

**Related Information**  


[`Blanket.js` Documentation on GitHub](https://github.com/alex-seville/blanket/blob/master/docs/intermediate_browser.md)

[Code Coverage Measurement](Code_Coverage_Measurement_7ef3242.md "You can measure the code coverage for your test inside the Control.qunit.html page either via HTML or JavaScript code using Blanket.js.")

