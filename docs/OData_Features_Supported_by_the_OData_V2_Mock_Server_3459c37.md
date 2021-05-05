<!-- loio3459c372aaaa4c31ab87bb0e174adcc3 -->

| loio |
| -----|
| 3459c372aaaa4c31ab87bb0e174adcc3 |

<div id="loio">

view on: [demo kit nightly build](https://openui5nightly.hana.ondemand.com/#/topic/3459c372aaaa4c31ab87bb0e174adcc3) | [demo kit latest release](https://openui5.hana.ondemand.com/#/topic/3459c372aaaa4c31ab87bb0e174adcc3)</div>

## OData Features Supported by the OData V2 Mock Server

List of OData version 2.0 features supported or not supported by the mock server

The mock server only supports the JSON format for representing the resources it exposes, such as collections, entries, and links.

> ### Restriction:  
> The mock server cannot mock more than one service per application.

The following table lists the OData features that are supported by the mock server.

 <a name="loio3459c372aaaa4c31ab87bb0e174adcc3__table_h31_lzq_qv"/>Supported OData Features

|Feature

|Status

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>---------</th>
			<th>--------</th>
		</tr>
	</thead>
	<tbody>

			<td>Supported
			</td>
		</tr>
		<tr>
			<td>Navigations
			</td>
			<td>Supported
			</td>
		</tr>
		<tr>
			<td> **Query String options:** 
			</td>
		</tr>
		<tr>
			<td>- Orderby System Query Option \(`$orderby`\)
			</td>
			<td>Supported
			</td>
		</tr>
		<tr>
			<td>- Top System Query Option \(`$top`\)
			</td>
			<td>Supported
			</td>
		</tr>
		<tr>
			<td>- Skip System Query Option \(`$skip`\)
			</td>
			<td>Supported
			</td>
		</tr>
		<tr>
			<td>- Filter System Query Option \(`$filter`\)
			</td>
			<td>Supported; `eq`, `ne`, `gt`, `lt`, `ge`, `le`, `substringof`, `startswith`, `endswith`, `and`, `or` 
			</td>
		</tr>
		<tr>
			<td>- Expand System Query Option \(`$expand`\)
			</td>
			<td>Supported
			</td>
		</tr>
		<tr>
			<td>- Select System Query Option \(`$select`\)
			</td>
			<td>Supported
			</td>
		</tr>
		<tr>
			<td>- Inlinecount System Query Option \(`$inlinecount`\)
			</td>
			<td>Supported
			</td>
		</tr>
		<tr>
			<td>- Format System Query Option \(`$format`\)
			</td>
			<td>Supported; only JSON format is allowed
			</td>
		</tr>
		<tr>
			<td>Batch processing
			</td>
			<td>Supported
			</td>
		</tr>
		<tr>
			<td>Multiple services
			</td>
			<td>Supported; we recommend to create one Mock Server instance per service
			</td>
		</tr>
		<tr>
			<td>Update via `MERGE`/`PATCH` 
			</td>
			<td>Supported
			</td>
		</tr>
		<tr>
			<td>ETag handling
			</td>
			<td>Supported
			</td>
		</tr>
	</tbody>
</table>

The following table lists the OData features that are **not** supported by the mock server.

 <a name="loio3459c372aaaa4c31ab87bb0e174adcc3__table_ymm_pzq_qv"/>Unsupported OData Features

|Feature

|Status

|
 > **Warning:** The below table contains complex elements that cannot not be displayed within a simple markdown table. It has been automatically converted to an HTML table. It's design may vary from the source page!

<table>
	<thead>
		<tr>
			<th>---------</th>
			<th>--------</th>
		</tr>
	</thead>
	<tbody>

			<td>Unsupported, but can be extended
			</td>
		</tr>
		<tr>
			<td>Annotations
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td>Getting individual properties of an entity \(`$value`\)
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td> `Edm.DateTime` keys
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td> `Edm.DateTime` values
			</td>
			<td>All dates have to be either before 2017 or after; you cannot use mixed values
			</td>
		</tr>
		<tr>
			<td> `metadata.xml` with properties from `datetimeoffset` 
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td>Key of type `Edm.Boolean` 
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td>Key of type `Edm.Int64` 
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td> `$links` and `#AddressingLinksBetweenEntries` 
			</td>
			<td>Unsupported
For more information see [Addressing Links between Entries](http://www.odata.org/documentation/odata-version-2-0/uri-conventions/#AddressingLinksBetweenEntries) and [Referencing Requests in a Change Set](http://www.odata.org/documentation/odata-version-2-0/batch-processing/#ReferencingRequestsInAChangeSet) on [http://www.odata.org/](http://www.odata.org/).
			</td>
		</tr>
		<tr>
			<td>Multiple navigation properties
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td>Response in byte array format
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td>Combination of the system queries `$select` and `$expand` in mocked OData services
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td>Filter query string operator \(`$filter`\) with one of the functions `substringof(string po, string p1)`, `endswith(string p0, string p1)` or `startswith(string p0, string p1)` 
			</td>
			<td>Does not support input strings \(`p0` or `p1`\) containing a comma `,`.
			</td>
		</tr>
		<tr>
			<td>Key values containing a comma
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td>System query option `$expand` with multiple multi-level navigation properties with the same root navigation property
			</td>
			<td>Unsupported
			</td>
		</tr>
		<tr>
			<td>Filter query `$filter` on fields from type `edm.datetime` 
			</td>
			<td>Unsupported
			</td>
		</tr>
	</tbody>
</table>

