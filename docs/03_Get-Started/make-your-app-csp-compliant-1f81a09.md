<!-- loio1f81a093a9f3433983dcb2ebe11cd4cd -->

# Make Your App CSP Compliant

CSP stands for Content Security Policy and is a security standard to prevent cross-site scripting or other code injection attacks.

It's strongly recommended that you make your OpenUI5 applications CSP compliant - after all, you want your apps to be secure. The main thing you have to do is to remove all scripts that directly execute code from your HTML pages.

***

<a name="loio1f81a093a9f3433983dcb2ebe11cd4cd__section_wkh_b2v_zfb"/>

## Define Initial Components in a Declarative Way

Don't use directly executable code in your HTML files, because this makes them vulnerable. Instead, enable the `ComponentSupport` module in the bootstrapping script. Then, declare your desired component in the body via a `div` tag. This will instantiate the component when the `onInit` is executed.

```html
...
<script id="sap-ui-bootstrap"
	src="resources/sap-ui-core.js"
	data-sap-ui-async="true"
	data-sap-ui-on-init="module:sap/ui/core/ComponentSupport">
</script>
<body class="sapUiBody" id="content">
	<div data-sap-ui-component data-name="sap.ui.demo.walkthrough" data-id="container" data-settings='{"id" : "walkthrough"}'></div>
</body>
```

-   Learn how: Walkthrough Tutorial [Step 9: Component Configuration](https://help.sap.com/viewer/93953b95df5f4e938c8eb421cef56319/1.138_SAPUI5_ABAP/en-US/4cfa60872dca462cb87148ccd0d948ee.html "After we have introduced all three parts of the Model-View-Controller (MVC) concept, we now come to another important structural aspect of SAPUI5.") :arrow_upper_right:
-   Find our more: [Declarative API for Initial Components](../04_Essentials/declarative-api-for-initial-components-82a0fce.md)

***

<a name="loio1f81a093a9f3433983dcb2ebe11cd4cd__section_kgn_521_1gb"/>

## Separate Scripts From HTML Files in Your Test Folder

Because the HTML files in your test folder do not directly open your application, you can't use the new `ComponentSupport` feature here. To make them CSP compliant, you need to put the executable script code in a separate file on the same level as the HTML file. You can then refer to this file in your HTML file inside a `script` tag in the head:

New script file:

```js
window.suite = function() {
	"use strict";

	var oSuite = new parent.jsUnitTestSuite(),
		sContextPath = location.pathname.substring(0, location.pathname.lastIndexOf("/") + 1);

	oSuite.addTestPage(sContextPath + "unit/unitTests.qunit.html");
	oSuite.addTestPage(sContextPath + "integration/opaTests.qunit.html");

	return oSuite;
};

```

HTML file:

```html
<head>
	...
	<script src="testsuite.qunit.js" data-sap-ui-testsuite></script>
</head>

</html>

```

-   Learn how: Testing Tutorial [Step 10: Automated Testing](https://help.sap.com/viewer/93953b95df5f4e938c8eb421cef56319/1.138_SAPUI5_ABAP/en-US/07c97a2e497d443eb6fa74bb9445ab9c.html "In this step, we will step back from our tests and application features that we have implemented so far and take a closer look at another important piece of the test setup - the test automation. We will learn how to set up a basic test automation, which might be used in a continuous integration system or locally to run tests via shell.") :arrow_upper_right:
-   Find out more: [Content Security Policy](../05_Developing_Apps/content-security-policy-fe1a6db.md)

