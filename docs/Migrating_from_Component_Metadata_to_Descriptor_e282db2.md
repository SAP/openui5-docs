<!-- loioe282db2865e94f69972c407469b801e9 -->

| loio |
| -----|
| e282db2865e94f69972c407469b801e9 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/e282db2865e94f69972c407469b801e9) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/e282db2865e94f69972c407469b801e9)</div>

## Migrating from Component Metadata to Descriptor

Overview, how the component metadata are mapped to the descriptor.

For compatibility reasons, the mapping to the `manifest.json` file is done automatically. If a metadata property has been defined, it can also be consumed via the corresponding property of the `manifest.json` file. For a detailed step-by-step guide, see [Creating a Descriptor File for Existing Apps](Creating_a_Descriptor_File_for_Existing_Apps_3a9baba.md).

> ### Note:  
> To benefit from the performance improvements that can be achieved by using “manifest first”, we recommend to migrate the component metadata to the descriptor \(`manifest.json`\). For more information about manifest first, see the *Manifest First Function* section in [Descriptor for Applications, Components, and Libraries](Descriptor_for_Applications,_Components,_and_Libraries_be0cf40.md).

<a name="loioe282db2865e94f69972c407469b801e9__table_ogz_llt_45"/>Mapping Table

|Metadata

|Descriptor

|Comment

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>----------</th>
			<th>------------</th>
			<th>---------</th>
		</tr>
	</thead>
	<tbody>

			<td> `sap.app/id` 
			</td>
			<td>-
			</td>
		</tr>
		<tr>
			<td> `version` 
			</td>
			<td> `sap.app/applicationVersion/version` 
			</td>
			<td>-
			</td>
		</tr>
		<tr>
			<td> `config` 
			</td>
			<td> `sap.ui5/config` 
			</td>
			<td>-
			</td>
		</tr>
		<tr>
			<td> `dependencies` 
			</td>
			<td> `sap.ui5/depedencies` 
			</td>
			<td>Different format, see *Dependencies* section below
			</td>
		</tr>
		<tr>
			<td> `customizing` 
			</td>
			<td> `sap.ui5/extends/extensions` 
			</td>
			<td>-
			</td>
		</tr>
		<tr>
			<td> `handleValidation` 
			</td>
			<td> `sap.ui5/handleValidation` 
			</td>
			<td>-
			</td>
		</tr>
		<tr>
			<td> `includes` 
			</td>
			<td> `sap.ui5/resources` 
			</td>
			<td>Different format, see *Resources* section below
			</td>
		</tr>
		<tr>
			<td> `rootView` 
			</td>
			<td> `sap.ui5/rootView` 
			</td>
			<td>-
			</td>
		</tr>
		<tr>
			<td> `routing` 
			</td>
			<td> `sap.ui5/routing` 
			</td>
			<td>-
			</td>
		</tr>
	</tbody>
</table>

***

### Dependencies

Libraries and components are objects and not arrays. For the descriptor part, we use `minUI5Version` instead of `ui5version`.

**Metadata** 

``` js

"dependencies": {
    "ui5version": "1.30.0",
    "libs": [
        "sap.m",
        "sap.ui.unified"
    ],
    "components": [ "sap.app.otherComponent" ]
}
```

**Descriptor**

``` js

"dependencies": {
    "minUI5Version": "1.30.0",
    "libs": {
        "sap.m": {},
        "sap.ui.unified": {}
    },
    "components": {
        "sap.app.otherComponent": {}
    }
}
```

***

### Resources

Includes are renamed to resources and are objects and not an array.

**Metadata**

``` js

"includes": ["script.js", "style.css"]
```

**Descriptor**

``` js

"resources": {
    "js": [
        {
            "uri": "script.js"
        }
    ],
    "css": [
        {
            "uri": "style.css"
        }
    ]
}
```

