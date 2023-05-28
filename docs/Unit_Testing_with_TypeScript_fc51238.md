<!-- loiofc51238aaadf43be863ba35986764d69 -->

| loio |
| -----|
| fc51238aaadf43be863ba35986764d69 |

<div id="loio">

view on: [demo kit nightly build](https://sdk.openui5.org/nightly/#/topic/fc51238aaadf43be863ba35986764d69) | [demo kit latest release](https://sdk.openui5.org/topic/fc51238aaadf43be863ba35986764d69)</div>

## Unit Testing with TypeScript

TypeScript unit testing is a technique that tests small units of code that function. It can be done with frameworks like Mocha.js and Chai2, or Alsatian3, which output TAP-compliant markup. Unit testing aims to achieve consistency and verify the code's functionality or specifications.

> ### Note:  
> QUnit is globally defined, and its types are automatically required by the UI5 types. So, there is no setup needed to use it. However, to allow cleaner code that does not access any globals, starting with UI5 1.112, QUnit can be explicitly imported like this: import QUnit from "sap/ui/thirdparty/qunit-2";

***

<a name="loiofc51238aaadf43be863ba35986764d69__section_wh2_131_pxb"/>

### Why Does OpenUI5 Write Unit Tests with TypeScript

TypeScript is neither a library nor a framework. Instead, it’s a programming language, a superset of vanilla JavaScript. TypeScript augments regular JavaScript with static typing, some functional details, and more features.

***

<a name="loiofc51238aaadf43be863ba35986764d69__section_acr_ck1_pxb"/>

### Creating an Entry Point

Below is the entry point for running the tests, it loads QUnit etc. and finally, once UI5 is launched, it loads the list of tests configured.

```
<!DOCTYPE html> 
<html> 
<head> 
	<meta charset="utf-8"> 
	<title>Unit tests for the TypesScript Hello World app</title> 
	<script 
		id="sap-ui-bootstrap" 
		src="../../resources/sap-ui-core.js" 
		data-sap-ui-resourceroots='{ 
			"ui5.typescript.helloworld": "../../", 
			"unit": "." 
		}' 
		data-sap-ui-async="true" 
		data-sap-ui-oninit="module:unit/unitTests.qunit"> 
	</script> 
	<link rel="stylesheet" type="text/css" href="../../resources/sap/ui/thirdparty/qunit-2.css"> 
	<script src="../../resources/sap/ui/thirdparty/qunit-2.js"></script> 
	<script src="../../resources/sap/ui/qunit/qunit-junit.js"></script> 
	<script src="../../resources/sap/ui/qunit/qunit-coverage.js"></script> 
	<script src="../../resources/sap/ui/thirdparty/sinon.js"></script> 
	<script src="../../resources/sap/ui/thirdparty/sinon-qunit.js"></script> 
</head> 
<body> 
	<div id="qunit"></div> 
	<div id="qunit-fixture"></div> 
</body> 
</html> 
```

***

<a name="loiofc51238aaadf43be863ba35986764d69__section_k2d_3m1_pxb"/>

### Importing Test Files

The code below imports all test files, which can be done in a very clean way thanks to the ES6 module imports. We follow the recommendation of QUnit: 

```
// https://api.qunitjs.com/config/autostart/ 
QUnit.config.autostart = false; 
 
// import all your QUnit tests here 
void Promise.all([ 
	import("unit/controller/App.qunit") 
]).then(() => { 
	QUnit.start(); 
}); 
```

`QUnit.config.autostart = false` must be set before QUnit thinks it can start, then the tests are imported as dynamic imports like`import("unit/controller/App.qunit")`with `Promise.all(...)`waiting for them and then triggering `QUnit.start()` is called.

***

<a name="loiofc51238aaadf43be863ba35986764d69__section_dmv_g41_pxb"/>

### Concrete Tests

In the \(very minimal\) actual tests in the code below there is nothing surprising from TypeScript perspective. There isn't any TypeScript-specific syntax required, but of course ES6-style imports are used just like in the application code.

```
import AppController from "ui5/typescript/helloworld/controller/App.controller"; 
 
QUnit.module("Sample App controller test"); 
 
QUnit.test("The AppController class has a sayHello method", function (assert) { 
    // as a very basic test example just check the presence of the "sayHello" method 
    assert.strictEqual(typeof AppController.prototype.sayHello, "function"); 
}); 
```

