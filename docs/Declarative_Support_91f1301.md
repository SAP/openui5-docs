<!-- loio91f130196f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f130196f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/91f130196f4d1014b6dd926db0e91070) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/91f130196f4d1014b6dd926db0e91070)</div>

## Declarative Support

Declarative programming allows you to define the UI within the HTML document as elements.

For this, OpenUI5 provides the `sap.ui.core.plugin.DeclarativeSupport` plugin that can be included either as required or marked as a module in the initial bootstrap script tag. The plugin parses the document and converts its tags with special attributes into OpenUI5 controls.

Declarative support is aware of properties, associations, events, and aggregations in a OpenUI5 control manner. This means that you can specify them within the markup of the HTML document either as data attributes or as child elements.

The following sections provide an overview of the declarative support and introduce the use of declarative support in OpenUI5.

***

<a name="loio91f130196f4d1014b6dd926db0e91070__section_C1D3894EF36F4766B06E27E5675CA11F"/>

### Example

The following example shows the concept by combining a `sap.m.input` with a `sap.m.Button` control. When you click the button, the value of the text field is displayed in an alert box:

``` html
<!Doctype HTML>
<html>
<head>
	<title>Declarative Programming for SAPUI5 - sample01</title>
	<script id="sap-ui-bootstrap"
	     type="text/javascript"
	     src="resources/sap-ui-core.js"
	     data-sap-ui-theme="sap_belize"
	     data-sap-ui-libs="sap.m"
	     data-sap-ui-modules="sap.ui.core.plugin.DeclarativeSupport"
	     >
	</script>
</head>
<body class="sapUiBody">
  <div data-sap-ui-type="sap.m.Input" id="message" class="my-button" data-value="Hello World"></div>
  <div data-sap-ui-type="sap.m.Button" data-text="Click me!" data-press="handlePress"></div>
</body>
</html>
```

***

<a name="loio91f130196f4d1014b6dd926db0e91070__section_E477586F3CAD4371AC5E8CAEB1021D5E"/>

### Summary: Attributes Used by Declarative Support

The table summarizes the attributes used by declarative support and gives examples.

|Attribute|Description|Example|
|---------|-----------|-------|
|`data-sap-ui-type`|Type of control|`<div data-sap-ui-type="sap.m.Button"></div>`|
|`data-sap-ui-aggregation`|Defines the aggregation that shall be used for the element or child element|`<div data-sap-ui-type="sap.m.Panel"><div data-sap-ui-aggregation="content" data-sap-ui-type="sap.m.Button" data-text="My Button"></div></div>`|
|`data-sap-ui.default-aggregation`|Sets or overrides the default aggregation of a control|`<div data-sap-ui-type="sap.m.Panel" data-sap-ui-default-aggregation="headerToolbar"><div data-sap-ui-type="sap.m.Toolbar"></div></div>` |
|`id`|Defines the ID property of a control|`<div data-sap-ui-type="sap.m.Button" id="myButton"></div>` |
|`class`|Adds a style class to the control|`<div data-sap-ui-type="sap.m.Button" class="myButton"></div>` |

