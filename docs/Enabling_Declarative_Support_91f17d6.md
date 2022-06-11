<!-- loio91f17d636f4d1014b6dd926db0e91070 -->

| loio |
| -----|
| 91f17d636f4d1014b6dd926db0e91070 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/topic/91f17d636f4d1014b6dd926db0e91070) | [demo kit latest release](https://sdk.openui5.org/topic/91f17d636f4d1014b6dd926db0e91070)</div>

## Enabling Declarative Support

Declarative support needs to be enabled in the HTML document by adding an attribute to the OpenUI5 bootstrap script tag.

This is done as follows:

```
data-sap-ui-modules="sap.ui.core.plugin.DeclarativeSupport"
```

OpenUI5 then requires \(loads\) the plugin `sap.ui.core.plugin.DeclarativeSupport`. When started, the plugin parses and enhances special HTML tags in the HTML document. The complete bootstrap script tag for OpenUI5 \(based on a CDN version\) looks as follows:

```html
<script id="sap-ui-bootstrap"
  type="text/javascript"
  src="resources/sap-ui-core.js"
  data-sap-ui-theme="sap_belize"
  data-sap-ui-libs="sap.m"
  data-sap-ui-modules="sap.ui.core.plugin.DeclarativeSupport"
  >
</script>
```

