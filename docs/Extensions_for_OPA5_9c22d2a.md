<!-- loio9c22d2ada0414d97837b845e1e85ab86 -->

| loio |
| -----|
| 9c22d2ada0414d97837b845e1e85ab86 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/9c22d2ada0414d97837b845e1e85ab86) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/9c22d2ada0414d97837b845e1e85ab86)</div>

## Extensions for OPA5

Extend OPA capabilities with custom extensions.

You can provide application-aware assertions that are called from the test but operate in the context of the application being tested.

***

<a name="loio9c22d2ada0414d97837b845e1e85ab86__section_nng_x5k_b1b"/>

### Interface

The extension API is defined in the `sap.ui.test.OpaExtension` class. A custom extension should extend this class and implement the necessary methods. The extension class should be available in the application and loaded in the application frame.

-   **`onAfterInit()`** - called after the application is fully loaded. The test will wait for the returned promise to resolve before starting. This is a good place for extension initialization.

-   **`onBeforeExit()`** - called after the test is finished but before the application is discarded. The application shutdown will wait for the returned promise to resolve. This is the place to clean up the extension.

-   **`getAssertions()`** - called after extension initialization but before the test has started. It should return a map of assertion names and assertion functions. This map is merged in the default QUnit assertion object. The assertion function is called in the context of the application being tested and should return a promise that resolves with `QUnit.pushResult` object. The promise should be resolved for both passing and failing assertion and rejected only if the assertion evaluation fails. The assertion function could interact with the application under test and the test will wait for the returned promise to resolve before continuing. From the point of the view of the test, this assertion is consistent with the classical synchronous QUnit assertions. For more information, see [https://api.qunitjs.com/assert/pushResult](https://api.qunitjs.com/assert/pushResult).


***

<a name="loio9c22d2ada0414d97837b845e1e85ab86__section_nnd_y5k_b1b"/>

### Lifecycle

To load an extension, the test should enable it by specifying extension class name as string in the key 'extensions' in the options object given to `Opa5.extendConfig()`. An array of extension names could be specified or the extension name `?opaExtensions=[my/custom/Extension]` could be given in the test URL. If the extension needs some application parameters, they could be provided in the `appParams`.

For more information, see the *API Reference*: [ `Opa5.extendConfig()`](https://openui5.hana.ondemand.com/#/api/sap.ui.test.Opa5/methods/sap.ui.test.Opa5.extendConfig) 

***

<a name="loio9c22d2ada0414d97837b845e1e85ab86__section_oc2_y5k_b1b"/>

### Example

Custom extension class:

``` js
sap.ui.define([
  'sap/ui/test/OpaExtension'
], function(OpaExtension) {
  "use strict";
  var customExtension = OpaExtension.extend("sap.ui.test.sample.CustomOpaExtension", {
    metadata : {
      publicMethods : [
        "getAssertions"
      ]
    },
    getAssertions : function() {
      return {
        myCustomAssertion: function() {
          return new Promise(function(resolve, reject) {

            // start custom assertion logic, resolve the promise when ready
            setTimeout(function() {

              // Assertion passes
              resolve({
                result: true,
                message: "Custom assertion passes"
              });

              // OR Assertion fails
              resolve({
                result: false,
                message: "Custom assertion fails"
              });

              // OR Propagate an error while evaluating assertion
              reject(new Error("Error while evaluating assertion, details: " + details));

            },0);

          });
        }
      }
    }
  });
  
  return customExtension;
});
```

Activate this extension and provide some URI parameters to the application:

``` js
Opa5.extendConfig({
  extensions: ["sap/ui/test/sample/CustomOpaExtension"],
  appParams: {
    "key": "value"
  }
});
```

Call the custom extension from the test:

``` js
Opa5.createPageObjects({
  onMyView : {
    viewName : "MyView",
    assertions : {
      iShouldUseMyCustomAssertion : function () {
        return this.waitFor({
          id: "MyControlId",
          actions: new Press(),
          success : function () {
            Opa5.assert.myCustomAssertion();
          }
        });
      }
    }
  }
});
```

