<!-- loio62d9c4d8f5ad49aa914624af9551beb7 -->

| loio |
| -----|
| 62d9c4d8f5ad49aa914624af9551beb7 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/62d9c4d8f5ad49aa914624af9551beb7) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/62d9c4d8f5ad49aa914624af9551beb7)</div>

## Frame Options

`frameOptions` is used to prevent security vulnerabilities like clickjacking. With the `frameOptions` configuration you define whether OpenUI5 is allowed to run embedded in a frame or only from trusted origins or not at all.

OpenUI5 provides the following configuration options for `frameOptions`:

|Mode|Default|Description|
|----|-------|-----------|
|allow|X|Allows to be embedded from all origins|
|deny| |Denies to be embedded from all origins|
|trusted| |Allows to be embedded from trusted origins according to the same-origin policy and to be embedded to origins allowed by the allowlist service|

With `frameOptionsConfig` the following additional configuration options can be set:

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Parameter</th>
			<th>Type</th>
			<th>Default</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> `callback` </td>
			<td> `function(bSuccess)` </td>
			<td>Function that is called with the success state

 > Note:
   > The function can be synchronously called from the OpenUI5 bootstrap script. The DOM \(`document.body`\) may not be accessible.
			</td>
		</tr>
		<tr>
			<td> `timeout` </td>
			<td> `number` </td>
			<td> `10000` </td>
			<td>After the delay, the page remains blocked and the provided callback is invoked \(milliseconds\)</td>
		</tr>
		<tr>
			<td> `blockEvents` </td>
			<td> `boolean` </td>
			<td> `true` </td>
			<td>Defines whether keyboard, mouse and touch events are blocked</td>
		</tr>
		<tr>
			<td> `showBlockLayer` </td>
			<td> `boolean` </td>
			<td> `true` </td>
			<td>Defines whether an invisible block layer is rendered to prevent interaction with the UI</td>
		</tr>
		<tr>
			<td> `allowSameOrigin` </td>
			<td> `boolean` </td>
			<td> `true` </td>
			<td>Defines whether same origin domains are allowed or not</td>
		</tr>
		<tr>
			<td> `allowlist` </td>
			<td> `string` </td>
			<td>Contains the domain allowlist \(comma-separated\)</td>
		</tr>
	</tbody>
</table>

***

### Example: `deny`

If the application is not intended to run in a frame, set `frameOptions` to `deny`:

``` html
<script id='sap-ui-bootstrap'
    src='resources/sap-ui-core.js'
    data-sap-ui-frameOptions='deny'>
</script>
```

***

### Example: `trusted` with `callback` 

To restrict the embedding to same-origin domains, set `frameOptions` to `trusted`. The `callback` in the following code sample is called with a boolean as success state and can be used to implement an application-specific behavior.

``` html

<script>
window["sap-ui-config"] = {
    frameOptions: 'trusted',
    frameOptionsConfig: {
        callback: function(bSuccess) {
            if (bSuccess) {
                alert("App is allowed to run!");
            } else {
                alert("App is not allowed to run!");
            }
        }
    }
};
</script>
<script id='sap-ui-bootstrap'
    src='resources/sap-ui-core.js'>
</script>
```

***

### Example: Allowlist Service

To allow that the OpenUI5 application is embedded in cross-origin domains, configure an allowlist service. The allowlist service checks whether the application can run in the parent origin, or not.

``` html
<script>
window["sap-ui-config"] = {
    allowlistService: 'url/to/allowlist/service',
    frameOptions: 'trusted',
    frameOptionsConfig: {
        callback: function(bSuccess) {
            if (bSuccess) {
                alert("App is allowed to run!");
            } else {
                alert("App is not allowed to run!");
            }
        }
    }
};
</script>
<script id='sap-ui-bootstrap'
    src='resources/sap-ui-core.js'>
</script>
```

***

### Example: Allowlist Service via `<meta>` Tag

Alternatively, a `<meta>` tag can be used to configure the `allowlistService` and set the `frameOptions` to `trusted`. This only applies if the `allowlistService` or `frameOptions` configuration is not set in the OpenUI5 configuration.

``` html
<meta name="sap.allowlistService" content="url/to/allowlist/service" />
<script  id='sap-ui-bootstrap'
    src='resources/sap-ui-core.js'>
</script>
```

**Related Information**  


[Allowlist Service](Allowlist_Service_d04a6d4.md)

[Configuration Options and URL Parameters](Configuration_Options_and_URL_Parameters_91f2d03.md)

