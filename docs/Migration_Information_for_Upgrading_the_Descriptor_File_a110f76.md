<!-- loioa110f762148a4933a33d30751a37a743 -->

| loio |
| -----|
| a110f762148a4933a33d30751a37a743 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/a110f762148a4933a33d30751a37a743) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/a110f762148a4933a33d30751a37a743)</div>

## Migration Information for Upgrading the Descriptor File

Information how to add new attributes of descriptor versions higher than V2 \(OpenUI5 1.30\) to the descriptor file.

 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>Attribute</th>
			<th>Version\*</th>
			<th>Description</th>
			<th>Example</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td> `_version` </td>
			<td>V3 \(1.32\)</td>
			<td>Needs to be updated in the `manifest.json` file when migrating to a new descriptor version:

 -   `_version` for V3 is 1.2.0
 -   `_version` for V4 is 1.3.0

 -   `_version` for V5 is 1.4.0 \(see example\)
			</td>
			<td> 

```
{
    "_version": "1.4.0",
    "sap.app": {
        ...
```
			</td>
		</tr>
		<tr>
			<td> `sap.app/crossNavigation` </td>
			<td>V3 \(1.32\)</td>
			<td>Contains navigation information and is a mandatory attribute in the `manifest.json` file for SAP Fiori apps; the attribute contains two sections:

 -   `sap.app/crossNavigation/inbounds` - Contains inbound intents and signature information
 -   `sap.app/crossNavigation/outbounds` - Contains required intents that are called explicitely by the app, for example, if a business process is split among different apps A and B. If A calls B, A has outbound the intent to address B.
			</td>
		</tr>
		<tr>
			<td> `sap.app/subTitle` </td>
			<td>V4 \(1.34\)</td>
			<td>Added to the `manifest.json` file by using the `{{...}}` syntax

 > Note:
 > Text symbols must be part of the properties file which is defined in `sap.app/i18n` \(default `"i18n/i18n.properties"`\).
			</td>
			<td> 

```
"sap.app": {
    "_version": "1.3.0",
    ...
    "title": "{{title}}",
    "subTitle": "{{subtitle}}",
```
			</td>
		</tr>
		<tr>
			<td> `sap.app/crossNavigation/inbounds/<inboundname>/subTitle` </td>
			<td>V4 \(1.34\)</td>
			<td>Used to overwrite the `subTitle` attribute per inbound; use the `{{...}}` syntax to add the attribute to the `manifest.json` file

 > Note:
 > Text symbols must be part of the properties file which is defined in `sap.app/i18n` \(default `"i18n/i18n.properties"`\).
			</td>
			<td> 

```
"sap.app": {
    "_version": "1.3.0",
    ...
    "crossNavigation": {
        "inbounds": {
            "contactCreate":
                {
                    "semanticObject": "Contact",
                    "action": "create",
                    "icon": "sap-icon://add-contact",
                    "title": "{{title}}",
                    "subTitle": "{{subtitleOther}}",
```
			</td>
		</tr>
		<tr>
			<td> `sap.ui/fullWidth` </td>
			<td>V4 \(1.34\)</td>
```

 |
| `sapui5/routing/config/async` |V4 \(1.34\)|General setting for routing that indicates how the views are loaded; if set to `true`, the views are loaded asynchronously \(default is `false`\) For performance reasons, we recommend to always use the `async` setting. This recommendation implies that you have followed the OpenUI5 programming model in general and do *HIGHLIGHT START*not*HIGHLIGHT END* rely on any sync-execution depending event-orders.| ```
"sap.ui5": {
   "_version": "1.2.0",
   ...
    "routing": {
        "config": {
            "viewType": "XML",
            "async": true
        ...
        },
        ...
```
			<td>If `dependencies/components/<componentname>/lazy` and `dependencies/libs/<libname>/lazy` are set to `true`, the attribute indicates in an SAP Fiori app that a dependency shall be lazy loaded \(default is `false`\), see the example for `manifest.json` for the SAP Fiori app.</td>
			<td>Example for `manifest.json` for the SAP Fiori app: 

```
"sap.ui5": {
   "_version": "1.2.0",
   ...
   "dependencies": {
        "minUI5Version": "1.34.0",
        "libs": {
            "sap.m": {
                "minVersion": "1.34.0"
            },
            "sap.ui.commons": {
                "minVersion": "1.34.0",
                "lazy": true
            }
        },
        "components": {
            "sap.ui.app.other": {
                "minVersion": "1.1.0"
                "lazy": true
            }
        }
    },
```
			</td>
		</tr>
		<tr>
			<td> `sapui5/routing/config/async` </td>
			<td>V4 \(1.34\)</td>
			<td>General setting for routing that indicates how the views are loaded; if set to `true`, the views are loaded asynchronously \(default is `false`\) For performance reasons, we recommend to always use the `async` setting. This recommendation implies that you have followed the OpenUI5 programming model in general and do **not** rely on any sync-execution depending event-orders.</td>
			<td> 

```
"sap.ui5": {
   "_version": "1.2.0",
   ...
    "routing": {
        "config": {
            "viewType": "XML",
            "async": true
        ...
        },
        ...
```
			</td>
		</tr>
		<tr>
			<td> `sap.ui5/models/preload` </td>
			<td>V5 \(1.38\)</td>
			<td>Defines whether or not the model is initialized \(preloaded\) before the component instance is created and while loading the component preload and its dependencies</td>
			<td> 

```
"equipment": { 
    "preload": true,
    "dataSource": "equipment",
     ...
}

```
			</td>
		</tr>
	</tbody>
</table>

\* Available as of descriptor version \(OpenUI5 version\)

