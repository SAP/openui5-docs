<!-- loio91f1454b6f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f1454b6f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/91f1454b6f4d1014b6dd926db0e91070) | [demo kit latest release](https://sdk.openui5.org/topic/91f1454b6f4d1014b6dd926db0e91070)</div>

## Compiling Declarative HTML

OpenUI5 provides a plugin for controls that are defined as declarative markup on startup time.

To compile the declarative UI markup deferred, for example, when the markup is dynamically loaded and added to the DOM you can call the `sap.ui.core.plugin.DeclarativeSupport`.compile method, see the following code snippet:

```html
<div id="button">
  <div data-sap-ui-type="sap.m.Button" data-text="This button is added dynamically"></div>
</div>

<script>
  sap.ui.core.plugin.DeclarativeSupport.compile(document.getElementById("button"));
</script>
```

