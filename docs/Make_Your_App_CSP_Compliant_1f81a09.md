<!-- loio1f81a093a9f3433983dcb2ebe11cd4cd -->

| loio |
| -----|
| 1f81a093a9f3433983dcb2ebe11cd4cd |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/1f81a093a9f3433983dcb2ebe11cd4cd) | [demo kit latest release](https://sdk.openui5.org/topic/1f81a093a9f3433983dcb2ebe11cd4cd)</div>

## Make Your App CSP Compliant

CSP stands for Content Security Policy and is a security standard to prevent cross-site scripting or other code injection attacks.

It's strongly recommended that you make your OpenUI5 applications CSP compliant - after all, you want your apps to be secure. The main thing you have to do is to remove all scripts that directly execute code from your HTML pages.

***

<a name="loio1f81a093a9f3433983dcb2ebe11cd4cd__section_wkh_b2v_zfb"/>

### Define Initial Components in a Declarative Way

Don't use directly executable code in your HTML files, because this makes them vulnerable. Instead, enable the `ComponentSupport` module in the bootstrapping script. Then, declare your desired component in the body via a `div` tag. This will instantiate the component when the `onInit` is executed.

```html
...
<script id="sap-ui-bootstrap"
	src="resources/sap-ui-core.js"
	data-sap-ui-preload="async"
	data-sap-ui-theme="sap_belize"
	data-sap-ui-oninit="module:sap/ui/core/ComponentSupport">
</script>
<body class="sapUiBody" id="content">
	<div data-sap-ui-component data-name="sap.ui.demo.walkthrough" data-id="container" data-settings='{"id" : "walkthrough"}'></div>
</body>
```

-   Learn how: Walkthrough Tutorial [Step 9: Component Configuration](Step_9_Component_Configuration_4cfa608.md)
-   Find our more: [Declarative API for Initial Components](Declarative_API_for_Initial_Components_82a0fce.md)

***

<a name="loio1f81a093a9f3433983dcb2ebe11cd4cd__section_kgn_521_1gb"/>

### Separate Scripts From HTML Files in Your Test Folder

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

-   Learn how: Testing Tutorial [Step 10: Test Suite and Automated Testing](Step_10_Test_Suite_and_Automated_Testing_07c97a2.md)
-   Find out more: [Content Security Policy](Content_Security_Policy_fe1a6db.md)

